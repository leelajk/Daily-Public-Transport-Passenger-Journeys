# Daily Public Transport Passenger Journeys
Public Transport Ridership Forecasting using SARIMA

Public Transport Ridership Forecasting using SARIMA

This project performs exploratory time-series analysis and 7-day route-level ridership forecasting for public transport services. It leverages SARIMA (Seasonal ARIMA) models to capture trend and weekly seasonality, helping transport agencies plan schedules, allocate buses, and reduce operational costs.

# Dataset Description
- Column	Description
- Date	Calendar date (daily records)
- Local Route	Daily ridership count
- Light Rail	Daily ridership count
- Peak Service	Ridership during office peak service
- Rapid Route	Fast-route bus services
- School	Ridership from school-focused services
- Other	All remaining classified passenger journeys

The dataset spans multiple years, enabling both long-term trend study and short-term demand prediction.
# Project Overview

Public transport demand fluctuates across weekdays, weekends, and school periods. Without forecasting, some routes may run under-utilized while others suffer overcrowding, leading to excessive costs and poor service experience.

This project analyzes multi-year daily ridership data across multiple routes:

- Local Route
- Light Rail
- Peak Service
- Rapid Route
- School
- Other

and generates short-term actionable demand forecasts with operational insights.

# Objectives

Clean and preprocess multi-route ridership data

Explore trends, weekday/weekend patterns & seasonal behavior

Build SARIMA models for each route to forecast demand for the next 7 days

Evaluate models using a hold-out test window

Provide planning insights for fleet scheduling and resource optimization


# Tech Stack
Category	Tools
Programming	Python
Forecasting	SARIMA (via statsmodels)
Data Handling	Pandas, NumPy
Visualization	Matplotlib, Seaborn
Evaluation	RMSE, MAPE


# Exploratory Analysis Highlights
The notebook performs several visual analyses to understand ridership behavior:
Analysis	Purpose
Daily total ridership trend	Long-term demand evolution
Weekly aggregation	System-wide seasonality
Day-of-week averages	Weekday–weekend behavior
School vs non-school days	Effect of school periods on other services
Weekday vs weekend demand	Operational load variation
Year-wise behavior of “Other” category	Long-term classification patterns or anomalies

# Forecasting Approach
Chosen Model — SARIMA

SARIMA is used because it:
- Captures weekly seasonality
- Models long-term trends and autocorrelation
- Handles non-stationary behavior through differencing
- The model is run separately for each route to generate route-specific predictions.

# Model Configuration
order = (1, 1, 1)
seasonal_order = (0, 1, 1, 7)   
forecast_days = 7
test_window = 60                


# Output
- Forecast table — predicted ridership for all routes for the next 7 days
- Forecast plot — trend lines per route
- Evaluation metrics — RMSE and MAPE for test window
- Insights for scheduling and resource optimization

# Business Insights Generated
The forecast and EDA provide data-driven decision support, such as:
- Add more buses during school periods and weekday peaks
- Reduce fleet deployment on weekends and school holidays
- Reassign idle buses to high-demand routes
- Identify potential data quality gaps from the rising “Other” category


# Future Improvements

Some meaningful extensions that can be added:
- Hyperparameter tuning and model comparison (SARIMA vs Prophet vs LSTM)
- Holiday/event tagging to improve forecast accuracy
- Real-time scheduling dashboard using Flask/Streamlit
- Clustering of routes based on demand similarity
