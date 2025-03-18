# Bitcoin System Dynamics Model Analysis

## From Academic Theory to Computational Implementation

This document analyzes the implementation of system dynamics concepts from "Modeling the Trajectory of Bitcoin using System Dynamics" (Gopalakrishnan, 2022) in the `btc_sd.ipynb` notebook.

### 1. Core System Dynamics Structures

The MIT thesis develops a comprehensive system dynamics model of Bitcoin with several key structural components. The notebook implements these using cadCAD (Complex Adaptive Dynamics Computer-Aided Design), a Python framework for modeling complex systems.

#### Stocks and Flows

The paper identifies several key stock variables including:
- Bitcoin supply (mining rewards over time)
- Bitcoin price
- Mining capacity (hash rate)
- User adoption (classified as chartists, fundamentalists, and transactors)

In the notebook, these stocks are implemented as state variables in the initial_state dictionary:

```python
initial_state = {
    'bitcoin_supply': 18.6e6,  # Initial BTC in circulation
    'hashrate': 150e18,        # Initial network hashrate (in hashes/sec)
    'price': 40000,            # Initial BTC price in USD
    'market_sentiment': 0.5,   # Market sentiment (0-1 scale)
    'adoption_rate': 0.2,      # Rate of new user adoption
    'user_types': {
        'chartists': 0.6,      # Speculators following price trends
        'fundamentalists': 0.3, # Investors looking at fundamentals
        'transactors': 0.1     # Users utilizing BTC for transactions
    }
}
```

Flows between these stocks are represented through state update functions:

```python
def update_bitcoin_supply(params, step, sL, s, _input):
    """Implements the bitcoin issuance schedule based on block halving events"""
    current_supply = s['bitcoin_supply']
    current_time = step
    halving_interval = 210000  # blocks (approximately 4 years)
    blocks_per_day = 144       # average blocks mined per day
    
    # Calculate new issuance based on halving schedule
    days_elapsed = current_time / blocks_per_day
    halvings = int(days_elapsed / (halving_interval / blocks_per_day))
    daily_issuance = 6.25 * (0.5 ** halvings) * blocks_per_day
    
    new_supply = current_supply + daily_issuance
    return ('bitcoin_supply', new_supply)
```

#### Feedback Loops

The paper identifies several crucial feedback loops in the Bitcoin ecosystem:

1. **Mining Profitability Loop**: Higher prices → more mining investment → higher hash rate → higher difficulty → lower mining profitability → price stabilization

2. **Adoption Feedback**: Rising prices → increased attention → more adoption → more demand → higher prices

3. **Speculative Feedback**: Price increases → positive sentiment → more buying from chartists → higher prices

The notebook implements these loops through policy functions and state update functions:

```python
def hashrate_policy(params, step, sL, s):
    """Models miners' decisions to add or remove hashrate based on profitability"""
    current_price = s['price']
    current_hashrate = s['hashrate']
    electricity_cost = params['electricity_cost']
    hardware_efficiency = params['hardware_efficiency']
    
    # Calculate mining profitability
    mining_reward = 6.25  # Current block reward
    daily_blocks = 144    # Avg blocks per day
    daily_reward_usd = mining_reward * daily_blocks * current_price
    
    # Estimate network hashrate adjustment based on profitability
    profitability = daily_reward_usd / (current_hashrate * electricity_cost * hardware_efficiency)
    
    # Miners add hashrate when profitable, remove when unprofitable
    hashrate_change = current_hashrate * (0.1 * (profitability - 1))
    
    return {'hashrate_change': hashrate_change}
```

### 2. Bitcoin Price Mechanisms

The paper describes Bitcoin's price formation as resulting from supply-demand dynamics, speculation, and market sentiment. The notebook implements this through:

```python
def price_policy(params, step, sL, s):
    """Models price formation based on supply-demand balance and sentiment"""
    current_price = s['price']
    market_sentiment = s['market_sentiment']
    adoption_rate = s['adoption_rate']
    user_types = s['user_types']
    
    # Calculate price impact from different user types
    chartist_impact = user_types['chartists'] * market_sentiment * 0.2
    fundamentalist_impact = user_types['fundamentalists'] * (0.5 - market_sentiment) * 0.1
    transaction_demand = user_types['transactors'] * adoption_rate * 0.05
    
    # Combined price pressure
    price_change_pct = chartist_impact + fundamentalist_impact + transaction_demand
    
    # Apply random market noise
    noise = np.random.normal(0, 0.02)
    
    return {'price_change': current_price * (price_change_pct + noise)}
```

This implementation captures the paper's recognition that price formation is influenced by:
- Chartists (technical traders following momentum)
- Fundamentalists (value-based investors)
- Transactors (utility-based users)

### 3. Mining Economics and Difficulty Adjustment

The paper emphasizes how Bitcoin's difficulty adjustment mechanism creates a balancing feedback loop that regulates mining profitability. The notebook implements this with:

```python
def update_hashrate(params, step, sL, s, _input):
    """Updates network hashrate based on mining profitability"""
    current_hashrate = s['hashrate']
    hashrate_change = _input.get('hashrate_change', 0)
    
    # Apply constraints to prevent negative hashrate
    new_hashrate = max(1e12, current_hashrate + hashrate_change)
    
    return ('hashrate', new_hashrate)

def update_difficulty(params, step, sL, s, _input):
    """Implements Bitcoin's difficulty adjustment mechanism"""
    target_block_time = 10 * 60  # 10 minutes in seconds
    adjustment_period = 2016      # blocks
    
    current_hashrate = s['hashrate']
    
    # Calculate implied difficulty to maintain 10-minute block time
    implied_difficulty = current_hashrate * target_block_time / (2**32)
    
    return ('difficulty', implied_difficulty)
```

This implementation captures the core balancing mechanism where higher hashrate leads to higher difficulty, which in turn reduces mining profitability until equilibrium is reached.

### 4. User Adoption Dynamics

The paper classifies Bitcoin users into three categories with different behaviors. The notebook models adoption dynamics with:

```python
def update_adoption(params, step, sL, s, _input):
    """Models the growth in Bitcoin adoption over time"""
    current_adoption = s['adoption_rate']
    current_price = s['price']
    price_change = _input.get('price_change', 0)
    
    # Adoption increases with positive price momentum but has a cap
    price_impact = 0.01 * (price_change / current_price) if price_change > 0 else 0
    
    # Logistic growth function with carrying capacity of 1.0
    growth_factor = 0.001 + price_impact
    new_adoption = current_adoption + growth_factor * current_adoption * (1 - current_adoption)
    
    return ('adoption_rate', new_adoption)

def update_user_types(params, step, sL, s, _input):
    """Updates the distribution of user types based on price trends"""
    user_types = s['user_types'].copy()
    price_change = _input.get('price_change', 0)
    current_price = s['price']
    
    # In bull markets, chartists increase; in bearish markets, fundamentalists increase
    if price_change > 0:
        # Shift 1% from fundamentalists to chartists in bull markets
        shift = min(0.01, user_types['fundamentalists'])
        user_types['chartists'] += shift
        user_types['fundamentalists'] -= shift
    else:
        # Shift 1% from chartists to fundamentalists in bear markets
        shift = min(0.01, user_types['chartists'])
        user_types['fundamentalists'] += shift
        user_types['chartists'] -= shift
    
    return ('user_types', user_types)
```

This implementation reflects the paper's description of how different user types respond to market conditions and how adoption follows a diffusion-like pattern influenced by price performance.

### 5. System Structure Simulations

The notebook brings all these components together using cadCAD's partial state update blocks structure:

```python
partial_state_update_blocks = [
    {
        'policies': {
            'mining': hashrate_policy,
            'price': price_policy,
        },
        'variables': {
            'bitcoin_supply': update_bitcoin_supply,
            'hashrate': update_hashrate,
            'difficulty': update_difficulty,
            'price': update_price,
            'market_sentiment': update_sentiment,
            'adoption_rate': update_adoption,
            'user_types': update_user_types
        }
    }
]
```

This simulation framework enables analysis of complex scenarios described in the paper:

```python
from cadCAD.engine import ExecutionMode, ExecutionContext, Executor
from cadCAD.configuration import Configuration

config = Configuration(
    initial_state=initial_state,
    partial_state_update_blocks=partial_state_update_blocks,
    sim_config=sim_config
)

exec_mode = ExecutionMode()
exec_context = ExecutionContext(exec_mode.single_proc)
executor = Executor(exec_context, [config])
raw_result, tensor_field, sessions = executor.execute()

# Process results for analysis
results = pd.DataFrame(raw_result)
```

### 6. Research Applications and Insights

The notebook enables exploration of several key research questions raised in the paper:

1. **Long-term Price Trajectory**: By simulating different adoption scenarios and mining economics, the model explores potential future price paths.

2. **Energy Consumption**: The model calculates energy consumption based on hashrate and hardware efficiency, allowing estimation of Bitcoin's environmental impact.

3. **Mining Centralization Risk**: By modeling mining profitability across different electricity cost scenarios, the model reveals how mining could concentrate in regions with cheap electricity.

4. **Policy Impact Analysis**: The model can simulate the effects of regulatory changes by modifying parameters like electricity costs or adoption rates.

### Conclusion

The `btc_sd.ipynb` notebook effectively translates the system dynamics concepts from "Modeling the Trajectory of Bitcoin using System Dynamics" into a computational framework. By implementing stocks, flows, and feedback loops as state variables and update functions, the notebook creates a platform for exploring Bitcoin's complex dynamics.

This implementation demonstrates how system dynamics modeling can help understand emergent behaviors in cryptocurrency ecosystems, test policy interventions, and make projections about future states under different scenarios. The model's structure allows researchers to explore the implications of different feedback mechanisms and understand the complex interplay between technical protocol design and market behaviors.