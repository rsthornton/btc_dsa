# Bitcoin Computational Simulations

This directory contains Bitcoin simulations using two complementary modeling frameworks: Agent-Based Modeling (ABM) and System Dynamics (SD). These simulations implement concepts from the accompanying Deep Systems Analysis paper.

## Contents

- `btc_abm.ipynb`: Agent-Based Model implementation of Bitcoin based on Kaligotla and Macal's framework
- `btc_sd.ipynb`: System Dynamics Model implementation of Bitcoin based on Gopalakrishnan's MIT thesis
- `btc_abm_analysis.md`: Analysis of the ABM implementation and its relationship to theory
- `btc_sd_analysis.md`: Analysis of the SD implementation and its relationship to theory

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
   - [Open ABM Notebook in Colab](https://colab.research.google.com/drive/1AlQmLd51xPCS0HNHiGFGyv4lLdqTp17w)

2. **System Dynamics Model (SD)**:
   - [Open SD Notebook in Colab](https://colab.research.google.com/drive/1fLwkYTXegprwllNtRAGUPEV25DpmqfcW)

### Option 2: Local Installation

To run these simulations locally:

1. Ensure you have Python 3.8+ and Jupyter Notebook installed
2. Install required packages: `pip install -r requirements.txt`
3. Launch Jupyter: `jupyter notebook`
4. Navigate to either the `btc_abm/` or `btc_sd/` directory
5. Open the respective notebook

## Documentation

Each notebook contains detailed comments explaining the implementation. For in-depth analysis:
- See `btc_abm_analysis.md` for details on the Agent-Based Model
- See `btc_sd_analysis.md` for details on the System Dynamics Model