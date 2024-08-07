# quantum shifter oracle
Qiskit code for d-qubit shifter circuits using at most 4*(d-2) T gates.

measurement_free_quantum_shifter(k, d) outputs a quantum circuit, on d qubits with an additional d - 2 clean ancilla qubits, that implements |x>|0> -> |x + k>|0>, where x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 2. The Toffoli gate count = 2 * (d - 2 - lsb), where lsb is the index of the least significant bit of k. The Toffolis can be implemented so that each pair the only costs one |T> state, which is recovered at the end, and six T gates.

controlled_measurement_free_quantum_shifter(k, d) outputs a quantum circuit, on 1 + d qubits and with an additional d - 1 clean ancilla qubits, that implements |c>|x>|0> -> |c>|x + c*k>|0>, where c is the control bit, x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 1. The Toffoli gate count = 2 * (d - 2 - lsb), where lsb is the index of the least significant bit of k. The Toffolis can be implemented so that each pair the only costs one |T> state, which is recovered at the end, and six T gates.

quantum_shifter_with_measurements(k, d) outputs a quantum circuit, on d qubits with an additional d - 2 clean ancilla qubits and d - 2 measurements, that implements |x>|0> -> |x + k>|0>, where x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 2. The T gate count = 4 * (d - 2 - lsb), where lsb is the index of the least significant bit of k.

(controlled_quantum_shifter_with_measurements(k, d) to come soon...)

Depths and total gate counts scale similarly in both cases.

Written in Qiskit. Generalizes the incrementor of https://algassert.com/circuits/2015/06/12/Constructing-Large-Increment-Gates.html
