# Time Series Analysis and Forecasting Project

## Overview
This project focuses on analyzing and forecasting Brent crude oil prices using various time series methods, including **ARIMA**, **Holt-Winters Exponential Smoothing**, and **Long Short-Term Memory (LSTM)** models. The dataset spans from **May 17, 1987**, to **November 13, 2022**, and is sourced from the [U.S. Energy Information Administration](https://www.eia.gov/).

---

## Objectives
### Data Exploration and Preprocessing
- Import and clean the dataset.
- Aggregate data to monthly averages to reduce noise.

### Time Series Analysis
- Perform seasonal decomposition to extract trend, seasonality, and residual components.
- Evaluate stationarity using the Augmented Dickey-Fuller (ADF) test.

### Forecasting Techniques
- Develop **ARIMA**, **Holt-Winters**, and **LSTM** models to predict oil prices.
- Evaluate model performance using **MAE** and **RMSE** metrics.

### Comparison of Models
- Identify the best model based on accuracy and forecasting ability.

---

## Methodology

### 1. Data Preprocessing
- Loaded and converted the `date` column to a datetime format.
- Resampled data to a monthly frequency and computed the mean price for each month.
- Performed log transformations and differencing to stabilize variance and achieve stationarity.

### 2. Seasonal Decomposition
- Decomposed the time series using additive and multiplicative methods.
- Evaluated trends and seasonal components.

### 3. Forecasting Models

#### ARIMA
- Determined orders \( (p, d, q) \) using ACF and PACF plots.
- Fitted **ARIMA(2,1,1)(0,0,2)[12]** and evaluated using **AIC**, **BIC**, and **Ljung-Box test**.
- Achieved the best performance with the lowest MAE and RMSE.

#### Holt-Winters Exponential Smoothing
- Used additive seasonality to capture trends and seasonal variations.
- Generated forecasts for the next 12 months, showing price fluctuations and market volatility.

#### LSTM
- Scaled data using `MinMaxScaler`.
- Split data into training and testing sets with a 70:30 ratio.
- Built a sequential LSTM model with multiple layers and dropout regularization.
- Evaluated the model using loss plots, MAE, and RMSE.

---

## Results

### ARIMA Model
- **MAE**: 2.97  
- **RMSE**: 4.42  
- Best fit for the dataset with accurate trend and seasonality capture.

### Holt-Winters Model
- **MAE**: 3.01  
- **RMSE**: 4.63  
- Effective in capturing trends but less accurate than ARIMA.

### LSTM Model
- **MAE (Test)**: 9.30  
- **RMSE (Test)**: 10.02  
- Struggled with sudden changes in price, producing smoother predictions.

---

## Conclusion
The **ARIMA** model outperformed **Holt-Winters** and **LSTM** models, providing the most reliable forecasts for Brent crude oil prices. This project demonstrates the effectiveness of statistical models over neural networks for this dataset, given its structured patterns and moderate complexity.

---


