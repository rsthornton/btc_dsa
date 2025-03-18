# Bitcoin System Dynamics Model

## Implementation Analysis

This notebook implements system dynamics concepts from "Modeling the Trajectory of Bitcoin using System Dynamics" (Gopalakrishnan, 2022) using cadCAD (Complex Adaptive Dynamics Computer-Aided Design).

### Core System Dynamics Structures

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

#### Feedback Loops

The paper identifies several crucial feedback loops in the Bitcoin ecosystem:

1. **Mining Profitability Loop**: Higher prices → more mining investment → higher hash rate → higher difficulty → lower mining profitability → price stabilization

2. **Adoption Feedback**: Rising prices → increased attention → more adoption → more demand → higher prices

3. **Speculative Feedback**: Price increases → positive sentiment → more buying from chartists → higher prices

### Bitcoin Price Mechanisms

The paper describes Bitcoin's price formation as resulting from supply-demand dynamics, speculation, and market sentiment. This implementation captures the paper's recognition that price formation is influenced by:
- Chartists (technical traders following momentum)
- Fundamentalists (value-based investors)
- Transactors (utility-based users)

### Mining Economics and Difficulty Adjustment

The paper emphasizes how Bitcoin's difficulty adjustment mechanism creates a balancing feedback loop that regulates mining profitability. This implementation captures the core balancing mechanism where higher hashrate leads to higher difficulty, which in turn reduces mining profitability until equilibrium is reached.

### User Adoption Dynamics

The model reflects the paper's description of how different user types respond to market conditions and how adoption follows a diffusion-like pattern influenced by price performance.

### Research Applications and Insights

The notebook enables exploration of several key research questions raised in the paper:

1. **Long-term Price Trajectory**: By simulating different adoption scenarios and mining economics, the model explores potential future price paths.

2. **Energy Consumption**: The model calculates energy consumption based on hashrate and hardware efficiency, allowing estimation of Bitcoin's environmental impact.

3. **Mining Centralization Risk**: By modeling mining profitability across different electricity cost scenarios, the model reveals how mining could concentrate in regions with cheap electricity.

4. **Policy Impact Analysis**: The model can simulate the effects of regulatory changes by modifying parameters like electricity costs or adoption rates.

This implementation demonstrates how system dynamics modeling can help understand emergent behaviors in cryptocurrency ecosystems, test policy interventions, and make projections about future states under different scenarios.