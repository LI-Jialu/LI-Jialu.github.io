---
layout: post
title: Gaussian Process for Machine Learning
date: 2023-10-03 16:20:00 +/-5000
categories: [Math]
tags: [machine learning, gaussian process ]     # TAG names should always be lowercase
---


## Intuition 
For most ML model, input -> **single number** of prediction. 
But, GP model, input -> **certainty** of prediction 

When dealing with machine learning problems, we can have two approaches: 
- assumption of **one** kind of the function: e.g., linear 
  
&rarr; problems: richness of functions 
- give prior porbability of **every possible functions**, and higher probability for more likely functions 
  
&rarr; problems: uncountably inf possible functions 

&rarr; solution: Gaussian Process

### A quick recap of Gaussian Process 
将高斯过程视为正态分布的无限维扩展。正如正态分布描述了一个随机变量的行为，高斯过程描述了一个随机函数的行为。

高斯分布（正态分布）：
一个随机变量 \(X\) 如果遵循高斯分布，其概率密度函数为：
\[p(x∣μ,σ^2) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x-μ)^2}{2\sigma^2}\right)\]
其中，
- \(μ\) 是均值。
- \(σ^2\) 是方差。
这是一个定义在实数上的概率分布，描述了一个随机变量的分布，取值在整个实数轴上。

高斯过程：
一个随机函数 \(f(x)\) 如果遵循高斯过程，其定义为：
\[f(x) \sim \mathcal{GP}(m(x), k(x, x'))\]
其中，
- \(m(x)\) 是均值函数，给定输入 \(x\)，它给出了函数的期望输出。
- \(k(x,x')\) 是协方差函数或核函数，描述了两个输入 \(x\) 和 \(x'\) 对应的函数值之间的协方差。核函数的选择决定了函数的平滑度、周期性等属性。
对于任意有限集合的输入点 \(x_1, x_2, ..., x_n\)，其对应的函数值 \(f(x_1), f(x_2), ..., f(x_n)\) 的联合分布是多元高斯分布，其均值向量由均值函数给出，协方差矩阵由核函数给出。
这是一个定义在函数空间上的分布，为每一个可能的函数赋予了一个概率。

高斯过程（GP）是一个定义在函数空间上的分布，为每一个可能的函数赋予了一个概率。当有一个从高斯过程中抽取的函数时，我们的意思是这个函数的任何有限集合的点都遵循多元高斯分布。

有限数量的点上进行推断，我们实际上是在查看这些点上函数值的联合分布。由于高斯过程的定义，这些点的联合分布是一个多元高斯分布。

当我们知道某些点的函数值时，这些已知点和任何新点之间的协方差（由核函数定义）决定了新点的分布。无论函数空间有多大或有多少其他点，只要我们知道了有限数量的点的值和它们与新点的协方差，我们就可以进行推断。

无限多的点：尽管高斯过程是在整个函数空间上定义的（即无限多的点），但我们实际上只关心我们观察到的点或我们想要进行预测的点。其他所有的点，尽管它们是无限的，对我们的推断没有直接的影响。
