# ARIMA Time Series Forecasting Report

## 1. Introduction

Time series forecasting is used to predict future values based on previously observed data. In this study, the **AutoRegressive Integrated Moving Average (ARIMA)** model is used to analyze and forecast a dataset. The model helps identify patterns in time series data and estimate future values.

The dataset used contains **10 observations**, representing values that increase over time. The **ARIMA (1,0,1)** model was applied using Python libraries such as **NumPy, Statsmodels, and Matplotlib**.

---

## 2. Data Description

The dataset used in the model is:

| Time | Value |
| ---- | ----- |
| 0    | 10    |
| 1    | 12    |
| 2    | 13    |
| 3    | 15    |
| 4    | 18    |
| 5    | 20    |
| 6    | 22    |
| 7    | 25    |
| 8    | 27    |
| 9    | 30    |

The values show a **clear increasing trend over time**, which makes the data suitable for time series forecasting.

---

## 3. Methodology

### ARIMA Model

The **ARIMA (1,0,1)** model consists of:

* **AR (AutoRegressive) = 1** → Uses one previous value to predict the next value
* **I (Integrated) = 0** → No differencing applied
* **MA (Moving Average) = 1** → Uses one previous error term

The model was implemented using the following steps:

1. Import required Python libraries.
2. Create the time series dataset.
3. Fit the ARIMA(1,0,1) model.
4. Generate a **5-step forecast**.
5. Plot the actual and forecasted values.

---

## 4. Model Summary

Key statistical results from the ARIMA model:

| Parameter      | Value   |
| -------------- | ------- |
| Observations   | 10      |
| Log Likelihood | -20.911 |
| AIC            | 49.821  |
| BIC            | 51.031  |
| HQIC           | 48.493  |

### Coefficients

| Parameter | Coefficient |
| --------- | ----------- |
| Constant  | 20.2123     |
| AR(1)     | 0.9649      |
| MA(1)     | 0.9130      |
| Sigma²    | 2.2005      |

**Interpretation**

* The **AR(1) value (0.9649)** shows a strong relationship between the current value and the previous value.
* The **MA(1) parameter (0.9130)** indicates that past error terms also influence the prediction.
* The model captures the trend in the dataset effectively.

---

## 5. Forecast Results

The ARIMA model predicted **5 future values**:

| Time | Forecast Value |
| ---- | -------------- |
| 10   | 32.11          |
| 11   | 31.70          |
| 12   | 31.29          |
| 13   | 30.91          |
| 14   | 30.53          |

The forecast shows a **slight stabilization after the increasing trend**, indicating the values may level off in the future.

---

## 6. Graphical Representation

The generated graph contains:

* **Blue line** → Actual observed data
* **Orange line** → Forecasted future values

The graph shows that the forecast begins after the 10th observation and follows the pattern learned from historical data.

---

## 7. Conclusion

The **ARIMA (1,0,1)** model was successfully applied to forecast future values of the time series dataset. The model identified the upward trend in the data and produced reasonable forecasts for the next five periods.

The results indicate that although the data previously increased steadily, the predicted values show a **gradual stabilization trend**. This demonstrates the usefulness of ARIMA models in analyzing and forecasting time series data.

---


* **A longer 3–4 page report for assignment/project submission**, or
* **Explanation of each line of your Python code** for viva or presentation.
# ARIMA-MODEL
