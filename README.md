# Stock-Market-Analysis

## Introduction
The stock market is the collection of markets where stocks and other securities are bought and sold by investors. Publicly traded companies offer shares of ownership to the public, and those shares can be bought and sold on the stock market.It is also a popular way for individuals to invest and grow their wealth over time.

## Objective
The primary objective of the dataset is to Simulate realistic stock market behavior that provide artificial yet realistic-looking stock prices for use in model development, testing, and education, Enable safe experimentation that allow data scientists, researchers, and students to build, test, and evaluate forecasting models like XGBoost, LSTM, SARIMAX, and Prophet without financial or compliance risks and support algorithmic trading research on facilitate backtesting of trading strategies, signal generation, and time-series modeling in a controlled, risk-free environment.

The focus is on forecasting stock market price, specifically examining stock prices, through comprehensive Time Series analysis

## Evaluated Models
Trained and tuned the following models:
 
- Time series
  - ARIMA
  - SARIMAX
  - LTSM
  - Prophet
- XgBoost

## Highlights

- Augmented Dickey-Fuller
   - P-value should be less than equal to 0.5 indicates time series is not stationary.
   - Test Statistic value should be always less than critical value indicates time series in not stationary
   - P-value is increasing and Test statistic is decreasing it indicates that the evidence against the null hypothesis is weakening.
- Autocorrelation and Partial Autocorrelation
  - The series is likely non-stationary due to the slow decay of autocorrelations.There's no clear seasonality visible in this ACF plot
  - This PACF plot suggests that a simple model like ARIMA(1,d,q) might be suitable. Might also try ARIMA(1,d,1)
  - The rapid decay in partial autocorrelations after lag 1 is a good sign, but doesn't guarantee stationarity. You should still perform formal stationarity tests.

## Performance

⚖️ Accuracy Comparison (RMSE)
  | Model                        | RMSE            |  Notes                                                        | 
  |------------------------------|-----------------|---------------------------------------------------------------|
  | XGBoost                      | 0.36            |  Best performer — beats LSTM                                  | 
  | LSTM(Tuned)                  | 1.4             |  Very strong, especially for deep temporal dependencie        | 
  | SARIMAX                      | 6.30            |  Better for stationary, linear trends                         | 
  | Prophet                      | 13.36           |  Easy to use, but limited in flexibility and accuracy         |   

   ✅ Conclusion: XGBoost outperforms all others, including LSTM, based on RMSE alone.

 🧠 Model Suitability
  | Model        | Handles Non-Linearity     | Captures Long-Term Trends | Complexity | Interpretability     |
  | ------------ | ------------------------  | ------------------------- | ---------- | ----------------     |
  | **XGBoost**  | ✅ Strong                | ⚠️ Limited without lags   | Medium     | ✅ High              |
  | LSTM (Tuned) | ✅✅ Excellent           | ✅✅ Excellent           | 🔺 High    | ❌ Low              |
  | SARIMAX      | ❌ Mostly linear         | ✅ Seasonal/trend capable | Medium     | ✅ High              |
  | Prophet      | ❌ Mostly linear         | ✅ Basic seasonality      | ✅ Low    | ✅✅ Very high       |
 
   ✅ Conclusion: If interpretability and speed matter, XGBoost wins. If you want long-term, deep pattern recognition, LSTM still has unique strengths.
  
## Why the Hybrid Model
- Conclusion: If interpretability and speed matter, XGBoost wins. If you want long-term, deep pattern recognition, LSTM still has unique strengths
- Best Accuracy: Combines strengths of both tree-based and deep learning models, achieving lowest RMSE (~0.30).
- Handles Complexity: LSTM captures nonlinear dependencies, while XGBoost models structured relationships and engineered features.
- Balanced Performance: Offers excellent predictive performance, interpretability, and generalization on future data.
- Without historical data, but assuming normal price movement and based on the model low RMSE (~0.30), price will likely remain close to price, with a slight upward or downward movement depending on trend input

## Recommendation

- After evaluating multiple time series forecasting models — including Prophet, SARIMAX, XGBoost, and a Tuned LSTM — the hybrid XGBoost + LSTM model is recommended for deployment due to its superior accuracy and robustness.
- Deploy the XGBoost + LSTM hybrid model for stock price prediction tasks. This architecture delivers robust, high-accuracy forecasts with flexibility for future enhancements.
- Without historical data, but assuming normal price movement and based on the model's low RMSE (~0.30), price will likely remain close to price, with a slight upward or downward movement depending on trend input
