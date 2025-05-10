# Stock-Market-Analysis

## Introduction
The stock market is the collection of markets where stocks and other securities are bought and sold by investors. Publicly traded companies offer shares of ownership to the public, and those shares can be bought and sold on the stock market.It is also a popular way for individuals to invest and grow their wealth over time.

The focus is on forecasting stock market price, specifically examining stock prices, through comprehensive Time Series analysis

## Objective
Our dataset comes from the Kaggel repository link. The data is from a Stock Market Simulation Analysis and is a collection of the results of marketing analysis. We will make use of the dataset here for more information on the data and features.
To model and simulate stock market behaviors, providing insights into market trends and potential investment strategies for investment decision-making by simulating stock market scenarios, with the goal of identifying patterns, minimizing risk, and improving returns.

-Understanding market behavior through historical data and stochastic simulations.
-Evaluating the performance of hypothetical portfolios or trading strategies over time.
-Providing insights into how different investment strategies might perform under varying market conditions.

## Evaluated Models
Trained and tuned the following models:
 
- Time series
  - ARIMA
  - SARIMAX
  - LTSM
  - Prophet
- Linear Regression

## Performance
 
| Model                        | MSE            | RMSE          | 
|------------------------------|----------------|---------------|
| ARIMA                        | 1.144          | 1.309         | 

## Highlights

- Augmented Dickey-Fuller
   - P-value should be less than equal to 0.5 indicates time series is not stationary.
   - Test Statistic value should be always less than critical value indicates time series in not stationary
   - P-value is increasing and Test statistic is decreasing it indicates that the evidence against the null hypothesis is weakening.
- Autocorrelation and Partial Autocorrelation
  - The series is likely non-stationary due to the slow decay of autocorrelations.There's no clear seasonality visible in this ACF plot
  - This PACF plot suggests that a simple model like ARIMA(1,d,q) might be suitable. Might also try ARIMA(1,d,1)
  - The rapid decay in partial autocorrelations after lag 1 is a good sign, but doesn't guarantee stationarity. You should still perform formal stationarity tests.
