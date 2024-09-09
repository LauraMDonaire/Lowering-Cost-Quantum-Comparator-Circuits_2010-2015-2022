# Optimized Proposed Quantum Gates

## Overview
This section presents the optimized versions of quantum gates, including the GN, Peres, and TR gates, aimed at reducing the quantum cost while maintaining functional correctness. These optimizations focus on reducing the number of T-gates used, enhancing the gates' performance in practical quantum circuits. Each gate is explained with its proposed optimized implementation, and visual aids are provided for clarity.
## Gates 
Quantum gates are fundamental for quantum computing, performing unitary operations on qubits. Some gates, like those in the Clifford+T set, approximate the vast range of quantum operations, crucial for fault-tolerant quantum circuits. The T-gate, while essential for universality, incurs a higher computational cost compared to basic gates like Hadamard or CNOT. This section focuses on designing optimized quantum gates using only Clifford+T gates, balancing efficiency and error correction to enhance performance on modern quantum platforms.

### GN Gate
- **Information**: The GN gate was proposed in [1] and is made up of two Controlled-V gates, one Controlled-V $$^\dagger$$ gate, and one CNOT gate (see **Figure 1**). This gate returns $$A \oplus C$$, $$\overline{A}C \oplus B$$, and $$C$$.

<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/GN_gate/GN_Original.png" alt="Original GN gate implementation" width="500"/>
</p>
<p align="center">
    <b>Figure 1: Original implementation of the GN gate.</b>
</p>

  This implementation have been optimised and now it uses a Temporary logical-AND gate, two CNOT gates, and two Pauli-X gates. can be seen in **Figure 1.1** 
  In this optimized version: 
  - The first Pauli-X gate negates qubit $A$ before the Temporary logical-AND gate performs the multiplication of the qubits.
  - Then, the Temporary logical-AND gate carries out the multiplication of $\bar{A}C$ and stores the result in the auxiliary qubit.
  - A CNOT gate acts on the auxiliary qubit, meaning it operates on $\bar{A}C$, performing an ⊕ operation with qubit $B$, resulting in $\bar{A}C ⊕ B$.
  - The second Pauli-X gate restores qubit A to its original state, allowing the CNOT gate to perform the $A ⊕ C$ operation.

<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/GN_gate/GN_proposed.png" alt="Proposed GN gate implementation" width="500"/>
</p>
<p align="center">
    <b>Figure 1.1: Proposed implementation of the GN gate.</b>
</p>

- **IBM Quantum Platform**: [View optimized version of the GN gate on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcIDyAHALgSyhgXjAJgAQAKATgPYrkDOBhA4gHIMRoyEC0hAygBICCAJQCiAERAAaEAEcI1KAmTFhjAIr9uAWUIAmAHQAGANwAdMBjABjADYBXfOxMyY1jACMAjHouWnpsGbSpDAA5oTSANoALAC6-pbBYZbRcWZmABbhEQapYJmRHrn5ETpFWQDMuWhZpf5uEKSkGDCkWTkSWYUdkaXdEZX%2BAB5tuZbDke01o%2BMRXVPxM72d01N9Of5o%2BGETVVvLG-NmY6sjCycFZT251IdgM%2BtHizF9A48jfYX%2BZgD034QAApZyHYoGAbtkJAZIdCPBIdBJyhIohIAKwSABsEgA7BIABx4gkATgkHihHlhHnhHkR1JJsTMkhADmoCQw6Aw5DAihAAF8gA)

### Peres Gate
- **Information**: The Peres gate, given three qubits $A, B$, and $C$, returns $A, B \oplus A$, and $C \oplus AB$. The most standard implementation requires one CNOT gate, two Controlled-V gates, and one Controlled-V $$^\dagger$$ gate (see **Figure 2**) [2].
<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/Peres_gate/Peres_proposed.png" alt="Proposed implemenation of the Peres gate" width="500"/>
</p>
<p align="center">
    <b>Figure 2: Most standart implementation of the Peres Gate</b>
</p>
However, this implementation have been optimised (see **Figure 2.1**). In this version, it can be observed that:
- The temporary logical-AND gate performs the multiplication operation AB and stores the result in the ancillary qubit.
- A CNOT gate acts on the ancillary qubit, which means it operates on AB, performing an ⊕ operation with qubit C, resulting in AB ⊕ C.
- The second CNOT gate performs the A ⊕ B operation.
<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/Peres_gate/Peres_proposed.png" alt="Proposed implemenation of the Peres gate" width="500"/>
</p>
<p align="center">
    <b>Figure 2.1: Proposed implementation of the Peres Gate</b>
</p>
  
- **IBM Quantum Platform**: [View optimized version of the Peres gate on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcIDyAHALgSyhgXjAJgAQAKATgPYrkDOBJMpM1hA4hGjIQLSEDKAEgEEASgFEAIiAA0IAI4RqUBMmKiAcgEVBvALKEATADoADAG4AOmAxgAxgBsArvk7m5MOxgBGARkPWbrhZglrKMAOaEsgDaACwAukE24YQ2sQmWlgAWkVHG6WDZ0d75hVH6JTkAzPloOeVBnhCkpBgMOXlSOcWd0eU9UdWJAB7tcf31ljYjRWN1%2BVNz-cXDi6NBaPgR0Xnrm101cyu9s9vz02UnUctZh5bMx0e5l9e2531V%2BZYA9F%2BEAAI2ciOKBgZi5KTGCFQ7xSfRSSpSGJSACsUgAbFIAOxYnEADikAE4pN5Id4Yd44RS4pZpCBnNQkhh0BhyGBlCAAL5AA)
### TR Gate
- **Information**: The TR gate, presented in [3], given three qubits $A, B$, and $C$, returns $A, A \oplus B$, and $A\bar{B} \oplus C$. An optimised version was proposed in [4] and can be seen in **Figure 3**. This optimised version, also working with three qubits $A, B$, and $C$, produces outputs $B, A \oplus C$, and $A\bar{B} \oplus C$. 

<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/TR_gate/TR_original.png" alt="Original version of the TR gate" width="500"/>
</p>
<p align="center">
    <b>Figure 3: Proposed version of the TR gate by Li et al. [4]</b>
</p>

However, it is important to note that in [5], a diferent implementation of the TR gate is used. This version consists of two Controlled-V gates, one Controlled-V† gate, and one CNOT gate, and it is  this particular version of the TR gate that we propose optimising to reduce it cost in terms of T-gates (see **Figure 3.1**). 
This approach utilizes a Temporary logical-AND gate in combination with two Pauli-X and two CNOT gates. Here's how it functions:

- The first Pauli-X gate negates qubit $B$ before the Temporary logical-AND gate performs multiplication.
- The AND gate multiplies qubits $A$ and $$\bar{B}$$, storing the result in an ancillary qubit.
- A CNOT gate then applies an exclusive ⊕ operation between the ancillary qubit $$A\bar{B}$$ and qubit C, resulting in $A\bar{B} \oplus C$.
- A second Pauli-X gate restores qubit $B$ to its non-negated state so that the second CNOT gate can perform the $A \oplus B$ operation.
  
  <p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Gates/TR_gate/TR_proposed.png" alt="Proposed version of the TR gate" width="500"/>
</p>
<p align="center">
    <b>Figure 3.1: Proposed optimized version of the TR gate.</b>
</p>


- **IBM Quantum Platform**: [View optimized version of the TR gate on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcICqYAuBLVAbGATABAMboBOhArpiADQgCOEAzlAiAPIAKAogHICKAQQDKAWXwAmAHQAGANwAdMOjCEs5XDHzz6MLOgBGARknLC2hWEV0SMAOb46AbQAsAXQuEb9wi-eLFABYOjtJ%2BYEFOhmERjuLRwQDMYajBcRb6ECQk6DAkwaHUwVGFTnEljkkWAB5FYYQ1TgWpdQ2Oxc0erWW1nc3loRaouPaNycM9iimlLX35M9PlURYxaYqMHYqtS4r1s06VO61NkWGKAPRn%2BAAChAD2alBg6yHU0q-vhtTi1AnUztQAVmoADZqAB2agADihMIAnNRDG9DJ9DN9DL90Qi3IoaCANIxPOgAA4YW5gVggAC%2BQA)
## Metrics
The T-count for all the proposed gates is 4, with a consistent T-depth of 2 for each gate. This consistency is due to the fact that the Temporary logical-AND gate is the only contributor to the T-gate cost. Additionally, it’s important to note that the number of auxiliary qubits has increased compared to the original versions.
## References 

- [1] Kalita G, Saikia N (2015) Reversible comparator circuit using a new reversible gate. In: Proceedings of the Sixth International Conference on Computer and Communication Technology 2015
- [2] Chanderkanta Chen N, Kaushik BK, Kumar S (2019) Implementation of reversible peres gate using electro-optic effect inside lithium-niobate based Mach-Zehnder interferometers. Opt Laser Technol 117:28–37
- [3] Thapliyal H, Ranganathan N (2013) Design of efcient reversible logic-based binary and BCD adder circuits. ACM J Emerg Technol Comput Syst 9(3):1–31
- [4] Li HS, Fan P, Xia H, Peng H, Long G (2020) Efcient quantum arithmetic operation circuits for quantum image processing. Sci China Phys Mech Astron 63:1–13
- [5] Thapliyal H, Ranganathan N, Ferreira R (2010) Design of a comparator tree based on reversible logic. In: 2010 10th IEEE Conference on Nanotechnology, pp 1113–1116

