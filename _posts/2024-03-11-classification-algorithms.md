---
title: 'Classification Algorithms'
date: 2024-03-11
permalink: /posts/2034/08/classification-algorithms/
tags:
  - learning notes
  - machine learning
  - loss function
---

Classification Algorithms

Logistic Regression
======

Description
------
$$z = w_0+w_1x_1+w_2x_2+...++w_nx_n$$
Then, the sigmoid function is used to convert z to probability $p$:
$$p = \frac{1}{1+e^{-z}}$$
$p$ can later be converted to binary classification.

Pros
------
1. Easy to implement 
2. Suitable for linear separable cases
3. Result explanable

Cons
------
1. Hard to solve non-linear problems
2. Performance impaired when dealing highly correlated data
3. Sensitive to noisy data
4. Not suitable for classification of more than 2 classes

Decision Tree
======

Description
------
1. Feature selection
2. Tree construction: recursively

Pros
------
1. Easy and explanation
2. Capable of handling both numerical and categorical data
3. No need to prepare data, e.g. normalization

Cons
------
1. Easy to overfit, especially on data with high dimensionality
2. Sensitive to outliers
3. Unstable, small changes of data could result in large changes of the tree structure
4. Not suitable of handling complicated relationship

Suitable for
------
1. Cases where explanability is of essence, e.g. medical diagnosis
2. Small to medium data size
3. Data easy to be splited
4. Feature selection

Random Forest
======

Naive Bayes
======

Description
------

### Assumption:
All features are independent on each other.

$$P(C_k|x) = \frac{P(x|C_k)P(C_k)}{P(x)}$$
$$P(x|C_k) = P(x_1|C_k)P(x_2|C_k)...P(x_n|C_k)$$

K-Nearest Neighbors (KNN)
======
- Classification: majority vote
- Regression: weighted average

Distance Measurements
------
- Euclidean Distance
- Manhattan Distance
- Chebyshev Distance
- Minkowski Distance
- Mahalanobis Distance

Cons:
------
1. Calculation cose
2. Space complexity
3. Imbalanced classes
4. Limited performance on data with high dimensionality
5. Sensitive to noisy data
6. Hard to decide the correct value of k

Support Vector Machine
======
Linear SVM (Hard Margin)
------
$$f(x) = sign(w\cdot x+b)$$

Non-linear (kernel trick)
------
$$f(x) = sign(\sum_{i=1}^{n}\alpha_{i}y_iK(x_i, x)+b)$$

SVM for imbalanced class (Soft Margin)
------

this is very easy to accomplish using the aligned environment from amsmath:

$$
\begin{equation}
\begin{aligned}
\min_{w,b,\xi} \quad & \frac{1}{2}w^{t}w+C\sum_{i=1}^{N}{\xi_{i}}\\
\textrm{s.t.} \quad & y_{i}(w\phi(x_{i}+b))+\xi_{i}-1\\
  &\xi\geq0    \\
\end{aligned}
\end{equation}
$$


Pros:
------
1. Can be used in various cases: text classification, image recognition, etc. 
2. Robust to noisy data points
3. Avoid stucking at local optima
4. Still works in high dimensional space (kernel trick)
5. Avoid over-fitting (by regularization) 

Cons:
------
1. Only work for binary classification case
2. High computation complexity
3. Sensitive to choice of parameter
4. Sensitive to missing data

AdaBoost
======

Gradient Boosting Trees
======

Multilayer Perceptrons
======

Artificial Neural Network