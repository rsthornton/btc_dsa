# Bitcoin Agent-Based Model

## Implementation Analysis

This notebook implements the generalized blockchain agent-based model framework described in Kaligotla and Macal's paper "A Generalized Agent Based Framework for Modeling a Blockchain System" with Bitcoin-specific extensions.

### Agent Types Implementation

#### Market Agents
The paper defines market agents as participants in bilateral transactions with unique identifiers and wallets. This notebook extends this concept by creating three user subtypes:

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

### Transaction System

#### Transaction Creation
The paper defines transactions as τn(i,j,v,g,t,σ) where n is transaction ID, i is source, j is recipient, v is value, g is gas/fee, t is time, and σ is verification status.

Bitcoin-specific additions include:
- Transaction size (in bytes)
- Fee rate (satoshis per byte)
- User transaction types

#### Mempool (Pending Transaction Queue)
The paper describes a Pending Transaction Queue (PTQ) of unverified transactions. The notebook implements this as the mempool.

#### Mining Process
The paper describes miners selecting blocks of transactions to verify.

Bitcoin-specific extensions:
- Block size limit (1,000,000 bytes)
- Difficulty adjustment
- Hashrate calculations
- Probabilistic mining success

### Mining Strategies

The paper outlines three mining strategies:
- **LARGEST**: Miners choose blocks with highest rewards
- **POLAR**: High-performing miners choose high-reward blocks, low-performing miners choose low-reward blocks
- **PARTITION**: Miners select blocks matched to their relative computing power

The notebook implements the LARGEST strategy.

### Energy Consumption

The paper emphasizes energy efficiency as a critical concern for blockchain systems. The notebook implements energy tracking to enable:
- Energy tracking over time
- Analysis of energy per transaction
- Potential for testing energy efficiency of different mining strategies

### Research Extensions and Applications

The notebook provides a foundation for several research directions:

1. **Mining Strategy Comparison**: Extending the model to implement POLAR and PARTITION strategies to compare energy efficiency
   
2. **Network Effects**: Analyzing how changes in user types affect transaction patterns and miner rewards

3. **Scalability Analysis**: Testing system behavior under varying transaction loads and miner counts

4. **Economic Incentives**: Analyzing the relationship between fees, block rewards, and miner participation

5. **Energy Efficiency**: Testing hypotheses about proof-of-work alternatives and their impacts on system security and energy consumption

This model provides a valuable tool for cryptoeconomic researchers to understand complex blockchain system dynamics without requiring deployment on actual networks.