# Gold Price Forecasting: Technical Analysis Report

## 1. Introduction

Time series forecasting is a critical tool for predicting financial market trends based on historical data. In this project, the **ARMA (AutoRegressive Moving Average)** model is employed to analyze and forecast the price of gold. The primary objective is to identify the underlying patterns in gold valuation and estimate future prices for short-term decision-making.

The analysis uses historical gold price data (24K Rate per 1 Gram) and applies the **ARIMA(1,0,1)** model—which functions as an ARMA model—using Python libraries including **Pandas, NumPy, Statsmodels, and Matplotlib**.
<img width="889" height="656" alt="Screenshot 2026-03-05 213803" src="https://github.com/user-attachments/assets/7acfb768-e903-49c6-bdf9-487444d0a499" />

---

## 2. Data Description

The dataset utilized for this model consists of historical gold price records. Key characteristics include:

* **Source**: An Excel dataset titled `Gold Price.xlsx`.
* **Feature**: The "24K Rate (1 Gram)" column represents the daily market value of gold.
* **Index**: The data is indexed by a "Date" column, which was converted to a datetime format for time-series compatibility.
* **Trend**: The dataset reflects historical fluctuations leading up to a specific evaluation period.

---

## 3. Methodology

### The ARMA Model

The model implemented is an **ARIMA (1, 0, 1)**, which consists of the following components:

* **AR (AutoRegressive) = 1**: Utilizes the relationship between the current price and the price from the immediate previous period ($p=1$).
* **I (Integrated) = 0**: No differencing was applied, assuming the series is stationary ($d=0$).
* **MA (Moving Average) = 1**: Incorporates the dependency between an observation and a residual error from a moving average model ($q=1$).

**Implementation Steps:**

1. Data loading and date-time indexing.
2. Defining the "24K Rate" as the target variable.
3. Fitting the ARIMA(1,0,1) model to the historical data.
4. Generating a **5-step out-of-sample forecast**.
5. Visualizing the results using a line plot.

---

## 4. Model Summary

The model was successfully fitted using the `statsmodels` library. While the notebook execution provided a summary of forecasts, it also noted specific technical warnings:

* **Frequency Warning**: The dataset did not have an associated frequency (e.g., daily), so the model utilized an integer-based index for predictions.
* **Compatibility**: The code was executed using **NumPy version 2.1.3**.

---

## 5. Forecast Results

The model generated the following **5 future gold prices** based on the learned historical patterns:

| Step Index | Predicted Gold Price (per Gram) |
| --- | --- |
| **30** | 16,490.64 |
| **31** | 16,315.00 |
| **32** | 16,203.27 |
| **33** | 16,132.18 |
| **34** | 16,086.95 |

**Interpretation**: The forecast indicates a gradual downward trend or stabilization following the last observed price in the dataset.

---

## 6. Graphical Representation

The generated plot provides a visual comparison of the model's performance:

* **Blue Line (Original Price)**: Shows the historical trajectory of gold prices.
* **Orange Line (Forecast)**: Represents the projected 5-step future prices.

The visualization helps in identifying how closely the model aligns with recent historical movements before projecting the stabilization trend.

---

## 7. Conclusion

The **ARMA(1, 1)** model was successfully applied to forecast the 24K gold rate per gram. The model successfully captured recent price momentum to provide a 5-step outlook.

The results suggest that gold prices may experience a **slight stabilization** in the short term. This analysis serves as a baseline; future iterations could be improved by assigning an explicit date frequency and performing stationarity tests (like the ADF test) to further refine the $d$ and $p$ parameters.

---

