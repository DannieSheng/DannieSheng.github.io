---
title: 'Loss Functions'
date: 2024-03-12
permalink: /posts/2024/03/loss-functions/
tags:
  - learning notes
  - machine learning
  - loss function
---

Regression Loss Functions
======

L1 Loss (Mean Absolute Error, MSE)
------
$$MSE = \frac{\sum_{i=1}^{N}|f(x_{i})-y_i|}{N}$$

L2 Loss (Mean Square Error, MSE)
------
$$MSE = \frac{\sum_{i=1}^{N}(f(x_{i})-y_i)^2}{N}$$

Smooth L1 Loss 
------
$$ SmoothL1 = \left\{
\begin{aligned}
0.5x^2,\ if\ |x|\ <\ 1 \\
|x-0.5|,\ otherwise
\end{aligned}
\right.$$

Huber Loss
------ 
Combines MSE and MAE.


Classification Loss Functions
======
Cross Entropy Loss
------

Binary case:
$$CE(p, y) = \left\{
  \begin{aligned}
  -log(p),\ if\ y\ =\ 1, \\
  -log(1-p),\ otherwise
  \end{aligned}
  \right.$$

$$p_t = \left\{
  \begin{aligned}
  p,\ if\ y=1,\\
  1-p,\ otherwise 
  \end{aligned}
\right.$$
Simplified to
$$CE(p,y) = CE(pt) = -log(pt)$$

Multi-class case:
$$CE(p_i, y_i) = -y_{i,c}log(p_{ic})$$

$$L = \frac{1}{N}\sum_{i}L_i = -\frac{1}{N}\sum_{i}\sum_{c=1}^{M}y_{ic}log(p_{ic})$$

Balanced Cross Entropy Loss
------
$$CE(p_t) = -\alpha_tlog(p_t)$$

Balanced cross entropy loss solves the problem of imbalanced classes, but did not put different focus on hard vs. easy samples. 

Focal Loss
------
$$FL(p_t) = -\alpha_t(1-p_t)^{\gamma}log(p_t)$$
$p_t$ is the model's estimated probability for each class being the correct classification.
$\alpha_T$ is a weighting factor for the class (to further address class imbalance).
$\gamma$ is the focusing parameter that smoothly adjusts the rate at which easy examples are down-weighted. When $\gamma=0$, focal loss is equivalent to cross-entropy loss. As $\gamma=0$ increases, the effect of the modulating factor increases, and the loss contribution from easy examples is reduced.

The key idea behind focal loss is to focus model training on hard, misclassified examples and reduce the relative loss for easy examples, preventing the overwhelming number of easy negatives from dominating the training of the model.

- For well-classified examples (where $p_t$ is high), $(1-p_t)^{\gamma}$ approaches 0, which significantly reduces their contribution to the loss. As a result, the loss for these easy examples becomes negligible, and they have little impact on the model updates during training.
- For misclassified or hard examples (where $p_t$ is low), $(1-p_t)^{\gamma}$ is closer to 1, meaning these examples contribute more significantly to the total loss. This ensures that the model's updates focus more on correcting these harder examples.

Poly Loss
------


Hinge Loss
------
Used in SVM. 
$$L(y) = max(0, 1-t \cdot y)$$

Triplet Loss
------

Contrastive Loss 
------

