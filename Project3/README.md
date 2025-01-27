# **TIF345/FYM345 Project 3: A Galton Board on a Rocking Ship**

This project investigates a modified Galton board system where bead trajectories are influenced by inertia and a rocking ship's slope. Using Approximate Bayesian Computation (ABC) and neural networks, we infer the hidden parameters—**α** (inertia bias) and **s** (slope bias)—from observed bead distributions.

## **Project Description**
The Galton board, a classic demonstration of the central limit theorem, is extended in this project with two additional parameters:
- **α (Inertia Bias):** Beads are more likely to continue in the same direction as the previous step.
- **s (Slope Bias):** A rocking slope introduces an overall directional bias.

The objective is to estimate **α** using a combination of:
1. **Approximate Bayesian Computation (ABC):** Likelihood-free inference using synthetic data simulations.
2. **Neural Networks (NN):** For estimating **s** and refining the ABC posterior.

### Key Tasks:
1. Simulate bead trajectories for given **α** and **s**.
2. Develop an ABC routine to estimate **α**.
3. Train an NN to predict **α** and **s** from observed distributions.
4. Integrate NN predictions to enhance the ABC routine.
5. Iteratively refine the posterior distribution for **α**.

---

## **Repository Contents**
- **`Project3_Report.pdf`**: Detailed report on methods, results, and improvements.
- **`Project_3description.pdf`**: Project instructions and theoretical background.
- **`project3.ipynb`**: Jupyter Notebook for simulations, ABC implementation, and NN integration.
- **`board.cpython-38-x86_64-linux-gnu.so`**: Python module for running experiments on the Galton board.
- **`board_data.npy`**: Pre-generated experimental data for use in simulations.
- **`board_data_gen.py`**: Script for generating synthetic data from simulations.


---

## **Highlights**
### **Data Simulation**
- Bead distributions are generated for varying **α** and **s** values.
- The simulator accounts for inertia and slope biases, with probabilities:
  \[
  P_{\pm} = 0.5 \pm (\alpha M + s)
  \]
  where \( M \) encodes the bead’s previous direction.

### **Approximate Bayesian Computation**
- Summary statistics include mean and variance of normalized distributions.
- A Gaussian kernel is used for likelihood-free inference:
  \[
  K = \exp\left(-\frac{|s(y^*) - s(y_{\text{obs}})|^2}{2h^2}\right)
  \]
- Initial results for **α** estimate a mean of 0.32 with a credible interval (CI) of [0.23, 0.41].

### **Neural Network Integration**
- A neural network maps bead distributions to **α** and **s**.
- Improved ABC efficiency by narrowing the parameter search space.
- Results show a refined **α** mean of 0.34 and a CI of [0.31, 0.38].

### **Iterative Refinement**
- Posterior from one ABC run serves as the prior for the next.
- Final **α** mean of 0.35 with a CI of [0.32, 0.37].

---

## **Results**
1. **Posterior Distributions:**
   - Initial ABC: α Mean = 0.32, CI = [0.23, 0.41]
   - ABC with NN: α Mean = 0.34, CI = [0.31, 0.38]
   - Iterative ABC: α Mean = 0.35, CI = [0.32, 0.37]

2. **NN Performance:**
   - Root Mean Square Error (RMSE):
     - **α:** RMSE = 0.022
     - **s:** RMSE = 0.0051

3. **Plots:**
   - Training and validation loss (NN): `NN_training.pdf`
   - Posterior distributions (ABC and NN-guided): `abc.pdf`, `abc_nn.pdf`, `seq_abc_nn.pdf`

---

## **Future Improvements**
1. **Increase Bead Count:** Enhances summary statistics by leveraging the central limit theorem.
2. **Refine ABC Techniques:** Explore ABC-MCMC and ABC-SMC methods for adaptive posterior sampling.
3. **Optimize NN Architecture:** Test alternative network designs to further reduce errors.
