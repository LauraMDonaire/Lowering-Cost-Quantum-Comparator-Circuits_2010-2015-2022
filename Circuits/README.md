# Proposed comparator circuits

## Overview

This section of the repository showcases various quantum comparators and their optimized versions in terms of T-count and T-depth. For each circuit, you will find visual diagrams, small descriptions, and links to their implementations on the IBM Quantum Platform.
## Circuits 

### Circuit 1: Thapliyal et al. (2010)
- **Authors**: H. Thapliyal, N. Ranganathan and R. Ferreira
- **Information**: The 2-bit half-comparator presented in by Thapliyal et al. (2010) is made up of two R-Bcomps modules, two CNOT gates, and two TR gates (see **Figure 1**).
  In the [original implementation of Thapliyal's comparator](Thapliyal_original.png), it can be observed the gates that form each module R-Bcomp, which are two TR gates and one CNOT gate. The relevant outputs of this circuit are Z and Y, Y becomes 1 when the condition $x>y$ is satisfied, and Z becomes 1 when $x < y$. 

  <p align="center">
    <img src="https://github.com/LauraMDonaire/QuantumComparators/blob/main/Half-Comparators/Thapliyal%20et%20al.%202010/Thapliyals%20Quantum%20Half%20Comparator(n%3D2).png" alt="Thapliyal et al. proposed 2-bit reversible comparator" width="500"/>
</p>
<p align="center">
    <b>Figure 1: 2-bit Comparator proposed by Thapliyal et al. (2010)</b>
</p>

Upon reviewing the circuit, it’s evident that the large number of T-gates originates from the TR gate, which has a T-count of 9 and a T-depth of 6. To address this, a new comparator circuit is introduced with an [optimized TR gate](../Gates/TR_gate/TR_proposed.png). The replacement of these gates leads to the cancellation of some Pauli-X and CNOT gates, as they are Hermitian. As a result, the circuit is reduced to six TR gates, four Hadamard gates, and one CNOT gate. This optimization significantly lowers the T-count and T-depth. After simplifying the circuit, it now consists of:

- Six TR gates, where consecutive duplicate gates have been removed.
- Four Hadamard gates that initialize the qubits to be compared.
- One CNOT gate.

According to the circuit metrics, it has a total of 24 T-gates (six TR gates with four T-gates each). The T-depth is calculated based on parallel execution of two TR gates, resulting in a depth of 8. However, with auxiliary qubit initialization, the total T-depth is reduced to 5 (see **Figure 1.1**). 

  <p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Circuits/Thapliyal%20et%20al.%20comparator%20and%20optimised%20proposal/Proposed_optimised_1.png" alt="Proposed 2-bit reversible comparator" width="500"/>
</p>
<p align="center">
    <b>Figure 1.1: Proposed comparator based on Thapliyal et al.</b>
</p>

- **IBM Quantum Platform**: [View Circuit on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcIAKAnA9gBzQZxgEwAICB5DAFwEsoLdCBhNKDCFCMtFAgIwloIrAEAKgAsIGADYUAnhAkBaAMoAJAIIAlAKIAREABoQAR15QEIYkk0A5AIqrFAWQIAmAHQAGANwAdMAIDGEgCueDAE3kYwUlwAjK4BET5ghigwAOYEhgDaMQAsALpJ-qkZ-jkFSb4imVnOhVU1AMz1YNXZFb6puGQ1AKwtbVkAbC1dMD3ZAOwDNTHuM9kxMaMw3bN1SWMTOc1J2xu%2B27uHNR1g2yN7s-NXi8tJPCgoFDCc2fN6s-mf2XU-Wc1-gV-v1-iN-tN-gAOb41ACcsMWH1my3%2BMT%2Bs2OYAAHl8krjsgiHixnq8asjFojalTAacqaCauCapCajD-gi0RScqj1lSYlj-ASslyDmBBay%2BTdfOLKf9RTKshzri0FRjKUUhXMqUTpUK1cKVZquTC9ngMu8WmQzXiTr9LdbsibDg7FZblRqavqpWKjVSnT7PXzDcr2S1NQtqfj4RGtUlsIG4%2B7dYGIcGkXysY9SW8DWiqfrae16VSmVM-drJXyeYt9fyw%2BS0zkafXHY2lXdG1yBUK2SjG4WDR6O9D%2B0Gh9yK6bzYPndP7raAfbp-6rdOdec%2B%2BOB-OA8Po1uqd6FUty1GLUlBliezGd8fDy149lu9GR4mOweQY2T2jRVmXjmuWral-gHYE%2BhLKkWVbUNOSrPlayvBtxzrMFOwg8dSxnc4XSPIVMLrW5hiXTFG3w59skw71BkuXxHyIjDIJaP8yQtPM5WbIFi1Q1MRxgkM%2Bx-DMv31M4FS5UShTA89kyLQSpyQhczlXXlxyknJ5Uk%2B8zywugAA1eX%2BKi6TfLIJLpT9iSef8GzYlMmipNSGQoxjeJffi9xrISklgXgglSBsCHkAA%2BAgym9HzsD8sJKUCkKyh3CKosDWLQsjXxEv8p98hSsosQy6LTOy4LUrOfLwJyrJ%2Bm8mBfMyoiKposAyrLCrpmq2qCphCr-Wa10KvXXqtQq2N0pqyK6pPYaErGpLPOG0VBuaYasV8AB6VaCAAAX8NBgigMB42FPR3GO06TvOs7TpiPRrtum77ucPRGievRcj0Xp3r0IYvr0SZfr0KEAb0OFgdBkHwZuk65hu27bse9Ebvh%2BHnv5G63ryG6Ppib7sZunGcb%2BmJCcBmISZBmIQecE6qb0Gm6ep6nrucJnHucVnnucDmudpt7nF5-naY%2B5whe%2B5w-rF2nAecEHGhO2WnuuxpFcexpnsaN7Gg%2BxpvsaP7GkBxoQdyE7cmu3JHvN16Lee3I3tyD7cm%2B3I-tyQHchB3oTt6R7eme3o3t6D7em%2B3o-t6QHehBoYTqGa6hkeoZnqGN6hn6Xx9BAUJsGKChyAoNAwDMEAAF8gA).

### Circuit 2: Kalita et al. (2015)
- **Authors**: Kalita G, Saikia N
- **Information**: This [full 1-bit comparator](Kalita_original.png) was proposed by Kalita et al. in 2015 (see **Figure 2**).

<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Circuits/Kalita%20et%20al.%20comparator%20and%20optimised%20proposal/Kalita_original.png" alt="Kalita et al. (2015) proposed comparator" width="500"/>
</p>
<p align="center">
    <b>Figure 2: Comparator proposed by Kalita et al. (2015)</b>
</p>
  
Using the new version of the [GN gate proposed](../Gates/GN_gate/GN_proposed.png), a new optimised comparator circuit is proposed](see **Figure 2.1**). Regarding the calculation of the metrics of this circuit, the only gate that includes 
T-gates is the proposed GN gate, so the total T-count is 4, while the T-depth is 2.
<p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Circuits/Kalita%20et%20al.%20comparator%20and%20optimised%20proposal/Proposed_optimised_3.png" alt="Proposed comparator based on Kalita et al. (2015)" width="500"/>
</p>
<p align="center">
    <b>Figure 2.1: Proposed comparator based on Kalita et al. (2015)</b>
</p>
  
- **IBM Quantum Platform**: [View Circuit (n=8) on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcIAKAnA9gBzQZxgEwAICB5DAFwEsoLdCBhNKDCFCMtFAgIwloIrAEA0hAA2FMhAC0AZQASAQQBKAUQAiIADQgAjrygIQxJCoByARQUyAsgQBMAOgAMAbgA6YAQGNRAVzwwBG66MOJcAIwO3sHuYB46KDAA5gQ6ANoALAC6sV6JKV6ZOR4eABapaXbFYIm4ZBUAzNX16VWxPCgoFDCc6U5ZmhXhAxVVg%2BlNsQAeFf25M30jrdVeC2nD45Ura2ND26NLaXMeZHgpi7Gn5%2BvNB-MHm8dga0%2BrD3v36Ruz1eXLsdg7h43stNpMPB0uj0fptvqDGvtFps2h4XtVId1ekdDnCtmCcgQAPSEggAAQwpV4MDUNAA1h5iWSvGg-FAwICjponJpwpo7JoGpoMpoAKyaABsmgA7JoAByaACcPO54RVKt54X5mp5gvCuuF4TF4Ul4Rl4VlWQ8sF4vkSPwIUgAfARCk9rdhbYEvlkHc7CsNYu7PQdfS6toGYDa7RMfU6w%2BC4mBGaTmaz2QROSq%2BQKhaKJdK5YX5UrVcqeRqNVr9TyjSazfLwkq7Ny7MMPFoQAFsHkKOQKGgwIYQABfIA).

### Circuit 3: Maity (2022) 
- **Authors**: H. Maity
- **Information**: The [full 2-qubit comparator](Maity_original.png) proposed by H. Maity uses several Peres gates (see **Figure 3**).  The relevant outputs of this circuit are X, Y and Z, X becomes 1 when the condition $x < y$ is met, Y becomes 1 when $x = y$ and Z becomes 1 when $x > y$.
  <p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Circuits/Maity%E2%80%99s%20comparator%20and%20optimised%20proposal/Maity_original.png" alt="Maity proposed comparator" width="500"/>
</p>
<p align="center">
    <b>Figure 3: Comparator proposed by Maity (2022).</b>
</p>

Using the new version of the [Peres gate proposed](../Gates/Peres_gate/Peres_proposed.png), a new optimised comparator circuit is proposed (see **Figure 3.1**). In terms of T-count and T-depth, each Peres gate contributes 4 T-gates, resulting in a total of 16 T-gates for the circuit (4 gates × 4 instances). The T-depth initially is 8, as each gate is executed in two stages (4 × 2). However, since the auxiliary qubit for the Temporary logical-AND gate is initialized only once, the actual T-depth for the entire circuit is reduced to 4.

  <p align="center">
    <img src="https://github.com/LauraMDonaire/Lowering-Cost-Quantum-Comparator-Circuits_2010-2015-2022/blob/main/Circuits/Maity%E2%80%99s%20comparator%20and%20optimised%20proposal/Maity_original.png" alt="Maity proposed comparator" width="500"/>
</p>
<p align="center">
    <b>Figure 3.1: Proposed comprator based on Maity (2022).</b>
</p>


- **IBM Quantum Platform**: [View Circuit on IBM Quantum Platform](https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcIAKAnA9gBzQZxgEwAICB5DAFwEsoLdCBhNKDCFCMtFAgIwloIrAEAshApkAngFoAygAkAggCUAogBEQAGhABHXlAQhiSZQDkAivOlCCAJgB0ABgDcAHTACAxgBsArnhgELjowXhRcAIx2nkGuYNooMADmBNoA2uE2ALqxHgnJHukAzNlubgAWKalZsRVpxbEJuGSVACwlYLWpAOztjTDNaQAc7Z0AnL0wTZXhDhNTaeHh7QNVy5X1bis9sSvjsTwoKBQwnGmzGtOZF2lZ16nFd213AKxXlQBsb2k9d8N343cZl90ktYgAPSqzcGVV7QhagtwHI4nSHApZ3W7rYFPGHAz53H6VP6VAHTc7TBFgDwQs7A6puam4gntRkLOksmmpfGVbYMzmYtk5TmEtKfIWVAWpKF8nnA2GbPDJWk7RWXHYS5aqtLysBkLVctbfDkau7SqnCuXGm5oq3dPEjDU1WWxbCOtyuo37FjI05Sm0Y4EPVqWu7co2-YGkhbk%2BG2mPpW2SjbmpkfW0i1LDL2HY6%2B%2BPok1Yx4htPMiP-NH5ymshMV8WiyO2qMG%2BupZuUvVKhMqrtizYkps21vNvsdAcu8eI7251GA9l3INpHHa%2B1lomNwFV20FhvDyvtJEz2lzgML7ElhtroYbslo6ucnf3bdb1vEuq2xeZj9DhVdrO-tV%2B3fVtP3vIt1ydYD3SxVtH3-FN32LbMfVnS5T3ApcLwNK8vwrTc72-QFKUPFFjzQwtEODF5V1lcsB3woj2lgXgfASVECEkAA%2BAgCjNZjsFYgI2Q47iCkpfjBI1ESeNWWIJLY99pIKZN5KE1I2iU9SmJgFiFNSV5NJ1VS0003kwGMo1NL2NwLK-TT4Ns8ZNMWbTdLUoFnPpMA3AAeh8ggAAEPDQXwoDAV0pQ0Bwopi6K4pi8INES5KNBsDRCnSzKWg0Z4co0d58o0Loio0QZSo0UYKqqyqaqS6KZiS5LkrSjIkoy8J2uy8Jcu6pKep6grwmK8IyvCSqbGimxEqm1LprSmwMpsbKbFymwCpsYqNtSsqbHGyrCmiwpEsKNKTvSjLCgu7LClywoCsKYrCjKwpKpaaKWkSlo0paDKWmylpcpaAqWmKloypaSrnmi55EueNLnmKNxNBAfxsFyChyAoNAwAMEAAF8gA).

## Metrics
The metrics for these circuits can be found in the `README.md` file of this repository.

## How to Use

Each circuit in this directory includes an analysis of the gates used, a visual diagram, and a link to its implementation on the IBM Quantum Platform. You can explore each circuit individually by following the links provided.
