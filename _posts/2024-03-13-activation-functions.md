---
title: 'Activation Functions'
date: 2024-03-13
permalink: /posts/2024/03/activation-functions/
tags:
  - machine learning
  - deep learning
  - learning notes
---

激活函数（Activation Function），负责将神经元的输入映射到输出端，激活函数将神经网络中将输入信号的总和转换为输出信号。激活函数大多是非线性函数，才能将多层感知机的输出转换为非线性，使得神经网络可以任意逼近任何非线性函数，进而可以应用到众多的非线性模型中。


Sigmoid Family
======
$$sigmoid(x) = \frac{1}{1+e^{-x}}$$

Hard Sigmoid
------
$$$$

Swish
------
$$swish(x) = x\cdot sigmoid(x) = \frac{x}{1+e^{-x}}$$

Maxout
------


ReLU Family (Rectified Linear Unit)
======
$$ReLU(x) = max(0,x)$$
- Dying neuron
- Handles the vanishing gradient issue
- Cannot avoid exploding gradient issue

ELU
------
$$ELU(x) = \left\{
\begin{aligned}
x,\ if\ x\ \geq 0 \\
\alpha(e^x-1),\ x<0
\end{aligned}
\right.$$

- Avoids dying neuron issue
- Cannot avoid exploding gradient
- Computational expensive (because of exponantial calculation)
- $\alpha$ is an hyper-parameter (normally, $\alpha$ between 0.1 and 0.3)

Leaky ReLU
------
$$LeakyReLU(x) = \left\{
\begin{aligned}
x,\ if\ x\ \geq 0 \\
\alpha x,\ x<0
\end{aligned}
\right.$$

- Avoids dying neuron issue
- Not computational expensive
- $\alpha$ is an hyper-parameter (normally, $\alpha$ between 0.1 and 0.3)

SELU (Scaled Exponential Linear Units)
------
$$SELU(x) = \left\{
\begin{aligned}
\lambda x,\ if\ x\ \geq 0 \\
\lambda \alpha (e^x-1),\ x<0
\end{aligned}
\right.$$
$\alpha \approx 1.6733$, $\lambda \approx 1.0507$.

GELU (Gaussian Error Linear Unit)
------
$$GELU(x) = xP(X\leq x) = x\Phi(x) = x\cdot\frac{1}{2}[1+erf(\frac{x}{\sqrt(2)})]$$
if $X \sim \mathcal{N}(0,1)$.

- GELUs are used in GPT-3, BERT, and most other Transformers.

Tanh Family
======
$$Tanh(x) = \frac{e^x-e^{-x}}{e^x+e^{-x}}$$
- Vanishing gradient problem
- Symmetric about the origin

HardTanh
------
$$HardTanh(x) = \left\{
\begin{aligned}
-1,\ if\ x < -1\\
x,\ if\ -1\leq x\leq 0\\
1,\ if x>1
\end{aligned}
\right.$$

- It is a cheaper and more computationally efficient version of the tanh activation.

TanhShrink
------

Softmax
======

LogSoftMax
------

Softmin
------
