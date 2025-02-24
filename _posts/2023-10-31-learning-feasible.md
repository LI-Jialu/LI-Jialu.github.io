---
layout: post
title: Is Learning Feasible? 
date: 2023-10-31 20:08:02 +/-5000
categories: [ML]
tags: [roadmap]     # TAG names should always be lowercase
---

## Intuition: The map of learning 


![Desktop View](/assets/atch/20231031/learning_diagram.png){: width="300" }

- $f: x$ &rarr; $y$:  this is the ground truth target function 
- $\mathcal{H} = \{h\}$ : the hypothesis set, e.g., linear functions, perceptron or SVM
- $g \in \mathcal{H}$ : this is the function we can learn/achieve to approximate $f$, which is chosen from the hypothesis set 
- $\mathcal{A}$: the learning algorithm, e.g., backpropagation 

## What is a learning model? 
The learning model is made up from 1) the hypothesis set 2) the learning algorithm 

|the hypothesis set | the learning algorithm | 
|-|-| 
|perceptron| PLA| 
|SVM| quadratic programming| 
|neural network| backpropagation| 

## How to apply Hoeffding Equation to learning? 
The Hoeffding Inequality: 

$$
P[|E_{out}(h)-E_{in}(h)| > \epsilon] \leq 2e^{-2 \epsilon^2 N} 
$$

This equation can be directly applied to verification or testing, when there is only 1 hypothesis. 

But it can't be directly applied to training, because we are searching in multiple hypothesis set to find the best hypothesis which gives smallest $E_{in}$. 

Let's suppose there are $M$ hypothesis set, and upon searching, we succesfully find one hypothesis $g$ gives small $E_{in}$. 

Even though the hypothesis seems to be good enough in sampels, but we still have to bound its out-sample performance. 

So, here comes the LHS of the Hoeffding Inequality

$$
LHS = P[|E_{out}(g)-E_{in}(g)| > \epsilon] 
$$

However, its bounding ability is diluted due to multiple experiment. 

$$
P[|E_{out}(g)-E_{in}(g)| > \epsilon] \leq \\ P[|E_{out}(h_1)-E_{in}(h_1)| > \epsilon \\ \textbf{ or } |E_{out}(h_2)-E_{in}(h_2)| > \epsilon \\ \ldots \\  \textbf{ or }|E_{out}(h_M)-E_{in}(h_M)| > \epsilon]
$$

Finally, the most pessimistic assumption, nothing overlap for these $M$ hypothesis. 

The final verdict is: 

$$
P[|E_{out}(h)-E_{in}(h)| > \epsilon] \leq M 2e^{-2 \epsilon^2 N} 
$$
