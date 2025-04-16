# StockPricePredcition
1. Data Preprocessing
Load Data: The stock data is loaded from an Excel file.

Clean Column Names: Removed any special characters like * from the column names.

Convert Date: Converts the 'Date' column to datetime format and drops rows with invalid dates.

Sort & Set Index: Sort the data by date and set the 'Date' column as the index.

Fill Missing Data: Uses the 'pad' method to fill missing values with the last valid data.

Extract Day Names: Creates a 'Day' column that contains the name of the day for each date.

2. ARIMA Model for Stock Price Forecasting
Fit ARIMA Model: ARIMA is used with (5, 1, 0) parameters, which mean the model uses the past 5 values, a first-degree difference, and no error correction.

Forecast Future: The model forecasts the stock prices for the next 30 days.

Plot ARIMA Results: Historical stock prices and ARIMA forecasts are plotted.

3. LSTM Model for Stock Price Forecasting
Scale Data: The stock prices are scaled between 0 and 1 using MinMaxScaler.

Prepare Sequences: Creates input sequences of 60 previous days' prices to predict the next day’s price.

Build LSTM Model: An LSTM model is built with two LSTM layers (50 units each) and one Dense layer to output the predicted price.

Train LSTM Model: The model is trained on the prepared sequences for 10 epochs.

Predict Next 30 Days: Using the trained model, the next 30 days of stock prices are predicted by feeding the model the last 60 days of data and iterating the predictions.

Inverse Scaling: The predicted values are converted back to the original scale using the inverse of the MinMaxScaler.

Plot LSTM Results: The historical stock prices and LSTM predictions are plotted.

4. Final Outputs
ARIMA Forecast: Historical stock prices along with the ARIMA forecast for the next 30 days.

LSTM Forecast: Historical stock prices along with the LSTM forecast for the next 30 days.
