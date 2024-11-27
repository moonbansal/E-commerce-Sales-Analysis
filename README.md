# E-commerce-Sales-Analysis
Predicting festival impact on sales for top 5 sub-categories 

# Sales Forecasting for Chairs and Phones Sub-Categories

This repository contains a project that applies time series forecasting to the sales data of two specific sub-categories: *Chairs* and *Phones* from a dataset named **Superstore Combined.csv**. The project aims to utilize two different forecasting techniques — SARIMA and Facebook Prophet models — to predict future sales and compare the accuracy of these models.

## Project Overview

The main objective of this project is to model and forecast the monthly sales of the **Chairs** and **Phones** sub-categories using two advanced time series forecasting approaches:

1. **SARIMA Model**: Seasonal Auto-Regressive Integrated Moving Average.
2. **Facebook Prophet Model**: A powerful open-source forecasting tool provided by Meta for time series analysis.

The project workflow consists of the following main steps:

1. **Data Loading and Preparation**
2. **Log and Box-Cox Transformations for Variance Stabilization**
3. **SARIMA Modeling**
4. **Residual Analysis and Model Diagnostics**
5. **Forecasting with SARIMA and Facebook Prophet**
6. **Comparison of Forecasts**
7. **Model Evaluation Metrics**

## Project Steps and Methods

### 1. Data Loading and Preparation

- The dataset, **Superstore Combined.csv**, is loaded and filtered to work with the `Chairs` and `Phones` sub-categories.
- Monthly aggregation is performed for each sub-category.
- The data is split into training and test sets (80% training, 20% testing).

### 2. Data Transformation

- **Log Transformation**: Applied to stabilize variance.
- **Box-Cox Transformation**: Optionally used when the data contains zero or negative values.

### 3. SARIMA Modeling

- A **SARIMA model** is manually applied using predefined orders for the model parameters (`p`, `d`, `q`, `P`, `D`, `Q`, `m`), and automatic model selection is also conducted using **auto_arima**.
- The model is fitted on training data, and its summary statistics such as **AIC** and **BIC** are computed to assess goodness of fit.

### 4. Residual Diagnostics

- To ensure the adequacy of the SARIMA model, **residual analysis** is conducted, including:
  - **Q-Q Plot** to check for normality.
  - **Ljung-Box Test** to check for white noise.
  - **ACF and PACF** of residuals to check for remaining autocorrelation.

### 5. Forecasting

- The **SARIMA model** is used to forecast future sales, and its forecast confidence intervals are calculated.
- **Facebook Prophet Model** is implemented on the same data to compare its predictions against the SARIMA model.

### 6. Model Comparison

- A combined plot shows the **actual sales**, **SARIMA forecast**, and **Facebook Prophet forecast**.
- Forecasting accuracy is measured using metrics such as:
  - **Mean Absolute Error (MAE)**
  - **Root Mean Squared Error (RMSE)**
  - **Mean Absolute Percentage Error (MAPE)**

### 7. Evaluation Metrics

- Both SARIMA and Prophet models are evaluated based on the **test set**, with **MAE**, **RMSE**, and **MAPE** calculated to understand the accuracy and reliability of each model's forecast.

## Results and Insights

- The residual diagnostics help assess model adequacy, ensuring that the residuals are normally distributed with no significant autocorrelation.
- Forecast plots compare SARIMA vs Prophet forecasts against actual sales data for both sub-categories, highlighting differences in accuracy.
- Performance metrics indicate which model performs better for the given data.

## Requirements

- **Python 3.x**
- **Libraries**:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `statsmodels`
  - `pmdarima`
  - `scipy`
  - `prophet` (Facebook Prophet)
  - `sklearn`

To install the required libraries, you can use the following command:

```sh
pip install pandas numpy matplotlib statsmodels pmdarima scipy prophet scikit-learn
```

## File Structure

- **forecasting_project.py**: Contains the entire script for data transformation, model training, diagnostics, and forecasting.
- **requirements.txt**: Lists the required Python packages.
- **README.md**: This documentation file.

## Key Learnings

- **SARIMA** is particularly useful when dealing with seasonality and ensuring model diagnostics are checked.
- **Facebook Prophet** is simple to implement and can be used for automated future trend predictions with minimal parameter tuning.

## Future Improvements

- **Hyperparameter Tuning**: Enhance model performance by tuning hyperparameters for both SARIMA and Prophet.
- **Additional Features**: Consider incorporating external regressors such as holiday data or marketing campaigns.
- **More Product Sub-Categories**: Expand the analysis to other product sub-categories for a broader business perspective.

