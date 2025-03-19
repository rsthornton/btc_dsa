# A Deep Systems Analysis of Bitcoin

This repository contains the paper "A Deep Systems Analysis of Bitcoin" along with computational simulations that support the analysis.

## Repository Structure

- `working_paper/`: Contains the final paper
  - `A_Deep_Systems_Analysis_of_Bitcoin.pdf`: PDF version of the paper
  
- `simulations/`: Contains computational models referenced in the paper
  - `btc_abm/`: Agent-Based Model implementation and documentation
  - `btc_sd/`: System Dynamics Model implementation and documentation
  - `README.md`: Overview of the simulation approaches
  
- `model/`: Contains system model data
  - `btc.json`: JSON representation of the Bitcoin system model


## Abstract

This paper applies the Deep Systems Analysis (DSA) methodology to Bitcoin, providing a comprehensive, interdisciplinary framework for understanding Bitcoin as a complex adaptive system. By systematically decomposing Bitcoin into its constituent subsystems and mapping their interactions, we reveal the intricate mechanisms that enable its core functions while maintaining decentralization and security. The DSA approach bridges traditional disciplinary divides, allowing technical, economic, and social perspectives to be integrated within a single analytical framework.

## Computational Models

To support the theoretical analysis presented in this paper, two complementary computational models have been developed:

1. **Agent-Based Model (ABM)**: Implements a bottom-up approach, simulating individual agents (miners, users, nodes) and their interactions to observe emergent system behavior.

2. **System Dynamics (SD) Model**: Implements a top-down approach, modeling key stocks, flows, and feedback loops to simulate Bitcoin's macroscopic dynamics.

These models are available in the `simulations/` directory with detailed documentation.

## Running the Simulations

### Option 1: Run in Google Colab (Recommended)

The easiest way to explore the simulations is through Google Colab, which requires no local setup:

1. **Agent-Based Model (ABM)**: 
   - [Open ABM Notebook in Colab](https://colab.research.google.com/drive/1XNYkyDZq-Ey_MToYBOqJ_YP6UesKdtyj)
   
2. **System Dynamics Model (SD)**:
   - [Open SD Notebook in Colab](https://colab.research.google.com/drive/1U7PfPnGQyVTyqXG3mX_77ZJLkP3DWsy3)

Simply click the links above and select "Run all" from the Runtime menu to execute the simulations.

### Option 2: Run Locally

If you prefer to run the simulations on your local machine:

1. Ensure you have Python 3.8+ and Jupyter Notebook installed
2. Install required packages: `pip install -r simulations/requirements.txt`
3. Navigate to either `simulations/btc_abm/` or `simulations/btc_sd/`
4. Open the respective Jupyter notebook
5. Run the simulations and explore the results

## Citation

If you use this analysis or the accompanying simulations in your research, please cite:

```
Thornton, S. (2025). A Deep Systems Analysis of Bitcoin. Working Paper.
```

## License

This work is licensed under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
