---
title: KIAA Intern
date: 2017-11-13 12:24:16
tags: [KIAA Intern]
comment: true
mathjax: true
---
# KIAA Intern
[toc]
## Matrix Calculate
>Reference
>J.H.Wilkinson: Rounding errors in algebraic process
>矩阵分析与应用 张贤达
>
>
>
>
>
>
>
>

$$\frac{\partial \| C \|}{\partial C_{ij}}=det(C)Tr[C^{-1}\frac{\partial C}{\partial C_{ij}}]$$



$$Tr[C^{-1}\frac{\partial C}{\partial C_{ij}}]=C^{-1}_{ii}$$



$$\frac{\partial C^{-1}}{\partial C_{ij}}=-C^{-1}\frac{\partial C}{\partial C_{ij}}C^{-1}$$



$$\Lambda=-\frac{1}{2}\ln{\|C\|}-\frac{1}{2} X^T C^{-1}$$



$$\delta \Lambda_{ij}=\frac{\partial \Lambda}{\partial C_{ij}}\delta C_{ij}=(-\frac{1}{2}C^{-1}_{ji}+\frac{1}{2}X^{T}C^{-1}V_{ij}C^{-1}X)\delta C_{ij}$$



>$$V_{ij}=\frac{\partial C}{\partial C_{ij}}$$

## Rounding error analysis of matrix inversion
Use $CX=I$ to calculate inversion of C, X is inversion of C.
if C is not singular then we have

![Screen Shot 2017-07-07 at 4.25.30 P]({{site.baseurl}}/assets/img/Screen%20Shot%202017-07-07%20at%204.25.30%20PM.png)

so the relative error for matrix C is less than $\rho \kappa (C)\epsilon$, where $\rho $ is usually less than 10, $\epsilon$ is the machine precision.

## 矩阵奇异上述方法用不了，转战SVD
$$\Lambda=-\frac{1}{2}\ln{|C|}-\frac{1}{2}X^TC^{-1}X$$



$$C=USV^{T}$$



$$C^{-1}=VS^{-1}U^{T}$$



$$\Lambda=-\frac{1}{2}\sum \ln (S_{i})-\frac{1}{2}Y^{T}S^{-1}Y$$



where $Y=U^{T}X$ and because the matrix C is symmetric so $U=V$
So we have
$$\Lambda =-\frac{1}{2}\sum \ln (S_{i})-\frac{1}{2}\sum\frac{y_i^2}{S_i}  $$



$$\delta \Lambda = -\frac{1}{2}\sum\frac{\delta S_i}{S_i}+\frac{1}{2}\sum \frac{y_i^2}{S_i^2}\delta S_i$$



where we let $\Delta_i = \frac{\delta S_i}{S_i}$, so 



$$\delta \Lambda = -\frac{1}{2}\sum \Delta_i + \frac{1}{2}\sum \frac{y_i^2}{ S_i}\Delta_i$$

For $Y=U^TX$ and $X$ satisfies $<X^TC^{-1}X>=1$, so we have the expectation of $\delta \Lambda$
$$<\delta \Lambda> = 0$$






