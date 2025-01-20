# quantum shifter oracle
Qiskit code for d-qubit shifter oracle using:
  (d - 1) ancillas,
  r * (d - 2) recoverable |T> states,
  t * (d - 2) T gates, and
  m * (d - 2) measurements,
where (r, t, m) can be chosen to (1, 6, 0) or (0, 4, 1).

Controlled version of these oracle are also provided. Added control makes the above complexities scale with (d - 1) instead of (d - 2). Depths and total gate counts scale linearly with d in all cases.

Explanation of main functions:
  1. measurement_free_quantum_shifter(k, d) outputs a quantum circuit, on d qubits with an additional d - 2 clean ancilla qubits, that implements |x>|0> -> |x + k>|0>, where x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 2. The T gate count is 8 * (d - 2 - lsb), where lsb is the index of the least significant bit of k. Alternatively, when starting the ancillas in |T>, the T gate count is 6 * (d - 2 - lsb) and the |T> state is recovered.
  2. controlled_measurement_free_quantum_shifter(k, d) outputs a quantum circuit, on 1 + d qubits and with an additional d - 1 clean ancilla qubits, that implements |c>|x>|0> -> |c>|x + c*k>|0>, where c is the control bit, x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 1. The T gate count is 8 * (d - 1 - lsb), where lsb is the index of the least significant bit of k. Alternatively, when starting the ancillas in |T>, the T gate count is 6 * (d - 1 - lsb) and the |T> state is recovered.
  3. quantum_shifter_with_measurements(k, d) outputs a quantum circuit, on d qubits with an additional d - 2 clean ancilla qubits and d - 2 measurements, that implements |x>|0> -> |x + k>|0>, where x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 2. The T gate count is 4 * (d - 2 - lsb), where lsb is the index of the least significant bit of k.
  4. controlled_quantum_shifter_with_measurements(k, d) outputs a quantum circuit, on 1 + d qubits with an additional d - 1 clean ancilla qubits and d - 1 measurements, that implements |c>|x>|0> -> |c>|x + c*k>|0>, where c is the control bit, x is an arbitrary bit string for lenght n, and 0 is the all zero bitstring of lenght d - 1. The T gate count is 4 * (d - 1 - lsb), where lsb is the index of the least significant bit of k.

Written in Qiskit. Generalizes the incrementor of https://algassert.com/circuits/2015/06/12/Constructing-Large-Increment-Gates.html
