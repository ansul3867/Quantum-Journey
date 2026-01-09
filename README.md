# Quantum-Journey: Computational Implementations of Quantum Protocols

![Status](https://img.shields.io/badge/Status-Active_Research-blue)
![Language](https://img.shields.io/badge/Language-Python_%7C_Qiskit-green)
![Focus](https://img.shields.io/badge/Focus-Quantum_Algorithms-purple)

## 📌 Project Overview
This repository documents my rigorous implementation of quantum algorithms and protocols, bridging the gap between the theoretical formalism of **Nielsen & Chuang** and practical execution using **IBM Qiskit**.

The primary objective is to verify fundamental quantum mechanics postulates (Superposition, Entanglement, Measurement) and implement communication protocols (Teleportation, Superdense Coding) on both simulators and IBM Quantum hardware.

**Current Focus:** *Quantum Computation and Quantum Information* (Nielsen & Chuang), Chapter 2 & 4.

## 🧮 Theoretical Foundations
The codebase is structured around the mathematical verification of quantum states. Key theoretical concepts implemented include:

* **State Space:** Linear Algebra in Hilbert Space ($\mathcal{H}$).
* **Superposition:** $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ where $|\alpha|^2 + |\beta|^2 = 1$.
* **Entanglement:** Generation of Bell States, specifically $|\Phi^+\rangle = \frac{|00\rangle + |11\rangle}{\sqrt{2}}$.
* **Unitary Evolution:** Implementation of reversible gates ($U^\dagger U = I$).

## 🚀 Repository Structure & Roadmap

### Phase 1: Fundamentals (Linear Algebra & Single Qubits)
- [x] **Linear Algebra Verification:** Python scripts for Inner Products, Norms, and Tensor Products.
- [ ] **Single Qubit Gates:** Implementation of Pauli-X, Y, Z, and Hadamard gates.
- [ ] **Bloch Sphere Visualization:** Mapping state vectors to spherical coordinates.

### Phase 2: Entanglement & Protocols (The "Teleportation" Project)
- [ ] **Bell State Circuit:** Creating and measuring entanglement.
- [ ] **Quantum Teleportation:**
    - Implementation of the 3-qubit protocol.
    - Verification of state transfer fidelity.
- [ ] **Superdense Coding:** Transmitting 2 classical bits using 1 qubit.
- [ ] **No-Cloning Theorem:** Computational verification that $|\psi\rangle \to |\psi\rangle|\psi\rangle$ is impossible for arbitrary states.

### Phase 3: Algorithms (Future Scope)
- [ ] **Deutsch-Jozsa Algorithm:** Demonstrating exponential speedup over classical oracles.
- [ ] **Variational Quantum Eigensolver (VQE):** Preliminary exploration for Quantum Chemistry (RU-A Interest).

## 🛠️ Technical Stack
* **Language:** Python 3.10+
* **Quantum SDK:** Qiskit 1.0
* **Visualization:** NumPY, Seaborn, Matplotlib, Qiskit Visualization Module
* **Environment:** Jupyter Notebooks

## 📉 Example: Bell State Generation
*A snippet of the logic used in `src/entanglement.py`*

```python
from qiskit import QuantumCircuit
# Create a Quantum Circuit with 2 qubits
qc = QuantumCircuit(2)

# Apply H-gate to the first qubit: |00> -> (|00> + |10>) / sqrt(2)
qc.h(0)

# Apply CNOT gate: (|00> + |11>) / sqrt(2)
qc.cx(0, 1)
