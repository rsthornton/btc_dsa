# Bitcoin Agent-Based Model

This directory contains an agent-based model (ABM) of Bitcoin, developed using the cadCAD simulation framework and guided by Deep Systems Analysis (DSA) methodology.

## Contents

- `btc_abm.ipynb`: Jupyter notebook containing the Bitcoin ABM simulation with integrated DSA narrative

## Model Features

- Different user types (P2P, Investor, Trader) with distinct transaction patterns
- Mining operations with energy consumption tracking
- Transaction validation and block production processes
- Fee market dynamics and emergent network behavior

## Running the Simulation

### Option 1: Google Colab (Recommended)

Run the simulation directly in your browser without any installation:
- [Open ABM Notebook in Colab](https://colab.research.google.com/drive/1XNYkyDZq-Ey_MToYBOqJ_YP6UesKdtyj)

### Option 2: Local Installation

To run locally:
1. Install dependencies: `pip install -r ../requirements.txt`
2. Open the notebook: `jupyter notebook btc_abm.ipynb`
3. Run all cells to execute the simulation

## Implementation Notes

This ABM implements the generalized blockchain framework described in Kaligotla and Macal's paper "A Generalized Agent Based Framework for Modeling a Blockchain System", enhanced with Bitcoin-specific details derived from our DSA process.