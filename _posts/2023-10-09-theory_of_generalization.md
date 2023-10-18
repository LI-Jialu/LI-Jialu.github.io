---
layout: post
title: ML Theory of generalization
date: 2023-10-09 20:08:02 +/-5000
categories: [ML]
tags: [generalization]     # TAG names should always be lowercase
---

# Theory of Generalization 

## Intuition 
The final aim of our learning process is to minimize the genralization error, which is exactly the test error. 

Here are two steps needed to achieve it: 

1. $E_{tr}(h) = 0$ 

    $E_{tr}(h) = \frac{1}{N} \sum_{n=1}^N e(h(x_n), f(x_n))$
    - We try to achieve the first step using optimization, talked before. 

2.  $E(h) = E_{tr}(h)$ 
   
    $E_{te}(h) = \frac{1}{M} \sum_{m=1}^M e(h(x_m), f(x_m))$
    
    $E(h) = \mathbb{E}_{x \sim \mathcal{D}}[e(h(x), f(x))] = E{te}(h)$

    - So, this topic will focus on this step. 
