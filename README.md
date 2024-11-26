Project Overview

Unraveling negative electricity prices in Germany using machine learning models (XGBoost, Random Forest). The project focuses on understanding and predicting negative electricity price events driven by renewable energy oversupply and the inflexibility of non-renewable energy sources. It leverages time-series data from the ENTSO-E Transparency Platform, including electricity generation (renewable: solar, wind; non-renewable: coal, gas), consumption, and day-ahead market prices.

Objectives

Prediction of Negative Price Events
Develop machine learning models to forecast periods of negative electricity prices using historical data.

Quantify Energy Contributions
Analyze and compare the roles of renewable (solar, wind) and non-renewable (coal, gas) energy sources in driving negative price events.

Pattern Analysis
Identify seasonal, daily, and hourly trends associated with negative electricity prices to support better grid and market management.

Data Source

ENTSO-E Transparency Platform

Comprehensive time-series data spanning from January 2022 to August 2024.
Covers electricity generation by source, actual and forecasted consumption, and day-ahead market prices.
Data Preprocessing

Cleaning

Handled missing values in key columns using forward-filling techniques.
Detected and treated outliers in day-ahead prices using the IQR method.
Feature Engineering

Time-Based Features: Hour of the day, day of the week, and holiday indicators.
Lag Features: 24-hour and 48-hour lagged prices.
Rolling Averages: Smoothing solar and wind generation to capture long-term trends.
Combined Wind Energy: Onshore and offshore aggregated for simplicity.
Scaling
Applied StandardScaler for normalization of all numerical features.

Model Development

Algorithms Used

XGBoost: Effective for imbalanced datasets and structured data, with hyperparameter tuning for precision.
Random Forest: Robust to noise and provides feature importance for explainability.
Target Variable
Binary classification:

1 for negative prices (< 0 €/MWh).
0 for non-negative prices (≥ 0 €/MWh).
Imbalance Handling

Experimented with scale_pos_weight in XGBoost.
Applied SMOTE (Synthetic Minority Oversampling Technique) for Random Forest.
Evaluation Metrics

Precision: Focuses on minimizing false positives.
Recall: Ensures rare negative events are identified.
F1-Score: Balances precision and recall for imbalanced data.
Confusion Matrix: Provides detailed insight into true positives, false positives, and other predictions.
Key Insights

Negative prices are more frequent during high renewable production and low demand periods (e.g., nights, early mornings, weekends).
Gas and coal production significantly decrease during negative price events, but their inflexibility contributes to sustained oversupply.
Seasonal patterns highlight higher negative price occurrences in spring, linked to wind and solar peaks.
