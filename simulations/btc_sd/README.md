# Bitcoin System Dynamics Model

This directory contains a system dynamics (SD) model of Bitcoin, developed using the cadCAD simulation framework and guided by Deep Systems Analysis (DSA) methodology.

## Contents

- `btc_sd.ipynb`: Jupyter notebook containing the Bitcoin SD simulation with integrated DSA narrative

## Model Features

- Bitcoin price formation through multiple user type interactions
- Mining economics with difficulty adjustment feedback loops
- Adoption dynamics with realistic growth patterns
- Stock-to-flow ratio and monetary policy effects
- Energy consumption projections

## Running the Simulation

### Option 1: Google Colab (Recommended)

Run the simulation directly in your browser without any installation:
- [Open SD Notebook in Colab](https://colab.research.google.com/drive/1U7PfPnGQyVTyqXG3mX_77ZJLkP3DWsy3)

### Option 2: Local Installation

To run locally:
1. Install dependencies: `pip install -r ../requirements.txt`
2. Open the notebook: `jupyter notebook btc_sd.ipynb`
3. Run all cells to execute the simulation

## Implementation Notes

This SD model implements concepts from Gopalakrishnan's MIT thesis "Modeling the Trajectory of Bitcoin using System Dynamics" (2022), enhanced with specific feedback loops and stocks identified through our DSA process.