# quantum shifter oracle
Qiskit code for d-qubit shifter circuits using at most 4*(d-2) T gates.

quantum_shifter(k, d) outputs a quantum circuit, on d qubits with an additional d - 2 clean ancilla qubits and d - 2 measurements, that implements |x>|0> -> |x + k>|0>, where x is a bit string for lenght n. The T gate count = 4 * (d - 2 - lsb), where lsb is the index of the least significant bit of k, Depth and total gate count scale similarly.

Written in Qiskit. Generalizes the incrementor of https://algassert.com/circuits/2015/06/12/Constructing-Large-Increment-Gates.html
