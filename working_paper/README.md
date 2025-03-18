# A Deep Systems Analysis of Bitcoin

## Paper Overview

This paper applies the Deep Systems Analysis (DSA) methodology to Bitcoin, providing a comprehensive, interdisciplinary framework for understanding Bitcoin as a complex adaptive system. It bridges technical, economic, and social perspectives while maintaining analytical rigor.

## Repository Structure

- `paper/dsa_btc.md`: The main paper in markdown format
- `simulations/`: Computational models referenced in the paper
  - `btc_abm/`: Agent-Based Model implementation and documentation
  - `btc_sd/`: System Dynamics Model implementation and documentation

## Computational Models

To support the theoretical analysis presented in this paper, two complementary computational models have been developed:

1. **Agent-Based Model (ABM)**: Implements the bottom-up approach described in Section 3.1, simulating individual agents (miners, users, nodes) and their interactions to observe emergent system behavior.

2. **System Dynamics (SD) Model**: Implements the top-down approach described in Section 3.2, modeling key stocks, flows, and feedback loops to simulate Bitcoin's macroscopic dynamics.

These models are available in the `simulations/` directory with detailed documentation.

## Running the Simulations

To explore the computational models:

1. Navigate to the `simulations/` directory
2. Follow the setup instructions in the README.md
3. Open either the ABM or SD notebook in Jupyter
4. Run the simulations and explore the results

## Citation

If you use this analysis or the accompanying simulations in your research, please cite:

```
Thornton, S. (2025). A Deep Systems Analysis of Bitcoin. Working Paper.
```

## License

This work is licensed under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).