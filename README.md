# quantum-shifter
Qiskit code for d-qubit shifter circuits using at most 4*(d-2) T gate.

quantum_shifter(k, d) outputs a quantum oracle on d qubits with an additional (d - 2) ancilla qubits and (d - 2) classical bits, which implements |x>|0> -> |x + k>|0>, where x is a bit string for lenght n. The T gate count is 4 * (d - 2 - lsb), where lsb is the index of the least significant bit of k. Depth and total gate count scales similarly.

Generalizes the incrementor of https://algassert.com/circuits/2015/06/12/Constructing-Large-Increment-Gates.html
