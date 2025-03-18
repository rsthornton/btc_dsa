# A Deep Systems Analysis of Bitcoin

This repository contains the paper "A Deep Systems Analysis of Bitcoin" along with computational simulations that support the analysis.

## Repository Structure

- `paper/`: Contains the main paper and related resources
  - `dsa_btc.md`: The paper in markdown format
  - `A_Deep_Systems_Analysis_of_Bitcoin.pdf`: PDF version of the paper
  - `README.md`: Overview of the paper
  
- `simulations/`: Contains computational models referenced in the paper
  - `btc_abm/`: Agent-Based Model implementation and documentation
  - `btc_sd/`: System Dynamics Model implementation and documentation
  - `README.md`: Overview of the simulation approaches

- `integration_plan.md`: Plan for integrating simulation insights into the paper
- `latex_integration_instructions.md`: Instructions for adding simulation references to LaTeX

## Abstract

This paper applies the Deep Systems Analysis (DSA) methodology to Bitcoin, providing a comprehensive, interdisciplinary framework for understanding Bitcoin as a complex adaptive system. By systematically decomposing Bitcoin into its constituent subsystems and mapping their interactions, we reveal the intricate mechanisms that enable its core functions while maintaining decentralization and security. The DSA approach bridges traditional disciplinary divides, allowing technical, economic, and social perspectives to be integrated within a single analytical framework.

## Computational Models

To support the theoretical analysis presented in this paper, two complementary computational models have been developed:

1. **Agent-Based Model (ABM)**: Implements a bottom-up approach, simulating individual agents (miners, users, nodes) and their interactions to observe emergent system behavior.

2. **System Dynamics (SD) Model**: Implements a top-down approach, modeling key stocks, flows, and feedback loops to simulate Bitcoin's macroscopic dynamics.

These models are available in the `simulations/` directory with detailed documentation.

## Running the Simulations

To explore the computational models:

1. Ensure you have Python 3.8+ and Jupyter Notebook installed
2. Install required packages: `pip install cadCAD pandas numpy matplotlib`
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