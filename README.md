# Forecasting Energy Consumption with Facebook Prophet

This project demonstrates time series forecasting of hourly energy consumption data using Facebook Prophet. The dataset used is `AEP_hourly.csv`, which contains hourly energy consumption measurements (in MW) for the American Electric Power (AEP) service area.

## Project Overview

Energy demand forecasting is essential for grid management and resource planning. In this project, the Prophet library is used to model and predict energy consumption based on historical data.

### Objectives:
- Clean and preprocess the dataset.
- Implement a forecasting model using Prophet.
- Visualize trends, seasonality, and forecast future energy consumption.

## Dataset

- **Source**: `AEP_hourly.csv`
- **Columns**:
  - `Datetime`: Timestamp of the observation (hourly frequency).
  - `AEP_MW`: Energy consumption in megawatts (MW).

## Methodology

1. **Data Preprocessing**:
   - Parsed `Datetime` into a datetime format.
   - Checked and handled missing values.
   - Resampled data if necessary to ensure consistent hourly observations.

2. **Modeling with Prophet**:
   - Renamed columns for compatibility with Prophet: `Datetime` → `ds`, `AEP_MW` → `y`.
   - Split the dataset into training and testing sets.
   - Trained the Prophet model on the training data.
   - Generated forecasts for future energy demand.

3. **Holidays Integration**:
   - Created two versions of the model:
     1. A **basic version** without considering holidays.
     2. An **enhanced version** that incorporates a custom list of holidays to analyze the impact of public holidays on energy consumption.
   - Holidays were added as an additional input to the Prophet model for better accuracy and insights.

## Results

- The model successfully captured long-term trends and seasonal patterns in the data.
- Forecasts provided reasonable estimates of future energy consumption for both short- and long-term horizons.
