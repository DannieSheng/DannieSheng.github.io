---
title: "Time-series forecasting for a payment processing company"
excerpt: "May 2023<br/>
This project is actually a pre-interview project for data scientist. I have got a chance to perform data analysis and time-series modeling and forecasting. <br/>"
collection: portfolio
---

## Background
The business team of a payment processing company is interested in GMV (Gross Merchandise Value: the sum of transaction amounts over a period of time) forecasting. 
GMV can be defined per store (the seller), per user (the purchaser), or for the company as a whole (across all users and stores). 

## Tasks
1. Perform an EDA (exploratory data analysis) to highlight patterns in the data
2. Forecast GMV for **each user** for the month of January 2022
3. Forecast GMV for **the company as a whole** for each date in the month of January 2022

## Data
**transactions**: all transactions for years 2020 and 2021.  
`user_id`: the user ID   
`store_id`: store ID  
`event_occurance`: the datetime of the transaction  
`amount`: the amount of the transaction in yen 

**stores**: characteristics for each store.
`nam`: prefecture  
`laa`: local administrative area  
`category`
`lat`: location in latitude  
`lon`: location in longitude 

**users**: characteristics for each user   
`gender`  
`age`: age as of December 31, 2021  

## Data Analysis, Modeling, and Prediction
### EDA
#### Transaction data (**transactions**)
1. Contains transaction data from 2020-01-01 to 2021-12-31, made by 9542 unique users,
with products provided by 95460 unique stores.
2. An overall increasing trend was observed for daily total transaction amount (daily GMV for the whole company). However, the daily average transaction remains steady with bouncing. This is explained by the observation that the daily transaction numbers is increasing. 
3. A weekday related pattern of total transaction amount is also observed - total transaction amount distributions differ in weekdays and weekends. 
#### User data (**users**)
1. There are 9961 unique users originally, 8965 without missing data (nans).
2. Almost 60% of active users are male; the ages of users range from 15 to 90 with an median of 52 years old.
3. Considering each user's average daily purchase amount, we did observe that different genders and different age groups behave slightly differently. 
#### Store data (**stores**)
1. There are 99991 unique stores with 17 different categories.
2. By taking a look at the relationship between daily transaction amount and category, an obvious relationship in between is observed. 

### Modeling and Forecasting GMV for **each user** for January 2022
To forecast GMV for each user, I proposed to use a **user churn** based method - group users into several groups, and make prediction for each group.
The reason is that the prediction for each user is traivia and not informative - we care about the company as a whole, and knowing our customer groups is of greater importance.  

The RFM model defines users to different level based on 3 scores: *Recency* (to the end of year 2022), *Frequency* and *Monetary*.  
By default, the RFM scores can be calcualted and the users can be grouped into 8 groups based on the scores. But we can use the RFM values as features in our modeling.   

As has been observed in previous steps, products' categories play a vital role in final transaction amount. 
So I proposed to use the ratios of each category's purchasing amount to the monthly purchasing total to define each user.  

Then, a **k-means clustering** method is used to cluster users into 7 clusters (the value of k is determined by silhouette score combined with the elbow method).  

Finally, I proposed to use the last value of the historical average monthly GMV for each user as a forecast for the coming January.  

Alternatively, a time-series forecasting model can be build for each cluster to predict the coming month in 2022.

### Modeling and Forecast GMV for **the company as a whole** for **each date** in January 2022
Forecasting GMV for each date for the whole company is a whole new story compared to the previous task. 
I proposed to use time-series forecasting modeling. 

As observed in the EDA, there is a correlation between weekday and the total GMV amount.  
This observation is substaintiated by checking the seasonality, of the data - "There is seasonality of order 7".  

With available historical data, I split data into train and validation, and tried several models: "naive", "exponential", "arima", "theta", "prophet". 
Based on the performance on validation data, I chose the "prophet" model as my final time-series forecasting model and made the forecasts for each date in January 2022 for the company. 

Checkout the [github repo](https://github.com/DannieSheng/Professional_Portfolio/tree/main/PaypayCoding%20Challenge) of this project for detailed scripts. 
