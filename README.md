# PORTFOLIOQ — Quantum-Assisted Portfolio Optimization using QAOA

**QuantumXpo 2026** | Rajiv Gandhi University of Knowledge Technologies (RGUKT) – IIIT Nuzvid

## Problem
Selecting a portfolio means choosing a combination of assets that balances
expected return, risk, and diversification — inside a fixed budget and a
limit on how many assets can be held. Checking every combination by brute
force scales poorly: with 8 candidate assets alone there are 256 possible
selections, and the search space grows fast as more assets are added.

## Solution
We formulate the portfolio selection problem as a Quadratic Unconstrained
Binary Optimization (QUBO) and solve it with the Quantum Approximate
Optimization Algorithm (QAOA) implemented in Qiskit. The model selects a
budget-constrained subset of assets that maximizes expected return while
minimizing risk, based on the assets' return and covariance data.

## Methodology
1. Define expected returns and per-asset risk for the candidate assets.
2. Build a covariance matrix from that risk data.
3. Formulate the problem as a QUBO using Qiskit Optimization.
4. Map the QUBO to an Ising Hamiltonian.
5. Run QAOA (Qiskit Algorithms) with the COBYLA optimizer on a simulator.
6. Benchmark the result against a classical brute-force baseline.

## Demo dataset
8 assets (Asset A–H), budget-constrained to 4 selections — matching the
asset universe and parameters shown on the project website.

## Tech Stack
Qiskit · Qiskit Optimization · Qiskit Algorithms · Qiskit Runtime · QAOA ·
COBYLA · NumPy · Matplotlib

## Setup
```bash
pip install qiskit qiskit-optimization qiskit-algorithms numpy matplotlib
python quantrisk.py
```

## Output
The script prints the quantum (QAOA) and classical (brute-force) asset
selections and their objective values, and saves a comparison bar chart
(`comparison_chart.png`). On the default demo dataset, both approaches
select Asset A, C, E, and G.

## Website
`index.html` is a companion dashboard presenting the same problem,
methodology, and results interactively — asset universe, a configurable
optimizer panel, the QAOA circuit, and a quantum-vs-classical comparison.

## Disclaimer
Educational research demo. Uses simulated/demo data and is not financial
advice.
