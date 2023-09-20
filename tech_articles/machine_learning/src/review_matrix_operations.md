# Review: Matrix Operations
## Norm 
**Vector norm:** general form:
$$
\|x\|_{p}=\left(\sum_{i=1}^{n}|x_{i}|^{p}\right)^{1/p}
$$

$l_1$ norm: 
$$||x||_1 = \sum_{i=1}^{n}x_i $$

$l_2$ norm: Euclidean 可以理解为向量的长度或大小
$$||x||_2 = \sqrt{\sum_{i=1}^{n}x_i^2}$$

$l_\infty$ norm: max $x_i$
$$||x||_\infty|| = max_i |x_i|$$ 


**Matrix norm:** i.e. Frobenius norm 也可以理解为矩阵的长度或者大小
$$ ||A||_F = \sqrt{\sum_{\bar{i}=1}^{m}\sum_{\bar{j}=1}^{n}\mathcal{A}_{ij}^{2}} = \sqrt{\mathrm{tr}(A^{T}A)} $$ 
