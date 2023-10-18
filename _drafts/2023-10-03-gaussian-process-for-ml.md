---
layout: post
title: Gaussian Process for Machine Learning
date: 2023-10-03 16:20:00 +/-5000
categories: [Math]
tags: [machine learning, gaussian process ]     # TAG names should always be lowercase
---


## Intuition 
When dealing with machine learning problems, we can have two approaches: 
- assumption of **one** kind of the function: e.g., linear 
  
&rarr; problems: richness of functions 
- give prior porbability of **every possible functions**, and higher probability for more likely functions 
  
&rarr; problems: uncountably inf possible functions 

&rarr; solution: Gaussian Process