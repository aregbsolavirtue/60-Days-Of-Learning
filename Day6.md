# Day 006 – Introduction to Time Series Forecasting with Prophet

**Date:** July 20, 2026

## What I Learned

Today, I learned how to build a simple forecasting model using **Facebook Prophet**, a Python library used to predict future values based on historical data.

### Libraries Used

- **Pandas** – Used to create and organize data into a table called a DataFrame.
- **Prophet** – A machine learning library used for time series forecasting.

## Understanding the Code

### 1. Importing Libraries

First, I imported the required libraries.

```python
import pandas as pd
from prophet import Prophet
```

- `pandas` is used for handling and organizing data.
- `Prophet` is used to train a forecasting model.

### 2. Preparing the Data

I created a DataFrame containing two columns:

- **ds** – The dates.
- **y** – The values recorded on those dates (in this example, the number of cookies sold).

Prophet requires every dataset to use:

- `ds` for dates.
- `y` for the values to be predicted.

### 3. Training the Model

I created a Prophet model and trained it using the historical data.

```python
helper = Prophet()
helper.fit(cookie_data)
```

During training, the model learns the pattern in the data so it can make future predictions.

### 4. Creating Future Dates

Next, I asked Prophet to generate the next **3 days** after the existing data.

```python
future_days = helper.make_future_dataframe(periods=3)
```

This creates a calendar containing both the original dates and the additional future dates.

### 5. Making Predictions

I then used the trained model to predict the values for all dates, including the new future dates.

```python
forecast = helper.predict(future_days)
```

### 6. Displaying the Results

Finally, I displayed the last three predicted values.

```python
print(forecast[['ds','yhat']].tail(3))
```

- `ds` represents the future dates.
- `yhat` represents Prophet's predicted values.

## Key Takeaways

- Prophet is a machine learning library used for time series forecasting.
- Before training a Prophet model, the dataset must contain:
  - `ds` for dates.
  - `y` for the values.
- The model learns from historical data and predicts future values.
- `make_future_dataframe()` creates future dates.
- `predict()` generates the forecasts.

## Reflection

Today's lesson introduced me to time series forecasting using Prophet. I learned how to prepare data, train a forecasting model, generate future dates, and make predictions. This gave me a better understanding of how machine learning can be used to forecast future events based on past data.

---

**Day 6 Complete **
