# Core Task: Quantum Error Correction with Classical Codes

## Overview

This folder contains our implementation for the Core Task (Section 5) of the iQuHack 2026 Alice & Bob challenge. We explore quantum error-correcting codes inspired by classical codes, specifically optimized for biased noise channels where bit-flip (X) errors dominate.

## Contents

- `notebook.ipynb` - Main notebook containing all implementations and analysis

## Implemented Codes

### 1. BCH [[15, 7, 5]] Code

We implemented a BCH (Bose-Chaudhuri-Hocquenghem) code that:
- Encodes 7 logical qubits into 15 physical qubits
- Has distance 5, allowing correction of up to 2 bit-flip errors
- Uses 8 stabilizer measurements (syndrome bits)

**Key features:**
- Generator polynomial: g(x) = x^8 + x^7 + x^6 + x^4 + 1
- Parity check matrix derived from the generator polynomial
- Lookup-table decoder for syndrome-based error correction

### 2. Steane [[7, 1, 3]] Code

We also implemented the Steane code as a CSS (Calderbank-Shor-Steane) code:
- Encodes 1 logical qubit into 7 physical qubits
- Has distance 3, allowing correction of 1 error
- Demonstrates the CSS construction for quantum codes

## Simulation Results

Our simulations show that:
- The BCH code matches theoretical predictions for logical error rates
- For physical error rate p = 0.01, the BCH code achieves significant error suppression
- The encoding efficiency (k/n = 7/15 ≈ 0.47) is much higher than the repetition code (k/n = 1/n)

## Comparison with Repetition Codes

| Code | n | k | d | k/n | t (correctable errors) |
|------|---|---|---|-----|------------------------|
| Repetition (n=15) | 15 | 1 | 15 | 0.067 | 7 |
| BCH [[15,7,5]] | 15 | 7 | 5 | 0.467 | 2 |
| Steane [[7,1,3]] | 7 | 1 | 3 | 0.143 | 1 |

The BCH code provides significantly better encoding efficiency while still offering meaningful error correction capability for low physical error rates.

## Dependencies

- stim ~= 1.15
- numpy
- matplotlib
- scipy

## Team

Team Donut Coder - iQuHack 2026
