# Stock-Price-Prediction-Model
Stock Price Prediction using ARIMA and Lstm

# Introduction
Stock price prediction is a critical task in finance, involving the use of historical stock price data to forecast future values. This project focuses on stock price prediction using implementation of ARIMA(AutoRegressive Integrated Moving Average) and LSTM(Long Short Term Memory) models.

# Dataset
The dataset consists of historical stock prices, including the date and closing prices of a particular stock. The Dataset in split intop training, validation and test sets.

# Model Implementation
## ARIMA
To implement ARIMA model, the time series must be stationary (having constant mean and variance over time) to apply the ARIMA model effectively. The Augmented Dickey-Fuller (ADF) test is used to check the stationarity of the series. The ADF test results include the test statistic, p-value, number of lags used, and critical values for different confidence levels. If the test statistic is less than the critical value, the null hypothesis of non-stationarity is rejected.

However, the time series is not stationary. So to make the series stationary, the first difference of the series is computed.

The ARIMA model is implemented using the training data with paramteters (1,1,1). Predictions are made for each point in the test set, and the true values are added to the history to update the model iteratively.

The performance of the model is evaluated using the Mean Absolute Error (MAE).

## LSTM
Long Short-Term Memory (LSTM) networks, a type of recurrent neural network (RNN), are particularly suited for time series forecasting due to their ability to capture long-term dependencies.

To train the data on LSTM and to improve its performance, the data is normalized. Then a windowed dataset is created for training and validation. For this code, a 30 day window is implemented.

The LSTM model is implemented with two LSTM layers followed by a Dense layer. The model is trained on the dataset using early stopping and Nadam optimization.

After training the model is used to make predictions on the test set and unscale the forecasted values. The model is then evaluated using Mean Absolute Error.

# Results
After training and evaluation the model give the following results-  
ARIMA - MAE: 1.5146  
LSTM - MAE: 27.7485


