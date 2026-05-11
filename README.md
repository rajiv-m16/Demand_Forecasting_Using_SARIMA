# Furniture Sales Forecasting using SARIMA

This project provides a comprehensive time series analysis and forecasting model for furniture sales using historical data from a Superstore dataset. The primary goal is to identify sales patterns, check for stationarity, and build a Seasonal AutoRegressive Integrated Moving Average (SARIMA) model to predict future sales.

## 📌 Project Overview

Sales forecasting is a crucial component of business strategy, helping with inventory management and financial planning. This notebook walks through the data science workflow of transforming raw transactional data into a monthly time series forecast.

## 🛠️ Requirements

To run this notebook, you will need the following Python libraries:

* **Pandas**: Data manipulation and analysis.
* **NumPy**: Numerical computing.
* **Matplotlib**: Data visualization.
* **Statsmodels**: Statistical modeling, including Time Series analysis (ARIMA/SARIMA) and stationarity tests.

You can install the dependencies using:

```bash
pip install pandas numpy matplotlib statsmodels

```

## 📊 Dataset

The analysis uses a `Super Store.csv` file.

* **Scope**: Focused exclusively on the **Furniture** category.
* **Timeframe**: Data spans from 2014 to 2017.
* **Target Variable**: Daily sales aggregated and resampled to the start of each month (`MS`).

## 🚀 Workflow

### 1. Data Cleaning and Preparation

* Filtered the dataset for Furniture sales.
* Removed non-essential columns (Row ID, Order ID, etc.).
* Handled date-time formats and sorted data chronologically.
* Aggregated sales by date and resampled the data to monthly averages.

### 2. Exploratory Data Analysis (EDA)

* Visualized sales trends to identify seasonality.
* **Observation**: Sales typically drop at the beginning of the year and peak toward the end of the year (Q4 holiday season).

### 3. Stationarity Testing

* Applied the **Augmented Dickey-Fuller (ADF) Test**.
* Results showed the time series was stationary (p-value < 0.05), indicating it was suitable for ARIMA modeling.

### 4. Time Series Decomposition

* Decomposed the series into **Trend**, **Seasonality**, and **Residuals** using `seasonal_decompose`.

### 5. Model Selection & Fitting

* Performed a **Grid Search** to find the optimal parameters $(p, d, q) \times (P, D, Q, s)$ based on the lowest **AIC (Akaike Information Criterion)** score.
* Fitted a **SARIMAX** model.

### 6. Validation and Evaluation

* Validated the model using a rolling forecast (One-step ahead forecast) for the final year.
* **Metric**: Calculated **Root Mean Squared Error (RMSE)** to measure prediction accuracy.

## 📈 Results

* The model successfully captured the seasonal peaks and troughs of the furniture market.
* The forecast provides a 13-month outlook into the future with confidence intervals to account for uncertainty.

## 📂 Project Structure

* `Furniture_Sales_Forecasting.ipynb`
## 💡 Conclusion

The analysis confirms that furniture sales are highly seasonal. Businesses can use this model to anticipate high-demand periods in November and December and prepare for the "off-season" at the start of the year.