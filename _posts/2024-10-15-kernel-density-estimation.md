---
title: 'Kernel Density Estimation'
date: 2024-10-15
permalink: /posts/2024/10/kernel-density-estimation/
tags:
  - data science
  - statistics 
  - machine learning
---

It has been a while since I last took some learning notes - I have been buried in work and trying to figure out a balance, and wasting my time ... 

Anyway, from a recent project I learned about KDE and I realized that I did not even know this very basic knowledge. 

Kernel Density Estimation
======
If I was to analyze the distribution of a newly given dataset, the first thing came to my mind was to visualize with some scatter plots (if possible, i.e. low dimensionality). The histogram only comes to my mind later on. However, we are all aware that histogram shapes changes with the choice of the grid size. 

Kernel Density Estimation (KDE) is a nonparametric model used for estimating probability density distributions. It can be used to get a smooth PDF (probability density function) from the data. 

Nonparametric Estimation
------

Nonparametric estimation does not assume that data is drawn from a known distribution. 
Rather, nonparametric models determine the model structure from the underlying data.
Some examples of nonparametric models include:
- Histograms and kernel density estimation.
- Nonparametric regression.
- K-nearest neighbor algorithms.
- Support vector machines.

The univariate case (1 variable):
------

$$\hat{f}(x,h) = \frac{1}{N}\sum_{i=1}^{N}K_{h}(x-x_{i})$$
Basically, we center a smooth scaled kernel function at each data point and then take their average.  

$$\hat{f}_{h}(x) = \frac{1}{Nh}\sum_{i=1}^{N}K(\frac{x-x_{i}}{h})$$
- $K$ is the kernel (a simple non-negative function like the normal or uniform distribution)
- $h$ is the bandwidth (a real positive number that defines smoothness of the density plot)
  - For each $x_{i}$, draw a normal distribution $N(x_{i}, h^2)$ (mean: $x_{i}$, variance: $h^2$)
  - A *small* bandwidth leads to *undersmoothing*; A *huge* bandwidth leads to *oversmoothing*.

The Gaussian kernel is one of the most commonly used one:
$$K(u)=\frac{1}{\sqrt{2\pi}}exp(-\frac{u^2}{2})$$

The intuition behind KDE is straightforward -- the more data points in a sample that occur around a location, the higher the likelihood of an observation occurring at that location.

The Bivariate case (2 variables):
------

$$\hat{f}(\mathbf{x},\mathbf{H}) = \frac{1}{N}\sum_{i=1}^{N}K_{\mathbf{H}}(\mathbf{x}-\mathbf{x_{i}})$$

Reference:
------

[1] [A gentle introduction to kernel density estimation](https://ekamperi.github.io/math/2020/12/08/kernel-density-estimation.html)
[2] [The Fundamentals of Kernel Density Estimation](https://www.aptech.com/blog/the-fundamentals-of-kernel-density-estimation/)
[3] [The importance of kernel density estimation bandwidth](https://aakinshin.net/posts/kde-bw/)