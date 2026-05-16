# Energy Consumption Forecasting and Analysis

## Overview

This project focuses on forecasting and analyzing energy consumption and power generation trends using time series forecasting models and data visualization techniques. The project includes statistical forecasting methods, comparative model evaluation, and interactive dashboards for energy generation analysis.

The repository contains:

* Jupyter Notebook (`.ipynb`) for forecasting and analysis
* Two energy-related datasets
* Power BI report for generation data visualization

---

# Objectives

* Analyze historical energy consumption and generation data
* Forecast future electricity consumption trends
* Compare multiple time series forecasting models
* Evaluate forecasting accuracy using standard metrics

---

# Technologies Used

## Programming & Analysis

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Statsmodels
* Prophet

## Visualization

* Power BI

---

# Forecasting Models Implemented

## ARIMA

Autoregressive Integrated Moving Average model used for capturing temporal dependencies in the consumption series.

## SARIMA

Seasonal ARIMA model used for handling seasonality in energy consumption data.

## Prophet

Facebook Prophet model used for trend and seasonality based forecasting.

---

# Evaluation Metrics

The models were evaluated using:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
  
---

# Key Findings

* Western region dominates thermal energy production nationally
* Northern region leads hydro generation, driven by Himalayan river systems
* Eastern and NorthEastern regions have zero nuclear generation
* Telangana consumption peaks in summer months (May-June) due to cooling demand
* SARIMA outperforms ARIMA and Prophet on this dataset due to weekly seasonality in consumption patterns
* Actual vs Estimated generation gap is most pronounced in the Western region for thermal power
  
---
# Steps Performed
1. Data Loading and Exploration

* Loaded both datasets using pandas
* Checked shapes, data types, date ranges, and null values
* Found 1,978 null values in Nuclear Generation columns for Eastern and NorthEastern regions (these regions have no nuclear plants — filled with 0)

2. Data Cleaning

* Dropped redundant index column
* Converted Date columns to datetime format
* Extracted Month, Day, Year, and Day-of-week features
* Handled duplicate dates using groupby mean aggregation
* Resampled daily frequency using resample('D')

3. Exploratory Data Analysis

* Region-wise total energy breakdown (Thermal, Nuclear, Hydro)
* Actual vs Estimated generation comparison by region
* Telangana power consumption trend over time
* Monthly and daily seasonal patterns

4. Time Series Modeling
Three models were built and compared on Telangana consumption data:

ARIMA (1,0,1) — Baseline autoregressive model
SARIMA (1,0,1)(1,1,1,7) — Captures weekly seasonality
Prophet — Facebook's forecasting model with additive seasonality, yearly and weekly components, and custom monthly seasonality

5. Model Evaluation
All three models evaluated on the same test set using:

* MSE (Mean Squared Error)
* RMSE (Root Mean Squared Error)
* MAE (Mean Absolute Error)

7. Interactive Forecasting Widget
Built an ipywidgets dropdown that lets users select any Indian state and view the best model's 30-day forecast dynamically.

---

# Power BI Dashboard

The repository also includes a Power BI report for analyzing:

* Thermal generation
* Hydro generation
* Nuclear generation
* Regional generation trends
* Generation distribution patterns

---

# How to Run

1. Clone or download this repository
2. Upload both CSV files to your Google Colab environment
3. Open Sampujya_project.ipynb in Google Colab
4. Run all cells sequentially
5. The interactive widget at the end lets you select any state for forecasting
6. Open PowerBI_Report.pbix in Power BI Desktop to explore the dashboard

---

# Future Improvements

* Implement LSTM/GRU models
* Add weather and temperature regressors
* Deploy forecasting dashboard using Streamlit
* Real-time energy forecasting
* Advanced hyperparameter optimization

---

# Author

Developed by M. Sampujya as part of Internship-4.0 with Infosys SpringBoard
