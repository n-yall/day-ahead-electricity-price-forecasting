# Day-Ahead Electricity Price Forecasting for Jeju Island

## Project Overview
This project aims to predict the day-ahead electricity price for Jeju Island given weather forecast data, actual weather data, electricity supply data, and price data.

## Implementation
This project uses the Lasso Estimated AutoRegressive (LEAR) model to predict day-ahead electricity prices. The code for this project is based on the implementation from **Forecasting day-ahead electricity prices: A review of state-of-the-art
algorithms, best practices and an open-access benchmark**. The key difference is that when considering the lag for price and exogenous variables (exogenous1, exogenous2), this project considers the lag for 1, 2, and 3 days for price, and only 1 day for exogenous variables.

## Considerations & Notes
Forecasting day-ahead electricity prices often involves predicting day-ahead electricity supply and load. To achieve this, weather data was used to predict day-ahead supply and load, and the correlation between weather data and supply-load data was analyzed.

Despite these efforts, the predicted supply and load values were not incorporated into the final price prediction model due to the following reasons:
1. The accuracy of day-ahead supply and load predictions was not high enough.
2. Even when using the actual supply and load data (available only on the target day), including these values in the model resulted in lower prediction accuracy compared to models that excluded supply-load data for the target day.

As a result, supply-load data for the target day was excluded from the final price prediction model.

## References
1. Lago, Jesus, et al. "Forecasting day-ahead electricity prices: A review of state-of-the-art algorithms, best practices and an open-access benchmark." Applied Energy 293 (2021): 116983.
