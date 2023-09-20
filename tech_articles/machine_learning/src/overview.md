# Overview 

第一部分：复习

1.1. 线性代数
- matrix operation 
- matrix decomposition 
- matrix calculus 

第二部分: 基础ML 

2.1.定义问题 
- 传统的线性回归：minimize error, $f = \| X w - y \|^2$，$\nabla f(w) = 2(X^T X w - X^Ty)$, $w^* = (X^TX)^{-1}X^Ty$
- Logistic regression: maximize likelihood, $max_w \prod_{n=1}^N \theta(y_n w^T x_n) = min_w \sum_{n=1}^N log(1+e^{-y_nw^Tx_N})$, 

2.2. 优化解决办法
- Gradient descent: 解决计算逆的问题
- Stochastic gradient descent: 解决需要所有sample的问题，只选取batch
# References
Matrix Cookbook https://www.math.uwaterloo.ca/~hwolkowi/matrixcookbook.pdf

Stanford CS229 https://cs229.stanford.edu/syllabus-fall2020.html
