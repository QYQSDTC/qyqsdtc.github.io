---
layout: post
title: Hamilton's Principle
date: 2018-01-09 12:03:20
tags: Physics
comment: true
---
According to Hamilton's Principle 
$$S=\int^{t_2}_{t_1}L(q,\dot q, t)dt$$

should have its limit, therefor the divergence of $S$ is

$$\delta S = \delta \int^{t_2}_{t_1}L(q,\dot q, t) = \int^{t_2}_{t_1}(\frac{\partial L}{\partial q}\delta q + \frac{\partial L}{\partial \dot q}\delta \dot q +\frac{\partial L}{\partial t}\delta t)dt$$



for $\delta t \to 0$ the last term comes zero.

for $\delta \dot q = \frac{d}{dt}\delta q$

the second term goes to

$$\int^{t_2}_{t_1}\frac{\partial L}{\partial \dot q}\delta \dot q dt = \frac{\partial L}{\partial \dot q}\delta q \lvert ^{t_2}_{t_1}-\int^{t_2}_{t_1}(\frac{d}{dt}\frac{\partial L}{\partial \dot q}\delta q)dt$$

for $\delta q(t_1)=\delta q(t_2)=0$
$\delta S$ becomes to
$$\delta S = \int^{t_2}_{t_1}(\frac{\partial L}{\partial q}-\frac{d}{dt}\frac{\partial L}{\partial \dot q})\delta q dt$$

Refer to Hamilton's Principle, $\delta S$ should be zero, therefor we can get the equation:
$$\frac{d}{dt}\frac{\partial L}{\partial \dot q}-\frac{\partial L}{\partial q} = 0$$

