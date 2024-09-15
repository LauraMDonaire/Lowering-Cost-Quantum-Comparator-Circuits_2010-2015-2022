# Lowering the Cost of Quantum Comparator Circuits

## Publication

This work has been published in the *Journal of Supercomputing*:

- **Title**: Lowering the Cost of Quantum Comparator Circuits
- **Authors**: Laura M. Donaire, Gloria Ortega, Ester M. Garzón, Francisco Orts
- **Published Online**: March 13, 2024
- **DOI**: [10.1007/s11227-024-05959-4](https://doi.org/10.1007/s11227-024-05959-4)
  
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

The proposed optimizations have achieved significant advancements in quantum circuit design. First, the optimized comparators reduce the number of T-gates by half compared to the original designs and significantly decrease the T-depth, which suggests a reduction in circuit execution time. Additionally, these optimized circuits are compatible with current quantum platforms and are designed to facilitate error correction.

The detailed analysis in **Table 1** compares various quantum circuits with the proposed optimized circuits, showing the following key results:

- **Optimized Proposed Circuit 1** demonstrates a notable reduction in **T-count** (from 54 to 24) and **T-depth** (from 24 to 5) compared to the circuit by Thapliyal et al.
- **Optimized Proposed Circuit 2** and **Optimized Proposed Circuit 3** also show significant improvements in both metrics compared to the circuits by Maity and Kalita et al., respectively.
- Although the optimized circuits require a slightly higher number of ancillary qubits, this small increase is offset by the significant improvement in computational efficiency.
- The optimizations are achieved exclusively using Clifford+T gates, highlighting the focus on precision and efficiency in quantum computations.

These results underscore that the optimizations introduced for the TR, Peres, and GN gates have had a highly positive impact on the overall performance of the circuits, emphasizing their potential for practical applications in quantum circuit design.

### Table 1: Comparison of circuits in terms of T-count, T-depth, ancillary qubits, comparator type, and number of digits compared.

| Circuit                             | T-count | T-depth | Anc. Qubits | Type | No. Digits |
|-------------------------------------|---------|---------|-------------|------|------------|
| Thapliyal et al. [[1]](#1)                   | 54      | 24      | 4           | Half - Comparator | 2          |
| **Optimized Proposed Circuit 1**    | **24**  | **5**   | **10**      | Half - Comparator           | 2 |
| Maity  [[2]](#2)                              | 36      | 16      | 4           | Full Comparator | 2          |
| **Optimized Proposed Circuit 2**    | **16**  | **4**   | **8**       | Full Comparator | 2          |
| Kalita et al. [[3]](#3)                   | 9       | 6       | 2           | Full Comparator | 1          |
| **Optimized Proposed Circuit 3**    | **4**   | **2**   | **2**       | Full Comparator | 1          |

## Future Work

- **Scaling the Circuits**: Expand the proposed comparators to handle a greater number of digits, enhancing their applicability in practical quantum computing scenarios.
- **Integration of New Methods**: Explore the integration of new optimization techniques and error correction methods to further improve circuit efficiency.

## References 

- <a name="1">[1]</a> Thapliyal H, Ranganathan N, Ferreira R (2010) Design of a comparator tree based on reversible logic. In: 2010 10th IEEE Conference on Nanotechnology, pp 1113–1116. [DOI:10.1109/NANO.2010.5697872](https://doi.org/10.1109/NANO.2010.5697872)
- <a name="2">[2]</a> Maity H (2022) Design and implementation of a two-qubit quantum comparator circuit (Q-CC). J Comput Electron 21:530–534. [DOI:10.1007/s10825-022-01858-0](https://doi.org/10.1007/s10825-022-01858-0)
- <a name="3">[3]</a> Kalita G, Saikia N (2015) Reversible comparator circuit using a new reversible gate. In: Proceedings of the Sixth International Conference on Computer and Communication Technology 2015. [DOI:10.1145/2818567.2818685](https://doi.org/10.1145/2818567.2818685)
  

## How to Cite

If you find this work useful and wish to cite it, please use the following reference:

Donaire, L. M., Ortega, G., Garzón, E. M., & Orts, F. (2024). Lowering the cost of quantum comparator circuits. Journal of Supercomputing, 80, 13900–13917. https://doi.org/10.1007/s11227-024-05959-4

## Contact

For more information, suggestions, or collaboration, you can contact:

- **Laura M. Donaire** (TIC-146 Supercomputación-Algoritmos [SAL], University of Almería): [laura.donaire@ual.es](mailto:laura.donaire@ual.es)

