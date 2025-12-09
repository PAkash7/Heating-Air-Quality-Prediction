# Heat Measuring and Prediction Demo By Akash Pandey

This notebook provides a comprehensive demonstration of generating synthetic time-series data related to environmental factors and building energy, followed by various data analysis, visualization, and machine learning modeling techniques.

## Table of Contents

1.  [Overview](#overview)
2.  [Features](#features)
3.  [Synthetic Data Generation](#synthetic-data-generation)
4.  [Plotting Utilities](#plotting-utilities)
5.  [Modeling - Heating Prediction](#modeling---heating-prediction)
6.  [Modeling - Air Quality Prediction (PM2.5)](#modeling---air-quality-prediction-pm2-5)
7.  [How to Run the Demo](#how-to-run-the-demo)
8.  [Number System Converter](#number-system-converter)

## Overview

This project simulates environmental and building data (outside temperature, humidity, heating load, and PM2.5 air quality) and demonstrates a workflow for:

*   Generating realistic synthetic time-series data.
*   Visualizing time-series, correlations, and model predictions.
*   Building simple machine learning models (RandomForestRegressor) to predict heating load and PM2.5 levels.
*   Analyzing data under different scenarios (default, cold wave, pollution spike).

## Features

*   **Synthetic Data Generator**: Creates hourly data for outside temperature, humidity, heating demand, and PM2.5 air quality with seasonal cycles, trends, and random noise/spikes.
*   **Plotting Utilities**: Functions to visualize time series, scatter plots with linear fits, correlation heatmaps, and forecast vs. actual comparisons.
*   **Machine Learning Models**: Includes functions to prepare features, train, and evaluate Random Forest Regressor models for predicting heating demand and PM2.5 levels.
*   **Scenario-based Demos**: Demonstrates data generation and analysis under 'default', 'cold_wave', and 'pollution_spike' scenarios.

## Synthetic Data Generation

The `generate_synthetic_dataset` function is the core of the data simulation. It allows you to create data for a specified period and frequency, with options to introduce different scenarios affecting temperature or air quality.

**Key Functions:**

*   `generate_time_index(start_date, periods, freq)`: Creates a pandas DatetimeIndex.
*   `seasonal_signal(...)`: Generates a signal with daily and yearly seasonality, trend, and optional spikes.
*   `generate_synthetic_dataset(...)`: Orchestrates the generation of all features based on specified parameters and scenarios.

## Plotting Utilities

Several functions are provided for quick visualization of the generated data and model results.

**Key Functions:**

*   `plot_time_series(df, cols, title, figsize, savepath)`: Plots selected columns of a DataFrame over time.
*   `plot_scatter_with_fit(x, y, xlabel, ylabel, title, savepath)`: Creates a scatter plot with a linear regression fit.
*   `plot_correlation_heatmap(df, cols, title, savepath)`: Displays a correlation matrix heatmap for specified columns.
*   `plot_forecast_vs_actual(dates, actual, predicted, title, savepath)`: Compares actual values against predicted values over time.

## Modeling - Heating Prediction

This section focuses on predicting the building's heating load (`heating_kW`) based on environmental factors and lagged features.

**Key Functions:**

*   `prepare_features(df, target_col)`: Selects features and target, handling NaNs.
*   `train_evaluate_regressor(X_train, y_train, X_test, y_test, model)`: Trains a regression model (defaulting to RandomForestRegressor) and evaluates its performance (MSE, R2).

## Modeling - Air Quality Prediction (PM2.5)

This section demonstrates predicting PM2.5 air quality using a similar machine learning approach, incorporating feature scaling.

**Key Functions:**

*   `train_simple_pm25_model(df)`: Prepares features, scales them, trains a RandomForestRegressor for PM2.5, and returns performance metrics.

## How to Run the Demo

The `demo_all()` function encapsulates the entire workflow for a given scenario.

1.  **Execute the first code cell (0FTiMlKYEX-_)** to define all functions and classes.
2.  **The `if __name__ == '__main__':` block at the end of the first code cell will automatically run the `demo_all()` function for three different scenarios**: 'default', 'cold_wave', and 'pollution_spike'.
3.  Observe the printed output and generated plots for each scenario.
4.  You can modify the `demo_all()` function or the `if __name__ == '__main__':` block to experiment with different parameters or scenarios.

## Number System Converter

Separately, the notebook includes a simple command-line interface (CLI) for converting numbers between different bases (decimal, binary, octal, hexadecimal).

**Key Functions (in cell qk34UxAnJ0zX):**

*   `decimal_to_binary`, `decimal_to_octal`, `decimal_to_hexadecimal`
*   `binary_to_decimal`, `binary_to_octal`, `binary_to_hexadecimal`
*   `octal_to_decimal`, `octal_to_binary`, `octal_to_hexadecimal`
*   `hexadecimal_to_decimal`, `hexadecimal_to_binary`, `hexadecimal_to_octal`

**To use the converter:**

1.  **Execute the code cell (qk34UxAnJ0zX)** containing the converter functions and the main loop.
2.  Follow the prompts in the output to select a conversion type and enter a number.
3.  Choose option `13` to exit the converter.

## Working by Akash Pandey for Learning Purpose only 
give realtime data in csv for more accurate output 
