# Bitcoin Agent-Based Model Analysis

## From Generalized Framework to Bitcoin Implementation

This document analyzes how the `btc_abm.ipynb` notebook implements the generalized blockchain agent-based model framework described in Kaligotla and Macal's paper "A Generalized Agent Based Framework for Modeling a Blockchain System".

### 1. Agent Types Implementation

#### Market Agents
The paper defines market agents as participants in bilateral transactions with unique identifiers and wallets. The notebook extends this concept by creating three user subtypes:

```python
'users': [{'id': i, 'type': random.choice(['P2P', 'Investor', 'Trader'])} for i in range(50)]
```

Each user type exhibits distinct transaction behaviors:
- **P2P users**: Lower transaction rates (0.5), medium transaction sizes (480 bytes)
- **Investors**: Lower transaction frequency (0.2), larger transaction sizes (1000 bytes)
- **Traders**: Higher transaction frequency (0.7), medium transaction sizes (720 bytes)

#### Miner Agents
The paper describes miners with identifiers, wallets, computing power, and costs. The notebook implements:

```python
'miners': [{'id': i, 'compute_power': random.uniform(1.0, 5.0), 'wallet': 0} for i in range(10)]
```

Key properties:
- Unique ID
- Variable compute power (1.0-5.0)
- Wallet for tracking earnings
- Implicit mining cost through energy consumption calculations

### 2. Transaction System

#### Transaction Creation
The paper defines transactions as τn(i,j,v,g,t,σ) where n is transaction ID, i is source, j is recipient, v is value, g is gas/fee, t is time, and σ is verification status.

The notebook implements this through the user_policy function:

```python
new_txs.append({
    'size': size,
    'fee_rate': fee_rate,
    'fee': fee,
    'user_id': user['id'],
    'type': user['type']
})
```

Bitcoin-specific additions include:
- Transaction size (in bytes)
- Fee rate (satoshis per byte)
- User transaction types

#### Mempool (Pending Transaction Queue)
The paper describes a Pending Transaction Queue (PTQ) of unverified transactions. The notebook implements this as the mempool:

```python
def update_mempool(params, step, sL, s, _input):
    mempool = s['mempool'].copy()
    new_txs = _input.get('new_transactions', [])
    mined_txs = _input.get('mined_transactions', [])
    
    mempool.extend(new_txs)
    for tx in mined_txs:
        if tx in mempool:
            mempool.remove(tx)
            
    return ('mempool', mempool)
```

#### Mining Process
The paper describes miners selecting blocks of transactions to verify. The notebook implements this through:

```python
def miner_policy(params, step, sL, s):
    # Selection of transactions
    mempool.sort(key=lambda x: x['fee_rate'], reverse=True)
    current_size = 0
    for tx in mempool:
        if current_size + tx['size'] <= block_size_limit:
            mined_txs.append(tx)
            current_size += tx['size']
        else:
            break
            
    # Mining probability
    total_hashrate = sum(miner['compute_power'] for miner in agents['miners']) * 10
    difficulty = 1 + (step / 10)
    block_chance = min(0.8, total_hashrate / (difficulty * 1000))
```

Bitcoin-specific extensions:
- Block size limit (1,000,000 bytes)
- Difficulty adjustment
- Hashrate calculations
- Probabilistic mining success

### 3. Mining Strategies

The paper outlines three mining strategies:
- **LARGEST**: Miners choose blocks with highest rewards
- **POLAR**: High-performing miners choose high-reward blocks, low-performing miners choose low-reward blocks
- **PARTITION**: Miners select blocks matched to their relative computing power

The notebook implements the LARGEST strategy:

```python
mempool.sort(key=lambda x: x['fee_rate'], reverse=True)
```

Additionally, the notebook implements a weighted selection mechanism for mining rewards:

```python
total_power = sum(m['compute_power'] for m in miners)
weights = [m['compute_power'] / total_power for m in miners]
winner = random.choices(miners, weights=weights)[0]
```

This creates a foundation for implementing the more complex POLAR and PARTITION strategies, which could involve segmenting the mempool based on miner capabilities.

### 4. Energy Consumption

The paper emphasizes energy efficiency as a critical concern for blockchain systems. The notebook implements energy tracking:

```python
energy_increment = total_hashrate * 0.1 * 15 / 1e9

def update_energy(params, step, sL, s, _input):
    energy = s['energy_used']
    energy_increment = _input.get('energy_increment', 0)
    return ('energy_used', energy + energy_increment)
```

This enables:
- Energy tracking over time
- Analysis of energy per transaction
- Potential for testing energy efficiency of different mining strategies

### 5. Blockchain System Components

#### Public Ledger
The paper describes a public ledger (L) as a vector of verified transactions. The notebook implements:

```python
def update_ledger(params, step, sL, s, _input):
    ledger = s['ledger'].copy()
    mined_txs = _input.get('mined_transactions', [])
    if mined_txs:
        ledger.append(mined_txs)
    return ('ledger', ledger)
```

#### Consensus Mechanism
The paper discusses consensus as agreement on the ledger's structure. The notebook implements a simplified consensus:

```python
def node_policy(params, step, sL, s):
    agents = s['agents']
    ledger = s['ledger']
    synced_nodes = 0
    for node in agents['nodes']:
        if ledger and random.random() < 0.9:
            synced_nodes += 1
    return {'synced_nodes': synced_nodes}
```

#### System State Transitions
The paper defines system state as BCt = {Xt, Yt, PTQt, Lt}. The notebook uses cadCAD to implement this:

```python
exp = Experiment()
exp.append_configs(
    initial_state=initial_state,
    partial_state_update_blocks=partial_state_update_blocks,
    sim_configs=sim_config
)
```

This enables structured simulation of the entire blockchain system.

### 6. Research Extensions and Applications

The notebook provides a foundation for several research directions:

1. **Mining Strategy Comparison**: Extending the model to implement POLAR and PARTITION strategies to compare energy efficiency
   
2. **Network Effects**: Analyzing how changes in user types affect transaction patterns and miner rewards

3. **Scalability Analysis**: Testing system behavior under varying transaction loads and miner counts

4. **Economic Incentives**: Analyzing the relationship between fees, block rewards, and miner participation

5. **Energy Efficiency**: Testing hypotheses about proof-of-work alternatives and their impacts on system security and energy consumption

### Conclusion

The `btc_abm.ipynb` notebook successfully implements the generalized blockchain framework described by Kaligotla and Macal while adding Bitcoin-specific details. It demonstrates how agent-based modeling can be applied to blockchain systems to test theories, analyze behaviors, and explore alternative designs.

The model provides a valuable tool for cryptoeconomic researchers to understand complex blockchain system dynamics without requiring deployment on actual networks. By extending the model with additional strategies and parameters, researchers can explore a wide range of scenarios relevant to blockchain design, economics, and environmental impact.