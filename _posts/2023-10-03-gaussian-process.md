---
layout: post
title: Gaussian Proceess
date: 2023-10-03 16:20:00 +/-5000
categories: [Math]
tags: [ gaussian process ]     # TAG names should always be lowercase
---
## Gaussian Distribution
### Univariate Gaussian Distribution:
$$
p(x \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)
$$
- \(x\): the random variable.
- \(\mu\): the mean (average) of the distribution.
- \(\sigma^2\): the variance (a measure of spread or variability).

### Bivariate Gaussian Distribution:
The **joint** behavior of two continuous random variables \(x_1\) and \(x_2\), and the joint PDF is below: 

$$
p(\mathbf{x} \mid \boldsymbol{\mu}, \mathbf{\Sigma}) = \frac{1}{2\pi |\mathbf{\Sigma}|^{1/2}} \exp\left(-\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^T \mathbf{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu})\right)
$$

- \(\mathbf{x} = [x_1, x_2]\) is a vector of the two random variables.
- \(\boldsymbol{\mu} = [\mu_1, \mu_2]\) is a vector of means.
- \(\mathbf{\Sigma}\) is the covariance matrix, which specifies the variances of \(x_1\) and \(x_2\) on the diagonal and their covariance off-diagonal.

$$
\boldsymbol{\Sigma}_{2 \times 2 } = \begin{bmatrix} \sigma_X^2 & \text{Cov}(X, Y) \\ \text{Cov}(X, Y) & \sigma_Y^2 \end{bmatrix}
$$

$$
\text{Cov}(x_1, x_2) = \frac{1}{N} \sum_{i=1}^{N} (x_{1i} - \mu_1)(x_{2i} - \mu_2)
$$

  - \(\text{Cov}(x_1, x_2)\) is the covariance between \(x_1\) and \(x_2\).
  - \(N\) is the number of data points.
  - \(x_{1i}\) and \(x_{2i}\) are individual data points of \(x_1\) and \(x_2\).
  - \(\mu_1\) and \(\mu_2\) are the means of \(x_1\) and \(x_2\).

### Multivariate Gaussian Distribution:
The same format as above, but vectors have higher dimension. 
$$
p(\mathbf{x} \mid \boldsymbol{\mu}, \mathbf{\Sigma}) = \frac{1}{(2\pi)^{n/2}|\mathbf{\Sigma}|^{1/2}} \exp\left(-\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^T \mathbf{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu})\right)
$$

### Inf-variate Gaussian Distribution -> GP:

$$
f(x) \sim \mathcal{GP}(m(x), k(x, x'))
$$

$$
\mu_{2 \times 1 } \rightarrow \mu_{\inf \times 1 } \rightarrow m(x)
$$

$$
\text{Cov}(x_1, x_2) \rightarrow \text{Cov}(\text{inf number of variables}) \rightarrow k(x,x')
$$

- \(m(x)\): mean function 
- \(k(x,x')\): covariance function, describes the relationships between function values at different input points x and x'.
  
## GP: Gaussian Process


### Kernel function 
#### RBF: Radial Basis Function
The Radial Basis Function (RBF) kernel, also known as the Gaussian kernel, is commonly used in machine learning and kernel methods. It is defined as follows:

$$
k(x, x') = \exp\left(-\frac{\|x - x'\|^2}{2\sigma^2}\right)
$$

- \(k(x, x')\): The RBF kernel function that computes the similarity or correlation between two input points, \(x\) and \(x'\).
- \(\|x - x'\|\): The Euclidean distance between the two input points.
- \(\sigma^2\): The kernel parameter, which determines the "width" or scale of the kernel. It controls the degree of smoothness and influence of neighboring points.

The RBF kernel is characterized by its ability to capture complex relationships in the data and is widely used in applications such as Gaussian Processes, Support Vector Machines (SVMs), and kernel-based regression.

This kernel function assigns high similarity (near 1) to points that are close to each other in the input space and low similarity (near 0) to points that are far apart.


### Applications: GP Regression 
这个函数的任何有限集合的点都遵循多元高斯分布.对于任意有限集合的输入点 \(x_1, x_2, ..., x_n\)，其对应的函数值 \(f(x_1), f(x_2), ..., f(x_n)\) 的联合分布是多元高斯分布，其均值向量由均值函数给出，协方差矩阵由核函数给出。
有限数量的点上进行推断，我们实际上是在查看这些点上函数值的联合分布

高斯过程（GP）是一个定义在函数空间上的分布，为每一个可能的函数赋予了一个概率。

无论函数空间有多大或有多少其他点，只要我们知道了有限数量的点的值和它们与新点的协方差，我们就可以进行推断。

尽管高斯过程是在整个函数空间上定义的（即无限多的点），但我们实际上只关心我们观察到的点或我们想要进行预测的点。其他所有的点，尽管它们是无限的，对我们的推断没有直接的影响。

## Reference 
https://www.zhihu.com/question/46631426/answer/1735470753?utm_psn=1698678822432731137&utm_id=0