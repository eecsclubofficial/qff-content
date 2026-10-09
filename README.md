# Qiskit Fall Fest 2026 — IISER Bhopal

Learning resources and Jupyter notebooks used during **The IISER Bhopal's First Ever IBM Quantum Qiskit Fall Fest 2026**, co-organised by **EECS Club × Physics Club**.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eecsclubofficial/qff-content)

---

## About the Event

This repository contains all notebooks, tutorials, and workshop materials prepared for the Qiskit Fall Fest 2026 held at IISER Bhopal. The event introduced quantum computing concepts using Qiskit (IBM's open-source quantum SDK) through hands-on sessions ranging from fundamentals to advanced algorithms.

The notebooks are designed to run in **Google Colab** (no local setup needed) and work with **Qiskit 2.x**.

---

## Repository Contents

### Core Workshop Notebooks

| Notebook | Description |
|----------|-------------|
| **[Essentials.ipynb](Essentials.ipynb)** | **Recommended starting point.** Covers most Qiskit APIs used during the fest: qubits, Bloch sphere, gates, measurement, primitives (Sampler/Estimator), circuits, entanglement, interference, noise, and running on IBM Quantum hardware. Includes interactive exercises with hidden solutions. |
| **[Qiskit_Fall_Fest_QFT_QPE.ipynb](Qiskit_Fall_Fest_QFT_QPE.ipynb)** | Follow-on to Essentials. Covers Quantum Fourier Transform (QFT) and Quantum Phase Estimation (QPE): discrete Fourier transform, Fourier basis as a binary clock, building QFT circuits, inverse QFT, period finding, phase kickback, phase estimation, precision analysis, library versions, and factoring 15. |

### SQD (Sample-based Quantum Diagonalization) Series

A three-part lab challenge celebrating 10 years of IBM Quantum on the cloud.

| Notebook | Description |
|----------|-------------|
| **[01_sample_then_diagonalize.ipynb](01_sample_then_diagonalize.ipynb)** | Core notebook 1/3. Introduces SQD on a transverse-field Ising chain: the $2^n$ wall, ground-state concentration, cropping Hamiltonians, sampling bitstrings from a circuit, and the central result — *a mediocre circuit still gives an excellent energy*. |
| **[02_molecules_as_bitstrings.ipynb](02_molecules_as_bitstrings.ipynb)** | Core notebook 2/3. Applies SQD to molecular chemistry (H₂): electron configurations as bitstrings, Hartree-Fock from one determinant, using `solve_fermion` from the SQD addon, and watching a determinant product space improve a bond-breaking curve. No quantum hardware needed — classical half of SQD. |
| *(Notebook 3 would extend to quantum sampling on hardware)* | |

### Challenge Tutorials (BasQ Qiskit Fall Fest 2026)

Three standalone tutorials by Benjamin Tirado (Basque Quantum):

| Notebook | Topic | Algorithm |
|----------|-------|-----------|
| **[challenge_1_tutorial.ipynb](challenge_1_tutorial.ipynb)** | Ground-state energy of H₂ | **VQE** — Jordan-Wigner mapping, UCCSD ansatz, Hartree-Fock reference, classical optimization |
| **[challenge_2_tutorial.ipynb](challenge_2_tutorial.ipynb)** | Max-Cut on a graph | **QAOA** — cost/mixer Hamiltonians, alternating layers, parameter optimization, sampling solutions |
| **[challenge_3_tutorial.ipynb](challenge_3_tutorial.ipynb)** | TFIM spin-chain dynamics | **Digital quantum simulation** — Trotterization (Lie-Trotter/Suzuki), time-evolution circuits, magnetization tracking |

### In-the-Classroom Modules (with auto-grading)

Graded exercises from the Qiskit in the Classroom curriculum, adapted for Fall Fest:

| Notebook | Topic |
|----------|-------|
| `get-started-with-qiskit_fallfest.ipynb` | Qiskit basics: circuits, gates, measurement, running on simulator/hardware |
| `superposition-with-qiskit_fallfest.ipynb` | Superposition, Hadamard, X-basis measurement |
| `exploring-uncertainty-with-qiskit_fallfest.ipynb` | Uncertainty principle, incompatible observables |
| `stern-gerlach-measurements-with-qiskit_fallfest.ipynb` | Stern-Gerlach experiment, sequential measurements |
| `bells-inequality-with-qiskit_fallfest.ipynb` | CHSH inequality, Bell states, entanglement verification |
| `quantum-teleportation_fallfest.ipynb` | Quantum teleportation protocol |
| `quantum-key-distribution_fallfest.ipynb` | BB84 protocol, eavesdropping detection |
| `deutsch-jozsa_fallfest.ipynb` | Deutsch-Jozsa algorithm, oracle construction |
| `grovers_fallfest.ipynb` | Grover's search algorithm, amplitude amplification |
| `shors-algorithm_fallfest.ipynb` | Shor's factoring algorithm, period finding |
| `qft_fallfest.ipynb` | Quantum Fourier Transform circuit |
| `vqe_fallfest.ipynb` | Variational Quantum Eigensolver for chemistry |

---

## Quick Start

### Open in Google Colab (recommended)

Click the badge above or visit:
```
https://colab.research.google.com/github/eecsclubofficial/qff-content
```

Then open any `.ipynb` file from the file browser.

### Run Locally

```bash
# Create environment
python -m venv venv
source venv/bin/activate

# Install dependencies (varies by notebook)
pip install "qiskit[visualization]" qiskit-aer qiskit-ibm-runtime pylatexenc ipywidgets

# For challenge notebooks:
pip install qiskit_nature pyscf qiskit_algorithms rustworkx

# For SQD notebooks:
pip install qiskit-addon-sqd pyscf

# Launch Jupyter
jupyter lab
```

---

## Prerequisites by Notebook

| Notebook | Required Background |
|----------|---------------------|
| Essentials.ipynb | None — starts from zero |
| QFT_QPE.ipynb | Essentials Ch. 3, 4, 7 (gates, measurement, interference) |
| 01_sample_then_diagonalize.ipynb | Essentials (qubits, circuits, measurement, primitives) |
| 02_molecules_as_bitstrings.ipynb | Notebook 1 |
| Challenge 1 (VQE) | Basic Qiskit, some quantum chemistry concepts helpful |
| Challenge 2 (QAOA) | Basic Qiskit, combinatorial optimization basics |
| Challenge 3 (Dynamics) | Basic Qiskit, Hamiltonian simulation concepts |
| Classroom modules | Progressive — start with `get-started-with-qiskit` |

---

## Key Qiskit Concepts Covered

- **Primitives**: `StatevectorSampler`, `StatevectorEstimator`, `AerSampler`
- **Circuits**: `QuantumCircuit`, parametrized circuits, `measure_all()`
- **Quantum Info**: `Statevector`, `Operator`, `SparsePauliOp`, `partial_trace`, `entropy`
- **Visualization**: `plot_bloch_vector`, `plot_bloch_multivector`, `plot_histogram`, circuit drawing
- **Transpilation**: `generate_preset_pass_manager`, optimization levels
- **Algorithms**: VQE, QAOA, QFT, QPE, Trotterization
- **Mappers**: Jordan-Wigner, fermion-to-qubit
- **Chemistry**: PySCF driver, Hartree-Fock, UCCSD, `qiskit_nature`

---

## Tips for Working Through the Notebooks

1. **Run cells top to bottom** — they build on each other
2. **Predict before running** — many cells have "Predict" prompts; write down your expectation first
3. **Attempt exercises before opening solutions** — hints and solutions are in collapsible `<details>` blocks
4. **Use the Check cells** — they validate your answers automatically
5. **Essentials.ipynb is the foundation** — if something is unclear later, revisit the relevant chapter there

---

## License

Materials are provided for educational purposes under the terms of the original authors and IBM Quantum. Individual notebooks may have their own licenses — see headers within each file.

---

## Acknowledgements

- **IBM Quantum** — for Qiskit, the Fall Fest program, and cloud quantum hardware access
- **Basque Quantum (BasQ)** — for the challenge tutorials (Benjamin Tirado)
- **EECS Club & Physics Club, IISER Bhopal** — for co-organising the event
- **Qiskit in the Classroom team** — for the graded classroom modules

---

## Questions or Issues?

Open an issue in this repository or reach out to the EECS Club / Physics Club at IISER Bhopal.
