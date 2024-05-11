The TR gate, presented in [1], given three qubits $A, B$, and $C$, returns $A, A \oplus B$, and $A\bar{B} \oplus C$. An optimised version was proposed in [2] and can be seen in file TR_orginal.png. This optimised version, also working with three qubits $A, B$, and $C$, produces outputs $B, A \oplus C$, and $A\bar{B} \oplus C$. However, it is important to note that in [3], a diferent implementation of the TR gate is used. This version consists of two Controlled-V gates, one Controlled-V† gate, and one CNOT gate, and it is  this particular version of the TR gate that we propose optimising to reduce it cost in terms of T-gates. 

[1] Thapliyal H, Ranganathan N (2013) Design of efcient reversible logic-based binary and BCD 
adder circuits. ACM J Emerg Technol Comput Syst 9(3):1–31

[2] Li HS, Fan P, Xia H, Peng H, Long G (2020) Efcient quantum arithmetic operation circuits for 
quantum image processing. Sci China Phys Mech Astron 63:1–13

[3] Thapliyal H, Ranganathan N, Ferreira R (2010) Design of a comparator tree based on reversible 
logic. In: 2010 10th IEEE Conference on Nanotechnology, pp 1113–1116