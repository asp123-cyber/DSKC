# Statistical Analysis of the Hubble Tension Using Type Ia Supernova Data

## Overview

This project investigates the **Hubble Tension** — the discrepancy between early-universe and late-universe measurements of the Hubble constant.

We explore an extension of the standard $\Lambda$CDM cosmological model by introducing an additional redshift-dependent barotropic fluid, whose energy density evolves as $(1+z)^n$.

Using Type Ia Supernova (SNe Ia) observations from the **Pantheon dataset**, we perform cosmological parameter estimation through Bayesian inference and Markov Chain Monte Carlo (MCMC) sampling using Python's `emcee` library.

## Objectives

- Investigate the Hubble Tension between early- and late-universe measurements.
- Study an extended $\Lambda$CDM cosmological model.
- Analyse Type Ia Supernova observational data.
- Implement Bayesian inference and MCMC parameter estimation.
- Constrain cosmological parameters and examine their posterior distributions.

## 1. Cosmological Model

The standard $\Lambda$CDM model is extended by introducing an additional energy-density component:

$$
\Omega_n(z)=\Omega_{n0}(1+z)^n
$$

The modified Friedmann equation is:

$$
H(z)=H_0\sqrt{
\begin{aligned}
&\Omega_{r0}(1+z)^4\\
&+\Omega_{m0}(1+z)^3\\
&+\Omega_{k0}(1+z)^2\\
&+\Omega_\Lambda\\
&+\Omega_{n0}(1+z)^n
\end{aligned}
}
$$

where:

- $H_0$ is the present-day Hubble constant.
- $\Omega_{r0}$ is the radiation density parameter.
- $\Omega_{m0}$ is the matter density parameter.
- $\Omega_{k0}$ is the curvature density parameter.
- $\Omega_\Lambda$ is the dark energy density parameter.
- $\Omega_{n0}$ is the additional energy-density parameter.
- $n$ determines the redshift dependence of the additional component.

The normalization condition is:

$$
\Omega_{r0}+\Omega_{m0}+\Omega_{k0}
+\Omega_\Lambda+\Omega_{n0}=1
$$

Two discrete values of $n$ are investigated:

- $n=1$
- $n=2.5$

## 2. Dataset

**Pantheon Type Ia Supernova Dataset**

The Pantheon dataset provides observational measurements of Type Ia Supernovae, which are used as standard candles to determine cosmological distances.

Dataset: [Pantheon – GitHub](https://github.com/dscolnic/Pantheon)

The analysis also incorporates a Gaussian prior from CMB constraints:

$$
H_0^2\Omega_{m0}=1424.18\pm31.37
$$

The other priors used are:

$$
8000\leq \frac{H_0^2}{\Omega_{m0}}\leq22000
$$

$$
0\leq\Omega_\Lambda\leq1
$$

## 3. Methodology

The analysis follows these steps:

**1. Data Preparation**

Extract and process observational data from the Pantheon dataset.

**2. Cosmological Modelling**

Implement the modified Friedmann equation and calculate theoretical luminosity distances.

**3. Likelihood Analysis**

Compare theoretical predictions with observed luminosity distances using the chi-square statistic:

$$
\chi^2(\Theta)=
\sum_{i=1}^{N}
\left[
\frac{
d_L^{\mathrm{th}}(z_i,\Theta)
-
d_L^{\mathrm{obs}}(z_i)
}{
\sigma_{d_L}(z_i)
}
\right]^2
$$

where $\Theta$ represents the cosmological parameters.

**4. Bayesian Inference**

Construct the posterior probability distribution using:

$$
P(\Theta\mid D)\propto
\mathcal{L}(D\mid\Theta)\,P(\Theta)
$$

where $\mathcal{L}$ is the likelihood and $P(\Theta)$ is the prior distribution.

**5. MCMC Sampling**

Implement the affine-invariant ensemble sampler using the `emcee` Python library.

**6. Parameter Estimation**

Analyse posterior distributions, confidence intervals, and parameter correlations using corner plots.

## 4. Results

The analysis was performed using **15,000 sampling points and 20 walkers**.

The best-fit cosmological parameters at the 68% confidence level are:

### Case I: $n=1$

| Parameter | Best-fit value |
|:---|:---|
| $H_0$ (km/s/Mpc) | $74.86\pm0.26$ |
| $\Omega_{m0}$ | $0.255\pm0.006$ |
| $\Omega_{n0}$ | $0.229^{+0.060}_{-0.057}$ |
| $\Omega_\Lambda$ | $0.569^{+0.056}_{-0.059}$ |

### Case II: $n=2.5$

| Parameter | Best-fit value |
|:---|:---|
| $H_0$ (km/s/Mpc) | $74.65^{+0.23}_{-0.24}$ |
| $\Omega_{m0}$ | $0.256\pm0.006$ |
| $\Omega_{n0}$ | $-0.024\pm0.017$ |
| $\Omega_\Lambda$ | $0.636\pm0.017$ |

### Key Observations

- The estimated Hubble constant is approximately $74.7$ km/s/Mpc for both models.
- The results are consistent with the late-universe SH0ES measurement.
- Posterior distributions provide constraints on the cosmological parameters and their correlations.
- For $n=2.5$, the additional energy-density parameter becomes negative, raising questions about the physical consistency of the model.

## 5. Tools and Technologies

| Technology | Application |
|:---|:---|
| Python | Computational analysis |
| NumPy | Numerical calculations |
| SciPy | Scientific computation |
| EMCEE | MCMC ensemble sampling |
| Plotly | Data visualisation |
| Statistical Methods | Monte Carlo simulation, likelihood analysis and Bayesian inference |

## 6. References

1. D. Kumar, D. Choudhury, and D. Nandi, *Exploring the Hubble Tension: A Novel Approach through Cosmological Observations* (2023).  
   https://doi.org/10.48550/arXiv.2310.03509

2. Pantheon Type Ia Supernova Dataset:  
   https://github.com/dscolnic/Pantheon

3. Foreman-Mackey, D., Hogg, D. W., Goodman, J., et al., *The MCMC Hammer*.  
   https://doi.org/10.1086/670067

## Authors

- Khush Shaw
- Himanshu Aggarwal
- Sudarshan Kumar
- Ashish Patel

## Acknowledgements

This work was carried out as part of the **D. S. Kothari Centre Summer Internship Program 2025**, Miranda House, University of Delhi, under the guidance of Dr. Abha Dev Habib and Dr. Nisha Rani.
