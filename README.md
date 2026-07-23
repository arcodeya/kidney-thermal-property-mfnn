# Kidney Thermal Property MFNN

This project evaluates multi-fidelity neural networks for reconstructing temperature-dependent kidney thermal properties from sparse experimental data.

## Overview

Four targets are modeled:

- Porcine thermal conductivity
- Porcine thermal diffusivity
- Bovine thermal conductivity
- Bovine thermal diffusivity

The residual MFNN uses a linear low-fidelity approximation and learns a nonlinear correction:

\[
\hat{y}_{HF} = \rho \hat{y}_{LF} + \delta(T)
\]

An uncertainty-weighted version gives greater influence to experimental measurements with lower reported uncertainty.

## Models Compared

- Linear low-fidelity regression
- Exponential regression
- Gaussian process
- HF-only neural network
- Residual MFNN
- Uncertainty-weighted residual MFNN

Each model is evaluated using HF training sizes of 3, 5, 7, and 9 measurements across 20 random splits + performance is measured using MAE and RMSE.

## Main Result
- Uncertainty weighting improved the residual MFNN relative to the unweighted MFNN in 13 of 16 experimental configurations.
- Exponential regression and the HF-only neural network performed best more frequently overall --> MFNN performance depends on the tissue type, property, and available training data.

## Notes
- Figures / code clean-up coming soon.
- The proof_of_concept notebook was just to test the linear approximation on one single target.
