# Bitcoin Computational Simulations

This directory contains Bitcoin simulations using two complementary modeling frameworks: Agent-Based Modeling (ABM) and System Dynamics (SD). Both implementations are guided by Deep Systems Analysis (DSA) methodology.

## Contents

- `btc_abm/`: Agent-Based Model implementation of Bitcoin
- `btc_sd/`: System Dynamics Model implementation of Bitcoin
- `requirements.txt`: Dependencies for running the simulations

## Agent-Based Model (ABM)

The ABM simulation models Bitcoin from the bottom up by implementing different agent types:
- Market participants (P2P Users, Investors, Traders)
- Miners with varying computational power
- Network nodes for transaction verification

This approach captures emergent behaviors and allows exploration of mining strategies, energy consumption, and transaction fee markets.

## System Dynamics (SD)

The SD simulation models Bitcoin from the top down by implementing:
- Key stocks (Bitcoin supply, price, hashrate, user adoption)
- Critical feedback loops (mining profitability, adoption dynamics, price formation)
- User type behaviors (chartists, fundamentalists, transactors)

This approach focuses on macro-level dynamics and feedback relationships between system variables.

## Getting Started

### Option 1: Google Colab (Recommended)

Access and run the simulations directly in your browser:

1. **Agent-Based Model (ABM)**:
   - [Open ABM Notebook in Colab](https://colab.research.google.com/drive/1XNYkyDZq-Ey_MToYBOqJ_YP6UesKdtyj)

2. **System Dynamics Model (SD)**:
   - [Open SD Notebook in Colab](https://colab.research.google.com/drive/1U7PfPnGQyVTyqXG3mX_77ZJLkP3DWsy3)

### Option 2: Local Installation

To run these simulations locally:

1. Ensure you have Python 3.8+ and Jupyter Notebook installed
2. Install required packages: `pip install -r requirements.txt`
3. Launch Jupyter: `jupyter notebook`
4. Navigate to either the `btc_abm/` or `btc_sd/` directory
5. Open the respective notebook

## Implementation Notes

Both simulations use the cadCAD framework to model Bitcoin's complex dynamics. The notebooks include narrative sections that explain how DSA facilitated the rapid development of these simulations by identifying key system components, flows, and feedback mechanisms.