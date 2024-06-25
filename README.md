# SARIMAX (Seasonal AutoRegressive Integrated Moving-Average with eXogenous Regressors) Model

## Introduction

This project demonstrates the application of SARIMAX (Seasonal AutoRegressive Integrated Moving-Average with eXogenous Regressors) and ARIMA (AutoRegressive Integrated Moving Average) models for time series forecasting using candy production data. SARIMAX is an extension of ARIMA that includes seasonal components and exogenous variables, making it suitable for complex and multivariate time series data.

## When to Use SARIMAX

- **Seasonal Data**: SARIMAX is appropriate for time series data that exhibits seasonality. It extends the ARIMA model to capture seasonal effects with seasonal AR, I, and MA components.
- **Multivariate Time Series**: SARIMAX can incorporate exogenous variables (additional predictors), which can improve forecasting accuracy if there are external factors influencing the time series.
- **Complex Structures**: When your data exhibits both seasonal patterns and non-seasonal patterns, SARIMAX can capture these complexities.

## When to Use ARIMA

- **Non-Seasonal Data**: ARIMA is suitable for time series data that does not exhibit seasonality. It can handle trends and non-stationary data by differencing.
- **Univariate Time Series**: ARIMA models are designed for univariate time series, where you are modeling and forecasting a single variable.
- **Simple Structures**: When your data can be well-modeled with just AR (autoregressive) terms, I (integrated, or differencing) terms, and MA (moving average) terms.

## Dataset

The dataset used in this project contains monthly candy production data. The data can be accessed [here](https://github.com/viniciusov/candy-production/blob/master/candy_production.csv).

## Exploratory Data Analysis

### Loading and Visualizing Data

The initial step involves loading the data and converting the `observation_date` column to a datetime format. The time series is then plotted to observe trends and patterns over time.

### Seasonal Decomposition

The seasonal decomposition is performed to separate the data into trend, seasonal, and residual components. This helps in understanding the underlying structure of the time series.

### Stationarity Check

The stationarity of the time series is checked using the Augmented Dickey-Fuller (ADF) test. If the series is non-stationary, transformations such as differencing and log scaling are applied until stationarity is achieved.

## Model Building

### ARIMA Model

The ARIMA model is built and trained using the training dataset. The model parameters (p, d, q) are selected based on the Partial Autocorrelation Function (PACF) and Autocorrelation Function (ACF) plots. 

#### Training and Prediction

The ARIMA model is fitted to the training data and used to predict future values. The predictions are compared with the test data, and the Mean Squared Error (MSE) is calculated to evaluate the model's performance.

### SARIMAX Model

The SARIMAX model is built by incorporating seasonal components (P, D, Q, S) along with the ARIMA components (p, d, q). This model captures both seasonal and non-seasonal patterns in the data.

#### Training and Prediction

The SARIMAX model is fitted to the training data and used to make predictions for the test period. The predictions are evaluated using the MSE metric.

## Model Evaluation

The performance of both ARIMA and SARIMAX models is evaluated by comparing the predicted values with the actual test data. The evaluation metrics such as MSE are calculated to assess the accuracy of the forecasts.

## Conclusion

This README provides an overview of applying ARIMA and SARIMAX models to time series forecasting. While ARIMA is suitable for non-seasonal and univariate time series, SARIMAX is more powerful for handling seasonal and multivariate data, capturing complex patterns and improving forecasting accuracy.

