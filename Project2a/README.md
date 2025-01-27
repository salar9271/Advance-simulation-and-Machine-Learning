# **TIF345/FYM345 Project 2a: Alloy Cluster Expansions**

This project focuses on modeling and predicting the thermodynamic properties of the Au-Cu alloy using cluster expansion methods. By leveraging Bayesian statistics and various regression techniques, the effective cluster interactions (ECI) are analyzed to gain insights into the behavior and ground-state configuration of the alloy.

## **Project Description**
The Au-Cu alloy is significant due to its unique properties and applications. This project applies advanced statistical and machine learning techniques to perform a cluster expansion analysis. Tasks include:
1. **Task 1:** Generating and visualizing cluster vectors and mixing energy based on atomic structure data.
2. **Task 2:** Comparing Ordinary Least Squares (OLS) and Ridge Regression for ECI fitting.
3. **Task 3:** Applying covariance-regularized regression to account for physical intuition in high-dimensional problems.
4. **Task 4:** Using Bayesian analysis with Markov chain Monte Carlo (MCMC) to estimate posterior distributions for ECIs.
5. **Task 5:** Evaluating Automatic Relevance Detection Regression (ARDR) to identify significant ECIs.
6. **Task 6:** Testing all models on ground-state candidate data to predict structures with the lowest energy.

## **Repository Contents**
The following files are included in this repository:
- **`images/`**: Visualizations
- **`AuCu-structures.db`**: Database containing atomic structure data.
- **`ground-state-candidates.db`**: Database of candidate structures for ground-state energy predictions.
- **`README.md`**: This document.
- **`TIF345_CE_project_2a.ipynb`**: Jupyter Notebook with Python implementation for all tasks.
- **`Project2a_Report.pdf`**: Detailed project report summarizing methods, results, and conclusions.

## **Highlights**
### **Task 1: Cluster Vectors and Mixing Energy**
- Generated cluster vectors using the ASE and icet packages.
- Visualized Cu concentration vs. mixing energy to identify trends.

### **Task 2: OLS and Ridge Regression**
- Compared OLS and Ridge models for ECI fitting.
- Ridge regression reduced overfitting by introducing a penalty term.

### **Task 3: Covariance-Regularized Regression**
- Added physical intuition through a custom regularization matrix.
- Improved model performance by accounting for orbit size and radius.

### **Task 4: Bayesian Analysis with MCMC**
- Used MCMC to estimate posterior distributions for ECIs.
- Violin plots revealed higher uncertainty for higher-order clusters.

### **Task 5: Automatic Relevance Detection Regression**
- Identified key ECIs using threshold-based optimization.
- Demonstrated the significance of lower-order clusters in predicting alloy behavior.

### **Task 6: Ground-State Candidate Testing**
- Tested all models on provided ground-state candidates.
- Bayesian analysis provided probabilistic predictions, while simpler models like OLS and Ridge performed competitively.

## **Results**
- **Best-performing models:** Ridge Regression and ARDR showed slight advantages in predicting ECIs and minimizing CV errors.
- **Ground-state prediction:** Most models identified the same structure, with minor differences.
- **Time-efficiency:** Bayesian methods were computationally intensive, while simpler models like Ridge were faster and effective for this dataset size.
