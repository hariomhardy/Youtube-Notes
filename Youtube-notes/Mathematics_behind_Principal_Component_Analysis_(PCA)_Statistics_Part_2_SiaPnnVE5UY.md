```yaml
title: Mathematics behind Principal Component Analysis (PCA) | Statistics | Part 2
channel: Unknown
url: https://www.youtube.com/watch?v=SiaPnnVE5UY
date_processed: 2023-10-27
content_type: youtube_notes
```

## 2. TL;DR
This video provides a step-by-step mathematical walkthrough of Principal Component Analysis (PCA) using a two-variable dataset. It explains how to construct a covariance matrix and derive eigenvalues and eigenvectors to determine the direction and magnitude of a new feature space. The core insight is that PCA reduces dimensionality by transforming data into an orthonormal basis where the variance is maximized.

## 3. Learning Objectives
*   Understand the role of the **covariance matrix** in PCA.
*   Explain the relationship between **eigenvectors** (direction) and **eigenvalues** (magnitude).
*   Follow the mathematical process of calculating eigenvalues and eigenvectors from a covariance matrix.
*   Understand the objective of PCA: maximizing variance through projection.

## 4. Concept Overview
PCA is a dimensionality reduction technique that transforms a set of correlated variables into a smaller set of uncorrelated variables called **Principal Components**. Mathematically, this involves calculating the covariance matrix of the data and then solving for its eigenvalues and eigenvectors. The eigenvectors define the new axes (feature space), while the eigenvalues represent the amount of variance captured by each axis.

## 5. Detailed Structured Notes

### The Covariance Matrix
*   **Definition:** A matrix that expresses the covariance between every pair of variables in a dataset.
*   **Significance:** It is the foundation of PCA. The eigenvectors of this matrix represent the directions of maximum variance.
*   **Calculation:**
    1.  Calculate the mean of each variable ($x_{mean}, y_{mean}$).
    2.  Subtract the mean from each data point.
    3.  Calculate the covariance for each pair using: $Cov(x, y) = \frac{\sum(x_i - x_{mean})(y_i - y_{mean})}{n-1}$.

### Eigenvalues and Eigenvectors
*   **Eigenvectors (Principal Components):** These determine the **direction** of the new feature space.
*   **Eigenvalues:** These determine the **magnitude** (amount of variance) associated with each principal component.
*   **The Characteristic Equation:** To find eigenvalues ($\lambda$), solve:
    $det(C - \lambda I) = 0$
    Where $C$ is the covariance matrix and $I$ is the identity matrix.

## 6. Step-by-Step Process: Calculating PCA
1.  **Center the Data:** Subtract the mean from each variable.
2.  **Compute Covariance Matrix ($C$):** Populate the matrix with variances on the diagonal and covariances on the off-diagonals.
3.  **Solve for Eigenvalues ($\lambda$):** Solve the quadratic equation derived from $det(C - \lambda I) = 0$.
4.  **Solve for Eigenvectors:** For each $\lambda$, solve the system of linear equations $(C - \lambda I)v = 0$.
5.  **Normalize:** Ensure the sum of the squares of the eigenvector components equals 1 (orthonormal basis).

## 7. Important Terminology
*   **Covariance:** A measure of the joint variability of two random variables.
*   **Eigenvector:** A non-zero vector that changes only by a scalar factor when a linear transformation is applied.
*   **Eigenvalue:** The scalar factor by which an eigenvector is scaled.
*   **Orthonormal Basis:** A set of vectors that are orthogonal (perpendicular) to each other and have a unit length (magnitude of 1).
*   **Dimensionality Reduction:** The process of reducing the number of random variables under consideration.

## 8. Common Mistakes / Misconceptions
*   **Calculation Errors:** Manual calculation of eigenvalues and eigenvectors is prone to arithmetic errors; using software solvers is recommended for practical applications.
*   **Confusing Variables:** Ensure you correctly distinguish between the original variables ($v_1, v_2$) and the transformed principal components ($PC_1, PC_2$).

## 9. Key Takeaways
*   PCA aims to find projection directions where the variance of the projected data is maximized.
*   The covariance matrix is central to identifying the structure of the data.
*   Eigenvectors represent the new axes of the feature space.
*   Eigenvalues represent the "importance" or magnitude of each principal component.
*   The resulting principal components are orthogonal to each other.

## 10. Quick Reference / Cheat Sheet
*   **Covariance Formula:** $Cov(x, y) = \frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{n-1}$
*   **Characteristic Equation:** $det(C - \lambda I) = 0$
*   **Orthonormal Constraint:** $x^2 + y^2 = 1$ (for 2D eigenvectors)
*   **Goal:** Maximize variance by projecting data onto eigenvectors.