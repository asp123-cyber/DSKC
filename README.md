# Statistical Analysis of the Hubble Tension Using Type Ia Supernova Data

## Overview

This project investigates the **Hubble Tension**, the discrepancy between early-universe and late-universe measurements of the Hubble constant.

The study explores an extension of the standard Lambda-CDM cosmological model by introducing an additional redshift-dependent barotropic fluid.

Using Type Ia Supernova (SNe Ia) observations from the **Pantheon dataset**, cosmological parameters are constrained through Bayesian inference and Markov Chain Monte Carlo (MCMC) techniques using Python's `emcee` library.

The primary objective is to investigate whether this extended cosmological model can reproduce Hubble constant values consistent with local-universe observations.

## Objectives

- Investigate the Hubble Tension between early- and late-universe measurements.
- Explore an extended Lambda-CDM cosmological model.
- Analyse observational data from Type Ia Supernovae.
- Implement Bayesian inference and MCMC parameter estimation.
- Estimate cosmological parameters and examine their posterior distributions.

## Cosmological Model

The standard Lambda-CDM model is extended by introducing an additional energy component whose density evolves with redshift according to a power-law dependence.

Two values of the model parameter are investigated:

- n = 1
- n = 2.5

The analysis considers the effects of this additional component on the expansion history of the universe and the resulting cosmological parameter estimates.

## Dataset

**Pantheon Type Ia Supernova Dataset**

The Pantheon dataset provides observational measurements of Type Ia Supernovae, which serve as standard candles for estimating cosmological distances.

**Dataset source:**  
https://github.com/dscolnic/Pantheon

The analysis also incorporates a Gaussian prior based on Cosmic Microwave Background (CMB) constraints.

## Methodology

The analysis follows these major steps:

1. **Data Preparation:** Extracting and processing observational data from the Pantheon dataset.
2. **Cosmological Modelling:** Implementing the extended Friedmann model and calculating theoretical luminosity distances.
3. **Likelihood Analysis:** Comparing theoretical predictions with observed luminosity distances using chi-square statistics.
4. **Bayesian Inference:** Defining prior distributions and constructing posterior probability distributions.
5. **MCMC Sampling:** Implementing the affine-invariant ensemble sampler using the `emcee` Python library.
6. **Parameter Estimation:** Analysing posterior distributions, confidence intervals, and parameter correlations using corner plots.

The final analysis uses 15,000 sampling points and 20 walkers.

## Results

The best-fit cosmological parameters obtained at the 68% confidence level are presented below.

### Case I: n = 1

| Parameter | Best-fit value |
|:---|---:|
| Hubble Constant (H0) | 74.86 ± 0.26 |
| Matter Density (Omega_m0) | 0.255 ± 0.006 |
| Additional Component (Omega_n0) | 0.229 (+0.060 / -0.057) |
| Dark Energy Density (Omega_Lambda) | 0.569 (+0.056 / -0.059) |

### Case II: n = 2.5

| Parameter | Best-fit value |
|:---|---:|
| Hubble Constant (H0) | 74.65 (+0.23 / -0.24) |
| Matter Density (Omega_m0) | 0.256 ± 0.006 |
| Additional Component (Omega_n0) | -0.024 ± 0.017 |
| Dark Energy Density (Omega_Lambda) | 0.636 ± 0.017 |

### Key Observations

- The estimated Hubble constant is approximately 74.7 km/s/Mpc for both models.
- The results are consistent with late-universe measurements reported by the SH0ES collaboration.
- Posterior distributions provide constraints on cosmological parameters and their correlations.
- For n = 2.5, the additional energy-density parameter becomes negative, raising questions about the physical consistency of the model.

## Tools and Technologies

| Technology | Application |
|:---|:---|
| Python | Computational analysis |
| EMCEE | Markov Chain Monte Carlo sampling |
| Plotly | Data visualisation |
| Monte Carlo Methods | Statistical simulations |
| Bayesian Inference | Cosmological parameter estimation |

## References

1. D. Kumar, D. Choudhury, and D. Nandi, *Exploring the Hubble Tension: A Novel Approach through Cosmological Observations* (2023).  
   https://doi.org/10.48550/arXiv.2310.03509

2. Pantheon Type Ia Supernova Dataset:  
   https://github.com/dscolnic/Pantheon

3. Foreman-Mackey, D., Hogg, D. W., Goodman, J., et al., *The MCMC Hammer*.  
   https://doi.org/10.1086/670067

## Authors

- Ashish Patel
- Himanshu Aggarwal
- Khush Shaw
- Sudarshan Kumar

## Acknowledgements

This work was carried out as part of the **D. S. Kothari Centre Summer Internship Program 2025**, Miranda House, University of Delhi, under the guidance of Dr. Abha Dev Habib and Dr. Nisha Rani.
