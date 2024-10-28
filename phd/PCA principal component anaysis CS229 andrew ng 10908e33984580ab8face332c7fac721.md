# PCA principal component anaysis CS229 andrew ng

Tags: machine learning, notes

# Introduction

- PCA stands for principar compnents anaysis tries to indetify a sub sapce inw the data is approximately lies removing redundancy. Image image below. X one scale skill skill relates with enjoyment of performing a task, for example learning guitar.
- The section discusses a dataset  $\{x(i); i = 1, \dots, n\}$  representing attributes of various automobiles (such as maximum speed and turn radius), with each attribute  $x(i) \in \mathbb{R}^d$. If two variables are linearly dependent, the data lies ins d-1 instead of d. PCA tries to solve that problem.
- Example x1 and x2 correlated, how to find u1, that describe the data, u2 describes the noise.

![image.png](PCA%20principal%20component%20anaysis%20CS229%20andrew%20ng%2010908e33984580ab8face332c7fac721/image.png)

- data is first normalized: xj = xj-mean/std

# Proof of PCA

Sure! Here's the PCA proof formatted for **Notion**:

---

### Principal Component Analysis (PCA) Proof

### Problem Statement:

Given a dataset \( $X = [x_1, x_2, \dots, x_n]^\top$ \), where \( $x_i \in \mathbb{R}^d$ \) are column vectors representing data points, the goal of PCA is to find a set of orthogonal vectors (principal components) that explain the maximum variance of the data. Specifically, we aim to project the data onto a lower-dimensional subspace that captures most of its variance.

---

### 1. **Data Centering:**

First, center the dataset by subtracting the mean of each feature. Let  $\bar{x}$  be the mean of the data points:

$$
z = \frac{x-\mu}{\sigma}
$$

The centered data matrix is:
$\tilde{X} = X - \bar{x}$

This ensures that the data is centered around the origin, which simplifies the calculations.

---

### 2. **Covariance Matrix:**

Next, compute the covariance matrix \( \Sigma \) of the centered data:
$\Sigma = \frac{1}{n} \tilde{X}^\top \tilde{X}$

The covariance matrix  $\Sigma \in \mathbb{R}^{d \times d}$ captures the variance and correlation between the different dimensions of the data.

---

### 3. **Optimization Objective:**

We aim to find the principal components, i.e., the directions in which the variance of the data is maximized. Let  $w \in \mathbb{R}^d$  be a unit vector (principal component). The variance of the data projected onto  $w$  is:
$\text{Var}(w^\top \tilde{X}) = w^\top \Sigma w$

Our goal is to maximize this variance with respect to \( $w$ \), subject to the constraint that \( $w$ \) is a unit vector, i.e., $|w\|_2^2 = 1$ .

---

### 4. **Lagrangian Formulation:**

To solve this constrained optimization problem, we introduce a Lagrange multiplier $\lambda$ and define the Lagrangian:

$\mathcal{L}(w, \lambda) = w^\top \Sigma w - \lambda (w^\top w - 1)$

Here, \( \lambda \) is the Lagrange multiplier enforcing the constraint \( $w^\top w = 1$ \).

---

### 5. **Taking Derivatives:**

Take the derivative of the Lagrangian with respect to  $w$  and set it to zero to find the optimal :
$\frac{\partial \mathcal{L}}{\partial w} = 2 \Sigma w - 2 \lambda w = 0$

Simplifying, we get the **eigenvalue equation**:
$\Sigma w = \lambda w$

This shows that \( w \) must be an **eigenvector** of the covariance matrix \( \Sigma \), and \( \lambda \) is the corresponding **eigenvalue**.

---

### 6. **Eigenvalue Interpretation:**

The eigenvalue \( \lambda \) corresponds to the variance of the data along the direction $w$. To maximize the variance, we choose the eigenvector corresponding to the **largest eigenvalue** of  $\Sigma$. This eigenvector is the first principal component.

---

### 7. **Higher Principal Components:**

After finding the first principal component, we can find additional principal components by iterating the process and ensuring that each new component is orthogonal to the previous ones. The \( $k$ \)-th principal component is the eigenvector of  $\Sigma$  corresponding to the $k$-th largest eigenvalue.

---

### Summary of PCA:

- The **principal components** of the data are the **eigenvectors** of the covariance matrix \( \Sigma \).
- The amount of variance explained by each principal component is given by the corresponding **eigenvalue**.
- To reduce the dimensionality of the data, we project it onto the subspace spanned by the top \( k \) eigenvectors (the principal components with the largest eigenvalues).

---

### Final Projection:

Once the principal components \( $w_1$, $w_2, \dots, w_k$ \) are found, the data can be projected onto the \( k \)-dimensional subspace:
$Z = X W$
where \( W \) is the matrix of the top \( k \) principal components, and \( $Z$ \) is the lower-dimensional representation of the data.

---