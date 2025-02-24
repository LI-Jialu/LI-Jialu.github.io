---
layout: post
title: Machine Learning Roadmap
date: 2023-09-25 20:08:02 +/-5000
categories: [ML]
tags: [roadmap]     # TAG names should always be lowercase
---

# Overview


## Recap: Linear Algebra
- **Matrix Operations**
- **Matrix Decomposition**
- **Matrix Calculus**

## The Learning Theory
- [**Is Learning Feasible?**  ]({{ site.baseurl }}{% link _posts/2023-10-31-learning-feasible.md %})
- **Theory of Generalization**
- **VC Dimension**
- **Bias & Variance** 
- **Regularization** 


## ML Techniques
- **Gradient Descent**
  - Solves the matrix inversion problem
  
- **Stochastic Gradient Descent**
  - Addresses the need for all samples by selecting batches


## ML Models 
- **Traditional Linear Regression**
  - Minimize error: $f = \| X w - y \|^2$
  - Gradient: $\nabla f(w) = 2(X^T X w - X^Ty)$
  - Solution: $w^* = (X^TX)^{-1}X^Ty$
  
- **Logistic Regression**
  - Maximize likelihood: 
    $$\max_w \prod_{n=1}^N \theta(y_n w^T x_n) = \min_w \sum_{n=1}^N \log(1+e^{-y_nw^Tx_N})$$
  
- **Support Vector Machine (SVM)**
- **CNN**
- **RNN**
- **Transformer** 

## References
- [Matrix Cookbook](https://www.math.uwaterloo.ca/~hwolkowi/matrixcookbook.pdf)
- [Stanford CS229](https://cs229.stanford.edu/syllabus-fall2020.html)
- [Caltech CS156](https://home.work.caltech.edu/telecourse.html)
