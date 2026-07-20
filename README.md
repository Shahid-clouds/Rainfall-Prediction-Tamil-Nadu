# Tamil Nadu 3-Day Rainfall Forecast

A machine learning model that predicts rainfall for the next 3 days (+1, +2, +3) across 10 districts in Tamil Nadu, using live weather data from the free [Open-Meteo API](https://open-meteo.com/) (no API key required).

## What it does

- Pulls 120 days of historical weather data + current forecast for 10 TN districts (Cuddalore, Chennai, Vellore, Coimbatore, Salem, Thanjavur, Tiruchirappalli, Madurai, Tirunelveli, Kanyakumari)
- Engineers features from rainfall lags/rolling averages and temperature, humidity, and pressure forecasts
- Trains and compares two models — Linear Regression and Random Forest — for each forecast horizon (Day+1, Day+2, Day+3)
- Evaluates with MAE, RMSE, and R²
- Visualizes feature importance, rainfall patterns by district/month, and predicted vs. actual rainfall

## Tech stack

Python, pandas, NumPy, scikit-learn (Linear Regression, Random Forest), matplotlib, seaborn, Open-Meteo API

## How to run

1. Open the notebook in Google Colab or Jupyter
2. Run all cells top to bottom (an active internet connection is required — the notebook fetches live data)
3. No API key or setup needed

## Limitations

- 120 days of history per district is a small sample — this is a proof of concept, not a production forecaster
- Temperature/pressure/humidity inputs are themselves outputs of a physics-based weather model (that's how Open-Meteo provides them), so this is closer to statistical post-processing of an existing forecast than predicting rainfall from raw first principles
- Accuracy degrades from Day+1 to Day+3, as with any weather model
- Limited to 10 districts to keep the notebook fast and readable; the same code works for any set of coordinates
