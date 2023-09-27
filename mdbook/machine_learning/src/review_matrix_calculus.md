# Matrix Calculus

## Conclusion 
### Scalar to vector: the same shape as vector 
$f$ is a scalar valued function, $x \in R^{p\times 1}$

Gradient: 
$$ \frac {\partial f}{\partial x} = [\frac {\partial f}{\partial x_1}  \frac {\partial f}{\partial x_2} ... \frac {\partial f}{\partial x_p}]^T$$
Derivative:  
$df$应该是个scalar，而gradient是$p\times1$ 的vector，所以应该transpose之后相乘，表示在各个方向上的变化量之和
$$df = \sum_{i=1}^{n} \frac{\partial f}{\partial x_i} dx_i = \frac{\partial f^T}{\partial x} dx $$
### Vector to scalar: the same shape as vector 
$f$ is a $R^{m\times1}$ vector valued function, $x \in R$
$$ \frac {\partial f}{\partial x} = [\frac {\partial f_1}{\partial x}  \frac {\partial f_2}{\partial x} ... \frac {\partial f_m}{\partial x}]^T$$
### Vector to vector 
这里的表达式只表示形状
$$\frac{\partial R^{m\times1}}{\partial R^{p\times1}} =  R^{p\times m} $$ 

### Scalar to matrix: the same shape as matirx 

### Matrix to scalar: the same shape as matri 

## 
