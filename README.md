Weather Forecasting

Dataset-

This weather forecasting dataset appears to contain various meteorological measurements and environmental conditions recorded at different locations over a period of time. Here's some information about the dataset columns:

DATE: The date of the recorded data.
MONTH: The month of the recorded data.
Location-specific columns (e.g., BASEL, BUDAPEST, DE_BILT): These columns contain weather-related measurements specific to each location. The measurements include cloud cover, humidity, pressure, global radiation, precipitation, sunshine duration, and temperature statistics such as mean, minimum, and maximum temperatures.
Other location-specific columns (e.g., DRESDEN, DUSSELDORF, HEATHROW): Similar to the previous set of columns, these also contain weather-related measurements for different locations.
Additional columns: Some additional columns seem to contain weather-related measurements for other locations such as KASSEL, LJUBLJANA, MALMO, etc. These measurements include wind speed, wind gust, humidity, pressure, global radiation, precipitation, and temperature statistics.
Overall, this dataset appears to be comprehensive and suitable for weather forecasting and analysis tasks. It covers a wide range of meteorological variables and spans multiple locations, which could be valuable for various applications such as climate modeling, agricultural planning, and weather prediction.

# Weather Time Series Analysis and Forecasting

## Overview
This project aims to analyze historical weather data and forecast future temperatures using time series analysis techniques and machine learning models. The analysis includes preprocessing the data, checking for stationarity, building LSTM (Long Short-Term Memory) neural network models, and fitting ARIMA (AutoRegressive Integrated Moving Average) models.

## Data Preparation
- Two datasets are used: `weather_prediction_dataset.csv` containing weather data and `weather_prediction_bbq_labels.csv` containing barbecue labels.
- The datasets are loaded into Pandas DataFrames (`df` and `df1`).
- Date columns are converted to datetime format, and the data is resampled to monthly frequency.

## Stationarity Test
- The Augmented Dickey-Fuller (ADF) test is applied to each time series to check for stationarity.
- The ADF test is implemented in the `adf_test` function.
- If the p-value is less than 0.05, the time series is considered stationary.

## Data Modeling
### LSTM Model
- The data is prepared for LSTM modeling by creating input-output pairs using the `create_dataset` function.
- The dataset is standardized using StandardScaler.
- The data is split into training and testing sets.
- An LSTM model is constructed using Keras Sequential API with four LSTM layers followed by a Dense output layer.

### ARIMA Model
- Autocorrelation and partial autocorrelation plots are generated using statsmodels to analyze the autocorrelation structure.
- An ARIMA model is instantiated with parameters (order=(12, 0, 25)) based on the observed autocorrelation structure.
- The ARIMA model is fitted to the training data, and predictions are made for the test period.

## Results
- The results of both LSTM and ARIMA models are visualized against the actual temperature data.
- The performance of the models can be evaluated using appropriate metrics such as Mean Absolute Error (MAE) or Root Mean Squared Error (RMSE).

## Dependencies
- pandas
- numpy
- matplotlib
- statsmodels
- scikit-learn
- keras
- Tensorflow

## Usage
1. Run the provided Python script to load and preprocess the data, build models, and generate forecasts.
2. Modify the script as needed for custom analysis or model tuning.

