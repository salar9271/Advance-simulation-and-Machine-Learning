# **TIF345/FYM345 Project 1: Cosmological Models**

This project explores the accelerating expansion of the Universe using real data from the Supernova Cosmology Project (SCP). By analyzing the luminosity distances and redshifts of Type Ia supernovae, we infer key cosmological parameters such as the Hubble constant (H0) and the deceleration parameter (q0).

## **Project Description**
Type Ia supernovae, as standard candles, provide insights into the Universe's expansion history. This project uses SCP Union 2.1 data to:
1. **Task 1:** Estimate the Hubble constant (H0) and the deceleration parameter (q0) for the small-redshift regime (z < 0.5).
2. **Task 2:** Compare two cosmological models:
   - ΛCDM (Lambda Cold Dark Matter)
   - wCDM (Cold Dark Matter with a dark energy equation of state parameter w)

## **Repository Contents**
The following files are included in this repository:
- **`project_description.pdf`**: Overview of the project, including tasks and theoretical background.
- **`project1.ipynb`**: Jupyter Notebook with the implementation of the tasks, including data preprocessing, Bayesian inference, and model comparison.
- **`Project1Report.pdf`**: A comprehensive report detailing methodology, results, and discussion.
- **`SCPUnion2.1_mu_vs_z.txt`**: SCP Union 2.1 dataset containing redshift and distance modulus measurements.
- **`README.md`**: This document.

## **Highlights**
### **Task 1: Estimation of Cosmological Parameters**
- Used Bayesian inference to estimate H0 and q0.
- Evidence strongly supports an accelerating universe (q0 < 0).

### **Task 2: Model Comparison**
- Compared ΛCDM and wCDM models using the Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC).
- ΛCDM was slightly preferred due to its simplicity and better fit.

## **Results**
1. **Posterior Predictive Plot:**
   - Shows the relationship between the distance modulus (mu) and redshift (z).
   - Confirms model alignment with observed data.

2. **Key Parameters:**
   - **Hubble Constant (H0):** 69.61 km/s/Mpc
   - **Deceleration Parameter (q0):** -0.42
   - **Matter Density Parameter (Omega_M0):** 0.28

3. **Model Performance:**
   - AIC for ΛCDM: 77.3
   - AIC for wCDM: 79.3
   - ΛCDM emerged as slightly better.
