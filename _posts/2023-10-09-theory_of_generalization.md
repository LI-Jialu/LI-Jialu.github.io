---
layout: post
title: Theory of generalization
date: 2023-10-09 20:08:02 +/-5000
categories: [ML]
tags: [generalization]     # TAG names should always be lowercase
---

# Theory of Generalization 

## Intuition 
The final aim of our learning process is: 

$$
E(h) := E_{te}(h) := E_{out}(h) \approx 0
$$

It's achieved through: $E_{tr}(h) \approx 0$  and $E(h) \approx E_{tr}(h)$. 

First, $E_{tr}(h) = \frac{1}{N} \sum_{n=1}^N e(h(x_n), f(x_n))\approx 0$ is achived using optimization as we discussed before. 

Second, $E(h) = \frac{1}{M} \sum_{m=1}^M e(h(x_m), f(x_m))\approx E_{tr}(h)$ will be further discussed here. 

## Start from Hoffeding equations 

## Dichotomy 

## Growth Function 

## VC Dimension 

## Break Point 