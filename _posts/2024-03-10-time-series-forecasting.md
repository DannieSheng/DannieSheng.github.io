---
title: 'Time-series Forecasting'
date: 2024-03-10
permalink: /posts/2024/03/time-series-forecasting/
tags:
  - machine learning
---

ARIMA (Autoregressive Integrated Moving Average)
======
It is a popular statistical analysis model used for forecasting time series data. 
ARIMA models are especially well-suited for short to medium-term forecasting models that have data with trends, seasonality, or cyclic patterns. 
The model aims to describe the *autocorrelations* in the data.

Description
-----
ARIMA models are characterized by three key parameters: (p, d, q).
- AR (p) - Autoregression:  
An autoregression model is a regression of the variable against itself. The "p" parameter represents the number of lag observations included in the model, also known as the lag order. It captures the relationship between an observation and a specified number of lagged observations (i.e., previous time steps).
- I (d) - Integrated:  
Differencing involves subtracting the previous observation from the current observation to make the time series stationary. The "d" parameter represents the degree of differencing required to make the time series stationary, i.e., the number of times the data have had past values subtracted. Stationarity is a crucial aspect of time series analysis, as it ensures that the statistical properties of the series (mean, variance) do not change over time.
- MA (q) - Moving Average:  
A moving average model uses past forecast errors in a regression-like model. The "q" parameter represents the size of the moving average window, also known as the order of moving average. It captures the relationship between an observation and a residual error from a moving average model applied to lagged observations.

Strengths
-----
- Flexibility: ARIMA models can be configured to model a wide range of time series data.
- Interpretability: The components of ARIMA (AR, I, MA) have a clear interpretation, making it easier to understand the model dynamics.
- Forecasting Accuracy: For many practical forecasting problems, especially those with data showing trends and seasonality, ARIMA models provide robust and reliable forecasts.

Model Identification and Fitting
------
The process of developing an ARIMA model typically involves several steps:

1. Identification: Determine whether the time series is stationary and identify the order of differencing (d) needed. This often involves using plots and statistical tests (e.g., Augmented Dickey-Fuller test) to check for stationarity.

2. Estimation of p and q: Use plots (like the Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF)) to decide the AR (p) and MA (q) terms.

3. Model Fitting: Use statistical software to fit the ARIMA model with the identified parameters.

4. Diagnostic Checking: Evaluate the model fit by analyzing the residuals to ensure there are no patterns (autocorrelation) left unexplained.

5. Forecasting: Use the model to make forecasts.

AutoARIMA
======
Description
------
AutoARIMA stands for "Automatic Autoregressive Integrated Moving Average." It is an extension of the ARIMA model that automatically selects the best combination of (p, d, q) parameters for the ARIMA model based on the given time series data. It does this by evaluating various combinations and selecting the one that minimizes a given metric, typically AIC (Akaike Information Criterion).

Strengths
------
Highly versatile and capable of modeling a wide range of time series data with or without seasonal components. Auto-tuning of parameters simplifies the modeling process.

Use Cases
------
Ideal for univariate time series forecasting where data shows patterns of autocorrelation, seasonality, and trends.

NaiveSeasonal
======
Description
------
NaiveSeasonal is a simple forecasting method that assumes the seasonal patterns will repeat at a fixed frequency. The forecast for a future time point is simply the value from the last observed cycle.

Strengths
------
Extremely simple and fast, requiring no model training. Works well when the time series has a strong and consistent seasonal pattern.

Use Cases
------
Best suited for time series with clear, stable seasonal patterns and when simplicity and speed are prioritized over precision.

3. Prophet
Description: Developed by Facebook, Prophet is designed for forecasting with daily observations that display patterns on different time scales. It works well with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend.
Strengths: Handles outliers well, and its additive model makes it more flexible than multiplicative approaches. It can incorporate holidays and events, making it suitable for more complex scenarios.
Use Cases: Ideal for daily time series with multiple seasonality patterns, holidays, and events. Useful in business metrics forecasting, such as sales and website traffic.

4. ExponentialSmoothing
Description: Exponential Smoothing models data by applying exponentially decreasing weights over time. It includes Simple Exponential Smoothing, Holt’s Linear Trend method, and Holt-Winters Seasonal method, allowing it to handle time series data with and without trends and/or seasonal components.
Strengths: Versatile, with the ability to model time series data with various combinations of trend and seasonality. Parameters can be optimized to fit a wide range of time series patterns.
Use Cases: Applicable to a broad range of time series data, especially when the data exhibits trends and seasonality. Useful in inventory demand forecasting.

5. NaiveDrift
Description: NaiveDrift is a simple forecasting method that assumes a linear trend (drift) based on the change between the first and last observation. The forecast is then a continuation of this trend into the future.
Strengths: Simplicity and speed, with no need for model training. Can capture linear trends in the data.
Use Cases: Suitable for time series with a linear trend and when a quick, simple baseline model is needed for comparison.