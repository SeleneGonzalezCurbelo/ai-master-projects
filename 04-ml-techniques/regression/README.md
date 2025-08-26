# Regression: Linear Regression and Decision Trees

## Overview

This repository contains implementations and analyses of **regression tasks** using two popular machine learning models:

1. **Linear Regression** – A fundamental algorithm for predicting a continuous target variable.
2. **Decision Trees** – A flexible model capable of capturing nonlinear relationships between features and target variables.

The goal is to understand the differences between linear and nonlinear regression models, evaluate their performance, and apply best practices in data preprocessing and exploratory analysis.

---

## Datasets
The experiments are conducted on the **Air Quality Dataset** from the UCI Machine Learning Repository: [Air Quality Dataset](https://archive.ics.uci.edu/dataset/360/air+quality)

- 9,358 hourly-averaged responses from 5 metal-oxide chemical sensors.
- Data collected from March 2004 to February 2005.
- The task is to predict air quality for a given day.

---
## Key Features
- Handling of missing values using imputation techniques.
- Logarithmic transformations to normalize skewed distributions.
- Outlier detection and removal using the Interquartile Range (IQR) method.
- Analysis of correlations and feature engineering to optimize model performance.

## Implementation
- **Linear Regression**: Implementation includes preprocessing, fitting the model, and evaluating performance metrics such as MSE, RMSE, MAE, and R².
- **Decision Trees**: Includes model fitting, hyperparameter tuning, and evaluation using the same metrics for comparison.

## Results
- Decision Trees outperformed Linear Regression across most metrics:
  - Lower MSE and RMSE indicate more accurate predictions.
  - R² closer to 1 shows better explanation of variance.
  - More robust to nonlinear patterns in the data.
- Linear Regression performed well for general trends but failed to capture complex nonlinear relationships.

---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Machine Learning Techniques*  
Date: 2024
