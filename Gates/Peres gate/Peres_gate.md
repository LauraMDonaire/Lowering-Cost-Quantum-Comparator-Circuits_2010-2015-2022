The Peres gate, given three qubits $A, B$, and $C$, returns $A, B \oplus A$, and $C \oplus AB$. The most standard implementation requires one CNOT gate, two Controlled-V gates, and one Controlled-V$^\dagger$ gate[1]. However, it is important to note that this implementation will be optimised (see [new version of the Peres gate](Peres_proposed.png)). 

[1] Chanderkanta Chen N, Kaushik BK, Kumar S (2019) Implementation of reversible peres gate using electro-optic effect inside lithium-niobate based Mach-Zehnder interferometers. Opt Laser Technol 117:28–37
