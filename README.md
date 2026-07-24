# Brent Crude Oil Price Forecasting

## Overview
This project aims to analyze and forecast Brent Crude Oil closing prices using various time series forecasting algorithms. Brent Crude Oil is a major indicator of global economic conditions, making accurate price prediction crucial for risk minimization and decision-making. The study utilizes historical daily closing prices from October 9, 2023, to April 30, 2026.

## Data
The dataset consists of historical Brent oil futures price data. The primary variable used for time series modeling is the daily closing price (`Terakhir`).
- **Data Range:** October 9, 2023 – April 30, 2026
- **Frequency:** Daily
- **Target Variable:** Closing Price (USD/Barrel)

### Data Preprocessing
- Sorted data chronologically (ascending order).
- Selected the `Tanggal` (Date) and `Terakhir` (Closing Price) columns.
- Checked for and confirmed no missing values.
- Converted the closing price variable into a time series object using the `ts()` function.
- Split data into **80% Training** (528 observations) and **20% Testing** (132 observations).

## Exploratory Data Analysis (EDA)
- **Price Trend:** Prices fluctuated dynamically, ranging from a low of ~$59 to a high of ~$118. A downward trend was observed between 2023 and 2025, followed by a sharp surge in 2026.
- **Distribution:** The price distribution is positively skewed, with most prices concentrated between $60 and $85 per barrel.
- **Outliers:** Mild and extreme outliers were identified, primarily associated with the sharp price increases.

## Models Evaluated
Several time series forecasting models were developed and compared to determine the best predictive performance:
1.  **Naive Forecast:** Used as a baseline benchmark.
2.  **Double Moving Average (DMA):** Evaluated with different window sizes (n=3, 4, 6, 7, 8).
3.  **Double Exponential Smoothing (DES):** Tested with various alpha and beta smoothing parameters.
4.  **Time Series Regression:** Explored models incorporating Trend, Lag 1, and Lag 9 features.
5.  **ARIMA:** Identified **ARIMA(2,1,2)** as the best fit based on stationarity tests (ADF), Box-Cox transformation, and ACF/PACF analysis.
6.  **MLP:** Evaluated with different hidden layer
7.  **LSTM:** Explored model with different layer and hidden unit
8.  **GRU:** Explored model with different layer and hidden unit

## Evaluation Metrics
Model performance was evaluated on the out-of-sample testing data using the following metrics:
- Root Mean Squared Error (RMSE)
- Mean Squared Error (MSE)
- Mean Absolute Percentage Error (MAPE)

## Results & Conclusion
The Gated Recurrent Unit (GRU) is the BEST PERFORMING MODEL. It achieves the lowest forecasting errors across all evaluation metrics. It produces the lowest RMSE and MSE values among all evaluated models. This indicates that its forecasts are closest to the actual observations, resulting in the smallest prediction errors. The model effectively learns complex nonlinear relationships in the Brent oil price series allows it to generate more accurate predictions with minimal error.

## Tools & Libraries Used
- **Language:** R, Python
- **Libraries:** `readxl`, `dplyr`, `ggplot2`, `lubridate`, `tseries`, `car`, `forecast`, `zoo`, `lmtest`, `nortest`, `tidyr`, `pandas`, `tensorflow`

## Author
1. Sanly
2. Zahra Annisa Afandi
