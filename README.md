# Random Projection: Gaussian vs. Sparse

This project implements a comparison between Gaussian Random Projection and Sparse Random Projection for dimensionality reduction, based on the reference paper "Very Sparse Random Projections" by Ping Li, Trevor J. Hastie, and Kenneth W. Church (KDD'06, 2006). The implementation uses scikit-learn's `random_projection` module to demonstrate the trade-offs in computation time and accuracy (measured by mean relative error in pairwise distances).

The code simulates high-dimensional data (n=1000 samples, D=10000 features) and reduces it to k=100 dimensions. It compares:
- Gaussian Random Projection: Dense matrix with Gaussian entries, preserving distances in expectation but computationally intensive.
- Sparse Random Projection: Sparse matrix with density=1/√D (Very Sparse variant from the paper, achieving ~√D speedup with minimal accuracy loss due to asymptotic normality and variance convergence).

Key insights from the reference:
- Sparse projections (with s=√D) offer significant speedup (e.g., √D-fold) while converging to Gaussian performance for large D.
- For heavy-tailed data, apply term weighting (e.g., sqrt or log) for robustness.
- Variance formulas and asymptotic distributions ensure pairwise distances are preserved.

## Installation

Requires Python 3+ and the following packages:
- numpy
- scikit-learn

Install via pip:
pip install numpy scikit-learn
