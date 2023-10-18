---
layout: post
title: ML Matrix Decomposition
date: 2023-09-25 20:08:02 +/-5000
categories: [ML]
tags: [linear algebra]     # TAG names should always be lowercase
---

# Review: Matrix Decomposition 

## LU Decomposiiton 

$$ A = LU $$ 

- For square matrix only 
- L: lower triangular matrix 
- U: Upper triangular matrix 
- Gaussian elimination with row operation, but no row exchange, if exchange, do it before decomposition 


### Calculation steps 

$$
\begin{bmatrix}
    a_{11} & a_{12} & a_{13} & a_{14} \\
    a_{21} & a_{22} & a_{23} & a_{24} \\
    a_{31} & a_{32} & a_{33} & a_{34} \\
    a_{41} & a_{42} & a_{43} & a_{44} \\
\end{bmatrix}
$$



## Eigendecomposition

$$ A = Q \Lambda Q^{-1} $$

- For diagonalizable matrix only 
- $Q$ is the matrix of eigenvectors.
- $\Lambda$ is the diagonal matrix whose diagonal entries are the eigenvalues.

### Python Code 
```python 
# Python code to compute eigendecomposition using NumPy
import numpy as np

# Define a square matrix
A = np.array([[4, 2], [1, 3]])

# Compute eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(A)

# Diagonal matrix of eigenvalues
Lambda = np.diag(eigenvalues)

# Reconstruct the matrix
A_reconstructed = eigenvectors @ Lambda @ np.linalg.inv(eigenvectors)

print("Original Matrix:\n", A)
print("\nEigenvalues:\n", eigenvalues)
print("\nEigenvectors:\n", eigenvectors)
print("\nReconstructed Matrix:\n", A_reconstructed)
```

## SVD: Singular Value Decomposition 

$$A = U \Sigma V^*$$

- For any m×n matrix 
- $U$ is an m×m unitary matrix
- $\Sigma$ is an m×n diagonal matrix
- $V^*$ is the complex conjugate transpose of an n×n unitary matrix

### Python code
``` 
# Create a sample matrix for SVD
A = np.array([[1, 2, 3],
              [4, 5, 6],
              [7, 8, 9]])

# Perform SVD
U, S, VT = np.linalg.svd(A)
```