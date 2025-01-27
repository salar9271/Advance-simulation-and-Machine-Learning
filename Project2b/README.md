# **TIF345/FYM345 Project 2b: Bayesian Optimization**

This project focuses on the efficient minimization of the potential energy surface (PES) for a gold atom on a gold surface. Through a series of tasks, we investigate and compare brute-force grid-based analysis, local search methods, and Bayesian Optimization using Gaussian Processes (GPs). The study highlights the effectiveness of probabilistic models like GPs in computationally intensive material science problems.

---

## **Project Description**
The main objective of this project is to identify the global minimum energy configuration of a gold atom on a gold surface, a task critical for understanding catalytic behavior, material stability, and interfacial phenomena. The project includes the following tasks:
1. **Task 1:** Direct calculation of the PES over a dense grid to locate the global minimum.
2. **Task 2:** Local search methods using gradient descent to refine global and local minima from random starting points.
3. **Task 3:** Bayesian Optimization using Gaussian Processes to minimize the PES with fewer iterations by leveraging uncertainty quantification.
4. **Task 4:** Training a general-purpose GP model for transition path analysis between global and local minima.

---

## **Repository Contents**
This repository contains the following files and directories:
- **`images/`**: Visualizations
- **`data/`**: Folder containing raw and processed datasets used for PES calculations and model training.
- **`README.md`**: This document.
- **`Project2b_Report.pdf`**: Detailed project report, including methods, results, and discussions.
- **`Project2b.ipynb`**: Jupyter Notebook with Python implementation of all tasks.

---

## **Highlights**
### **Task 1: Direct PES Calculation**
- A dense grid of 300x300 points was used to calculate the PES.
- Identified the global minimum at coordinates `(3.2867 Å, 0.7237 Å)` with energy `7.0761 eV`.
- Brute-force approach required **90,000 calculations** and significant computational time.

### **Task 2: Local Search**
- Applied gradient descent on 300 random starting points using `scipy.optimize.minimize`.
- Found 19 unique local minima; 15.3% were clustered around the global minimum.
- Refined global minimum: `(3.2591 Å, 0.7212 Å)` with energy `7.0751 eV`.

### **Task 3: Bayesian Optimization**
- Utilized Gaussian Processes (GPs) with an acquisition function for efficient exploration.
- Tested various exploration-exploitation trade-offs by tuning β values.
- Optimal β = 5 achieved convergence to the global minimum at `(3.2610 Å, 0.7198 Å)` with energy `7.0751 eV`.

### **Task 4: Transition Paths**
- Trained a general-purpose GP model on the PES for transition path analysis.
- RMSE decreased significantly (from ~0.18 eV to <0.05 eV) with 100 training samples.
- The model accurately captured the energy barriers and uncertainties along transition paths.

---

## **Results**
- **Best Minimum Energy:** `7.0751 eV`, achieved by local search and Bayesian Optimization.
- **Efficiency:** Bayesian Optimization reduced the number of evaluations significantly compared to brute-force methods.
- **Transition Path Analysis:** The general-purpose GP closely approximated EMT reference energies with minimal error.

---

## **How to Use**
1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/Advance-simulation-and-Machine-Learning.git
   cd Advance-simulation-and-Machine-Learning/Project2b
