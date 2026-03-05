# Gold Price Forecasting Analysis

## 1. Introduction

Time series forecasting is a crucial method for predicting future market trends by analyzing historical patterns. In this study, the **AutoRegressive Integrated Moving Average (ARIMA)** model—specifically configured as an **ARMA(1,1)** or **ARIMA(1,1,1)**—is applied to historical gold price data. The objective is to evaluate price momentum and generate short-term projections for the 24K gold rate per gram.
<img width="801" height="671" alt="Screenshot 2026-03-05 220821" src="https://github.com/user-attachments/assets/a73ff267-be98-4020-b6ed-9b980b58665e" />

---

## 2. Data Description

The dataset comprises historical 24K gold prices (per 1 gram) with the following attributes:

* **Primary Variable**: 24K Rate (1 Gram).
* **Time Horizon**: The data spans early 2026, with observations showing significant volatility, reaching peaks above 18,000 before stabilizing.
* **Trend Analysis**: Initial analysis of the raw data indicated a strong upward trend followed by a recent corrective phase.

| Attribute | Details |
| --- | --- |
| **Data Source** | `Gold Price.xlsx` |
| **Observation Frequency** | Daily (Freq: D) |
| **Target Period** | January 2026 – March 2026 |

---

## 3. Methodology

The forecasting process utilized the **ARIMA(1,1,1)** model framework to account for both the auto-regressive nature of prices and the moving average of previous forecast errors.

### Model Components:

* **AR (1)**: Uses one previous value to capture momentum.
* **I (1)**: Applies first-order differencing to stabilize the mean and handle the dataset's trend.
* **MA (1)**: Incorporates the previous period's forecast error to refine the current prediction.

---

## 4. Technical Refinement

Initial model execution revealed a date-alignment issue where forecasts were incorrectly mapped to the year 1970 due to a lack of defined frequency. This was corrected by:

1. Converting the index to a proper datetime format.
2. Assigning a explicit **Daily ('D') frequency** to the index.
3. Synchronizing the forecast starting point with the end of the historical series (March 2026).

---

## 5. Forecast Results

The refined model generated a **5-day forecast** for gold prices following the last observation:

| Date | Forecast Value (per Gram) |
| --- | --- |
| **2026-03-06** | 16,321.48 |
| **2026-03-07** | 16,062.42 |
| **2026-03-08** | 15,904.93 |
| **2026-03-09** | 15,809.19 |
| **2026-03-10** | 15,750.98 |

**Interpretation**: After the recent peak and subsequent dip, the model predicts a continued, albeit gradual, stabilization trend toward the 15,750 level.

---

## 6. Graphical Representation

The updated visualization confirms that the forecast (orange line) now correctly appends to the original price data (blue line).

* **Historical Data**: Shows high volatility with a recent peak in February followed by a sharp decline.
* **Projected Trend**: The forecast smooths out the recent sharp drop, suggesting the price is approaching a short-term floor.

---

## 7. Conclusion

The application of the **ARIMA(1,1,1)** model successfully identified the corrective trend in gold prices. By resolving the indexing issues, the model now provides a chronologically accurate 5-day outlook. The results indicate that while the price has experienced a significant decline from its 18,000+ peak, the rate of decline is expected to slow down as it moves through mid-March 2026.
