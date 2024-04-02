---
title: 'Clustering alrogithms'
date: 2024-03-14
permalink: /posts/2024/03/stochastic-gradient-descent/
tags:
  - machine learning
  - deep learning
  - learning notes
---

gradient descent, stochastic gradient descent, batch gradient descent

Improvements for gradient descent
======
Momentum (惯性保持)
------
$$v_t = \gamma v_{t-1}+ \eta g_t$$
$$\theta_{t+1} = \theta_{t}-v_t$$

- 学习速率$\eta$乘当前梯度$g_t$.
- 带衰减的前一次的步伐$v_{t-1}$.

AdaGrad (环境感知)
------
采用“历史梯度平方和”来衡量不同参数的梯度和稀疏性（取值越小越稀疏）

Adam (惯性保持+环境感知)
------
- 梯度的一阶矩 (first moment)：过往梯度与当前梯度的平均 -> 惯性保持
- 梯度的二阶矩 (second moment)：过往梯度平方与当前梯度平方的平均 -> 环境感知，为不同参数产生自适应的学习速率