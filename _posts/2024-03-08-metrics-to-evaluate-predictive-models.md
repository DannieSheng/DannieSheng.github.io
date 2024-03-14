---
title: 'Metrics to Evaluate Predictive Models'
date: 2024-03-08
permalink: /posts/2024/03/metrics-to-evaluate-predictive-models/
tags:
  - evaluation metrics
  - machine learning
---

Metrics used to evaluate predictive modeling, highly used in regression, time-series forecasting cases. 

MAE (Mean Absolute Error)
======
Definition
------
MAE measures the average magnitude of the errors in a set of predictions, without considering their direction.
It's calculated as the average of the absolute differences between the predicted values and the actual values.

Formula
------
$$MAE = \frac{1}{N}\sum_{i=1}^{N}|y_i-\hat{y_i}|$$

Interpretation
------
Lower MAE values indicate better model performance. MAE provides a straightforward measure of prediction accuracy with the same units as the predicted variable.

MSE (Mean Squared Error)
======
Definition
------
MSE measures the average of the squares of the errors—that is, the average squared difference between the estimated values and the actual value.

Formula
------
$$MSE = $$

Interpretation
------
Lower MSE values indicate better model performance. MSE is more sensitive to outliers than MAE because it squares the errors before averaging, which disproportionately penalizes larger errors.

RMSE (Root Mean Squared Error)
======
Definition
------
RMSE is the square root of the mean squared error. 
It measures the standard deviation of the residuals or prediction errors.

Formula
------
$$RMSE$$

Interpretation
------
Lower RMSE values indicate better model performance. RMSE is similar to MSE but is in the same units as the predicted and actual values, making it more interpretable.

R-Squared (Coefficient of Determination)
======
Definition
------
R-Squared is a statistical measure that represents the proportion of the variance for a dependent variable that's explained by an independent variable or variables in a regression model.

Formula
------
$$R^2 
= 1-\frac{\sum_{i=1}^{n}(y_i-\hat{y_i})^2}{\sum_{i=1}^{n}(y_i-\bar{y})^2}
$$

Interpretation
------
R-Squared values range from 0 to 1, where higher values indicate that a greater proportion of variance is accounted for by the model. An R-Squared value of 1 indicates perfect fit.

MAPE (Mean Absolute Percentage Error)
======

Definition
------
MAPE measures the average of the absolute percentage errors by comparing the actual value with the predicted value.

Formula
------ 
$$MAPE = \frac{100\%}{n}\sum_{i=1}^{n}|\frac{y_i-\hat{y_i}}{y_i}|$$

Interpretation
------
Lower MAPE values indicate better model performance. 
MAPE is useful because it provides an error percentage that is easy to interpret, but it can be undefined for values of $y_i = 0$ and can disproportionately penalize underpredictions when $y_i$ is small.

