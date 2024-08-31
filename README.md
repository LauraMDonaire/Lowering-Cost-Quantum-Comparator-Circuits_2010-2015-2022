# Lowering the Cost of Quantum Comparator Circuits

## Summary

This research introduces an innovative approach to reducing the computational cost of quantum comparator circuits, which are fundamental components in a wide range of quantum algorithms. Our study focuses on optimizing comparator circuits using only gates from the Clifford+T set, with a particular emphasis on minimizing the use of T-gates, which are resource-intensive in terms of computational cost and execution time.

## Objectives

- **Reduction of T-gate Usage**: Minimize the number of T-gates in the circuits to improve efficiency and robustness against noise.
- **Quantum Circuit Optimization**: Propose new implementations of quantum comparators that are more efficient and suitable for the Noisy Intermediate-Scale Quantum (NISQ) computing era.
- **Facilitate Fault Tolerance**: Use designs that allow the integration of error-correcting codes, enhancing the fault tolerance of the circuits.

## Methodology

1. **Analysis of Existing Circuits**: We analyzed three comparator circuit designs from existing literature, focusing on the use of TR, Peres, and GN gates.
2. **Proposed Optimization**: New versions of these comparators were proposed using optimized gates to reduce the number of T-gates required.
3. **Implementation**: The new proposals were implemented on the IBM Quantum platform, demonstrating significant improvements in terms of T-count and T-depth.

## Results

- **Optimized Comparators**: The proposed comparators reduced the number of T-gates by half compared to the original designs.
- **Improvement in T-depth**: The optimizations also resulted in a significant decrease in T-depth, suggesting reduced execution time for the circuits.
- **Practical Implementation**: The optimized circuits are compatible with current quantum platforms and are designed to facilitate error correction.

## Publication

This work has been published in the *Journal of Supercomputing*:

- **Title**: Lowering the Cost of Quantum Comparator Circuits
- **Authors**: Laura M. Donaire, Gloria Ortega, Ester M. Garzón, Francisco Orts
- **Published Online**: March 13, 2024
- **DOI**: [10.1007/s11227-024-05959-4](https://doi.org/10.1007/s11227-024-05959-4)

## How to Cite

If you find this work useful and wish to cite it, please use the following reference:

Donaire, L. M., Ortega, G., Garzón, E. M., & Orts, F. (2024). Lowering the cost of quantum comparator circuits. Journal of Supercomputing, 80, 13900–13917. https://doi.org/10.1007/s11227-024-05959-4


## Future Work

- **Scaling the Circuits**: Expand the proposed comparators to handle a greater number of digits, enhancing their applicability in practical quantum computing scenarios.
- **Integration of New Methods**: Explore the integration of new optimization techniques and error correction methods to further improve circuit efficiency.

## Contact

For more information, suggestions, or collaboration, you can contact:

- **Laura M. Donaire**: [laura.donaire@ual.es](mailto:laura.donaire@ual.es)
