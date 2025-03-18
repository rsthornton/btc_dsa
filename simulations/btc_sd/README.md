# Bitcoin System Dynamics Model

This notebook implements a Bitcoin system dynamics (SD) model based on Gopalakrishnan's MIT thesis "Modeling the Trajectory of Bitcoin using System Dynamics" (2022).

## Overview

The model simulates Bitcoin's ecosystem by implementing:

1. **Key Stocks**
   - Bitcoin supply: Based on the halving schedule
   - Bitcoin price: Influenced by multiple types of market participants
   - Mining hashrate: Adjusts based on economic incentives
   - User adoption: Follows a logistic growth curve with feedback effects

2. **Critical Feedback Loops**
   - Mining Profitability Loop: Price → mining investment → hashrate → difficulty → profitability
   - Adoption Feedback: Price → attention → adoption → demand → price
   - Speculative Feedback: Price increases → sentiment → chartist buying → price

3. **User Type Dynamics**
   - Chartists: Technical traders following price trends
   - Fundamentalists: Value-based investors
   - Transactors: Utility-focused users

## Key Features

- Models Bitcoin's price formation mechanisms through multiple user influences
- Captures mining economics including difficulty adjustment
- Simulates adoption dynamics with realistic growth patterns
- Implements the core feedback loops that drive Bitcoin's behavior
- Enables simulation of different scenarios and policy impacts

## Research Applications

The simulation enables research into:
- Long-term price trajectory projections
- Energy consumption estimation
- Mining centralization risk assessment
- Regulatory impact analysis
- User distribution evolution

## Implementation Details

The simulation uses cadCAD (Complex Adaptive Dynamics Computer-Aided Design) to model system stocks, flows, and feedback loops. For detailed analysis of the implementation, see the accompanying `btc_sd_analysis.md` file.

## Running the Simulation

### Run Online (Recommended)

The easiest way to explore this model is through Google Colab:

- [Open SD Notebook in Colab](https://colab.research.google.com/drive/1fLwkYTXegprwllNtRAGUPEV25DpmqfcW)

### Run Locally

To run on your local machine:

1. Ensure requirements are installed: `pip install cadCAD pandas numpy matplotlib`
2. Open `btc_sd.ipynb` in Jupyter Notebook
3. Run all cells to execute the simulation
4. Explore the results through the provided visualizations