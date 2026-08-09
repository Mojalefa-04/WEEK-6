# Week 6 – Advanced Python Analysis: AAPL Stock Market Analysis

## AnalystLab Africa Data Analytics Internship – Batch B

This project was completed as part of **Week 6: Advanced Python for Data Analysis**. The objective was to apply Python techniques for data transformation, time-series analysis, and feature engineering using historical stock-market data for **Apple Inc. (AAPL)**.

---

## 1. Project Overview

The analysis uses approximately five years of AAPL historical stock-market data downloaded using the `yfinance` Python library.

The project focuses on:

- Data cleaning and preprocessing
- Advanced Pandas data transformation
- Time-series analysis
- Daily and monthly performance analysis
- Rolling averages
- Percentage-change analysis
- Feature engineering
- Volatility analysis
- Data visualization

The analysis is **descriptive rather than predictive**. Historical trends and volatility patterns should not be interpreted as guarantees of future stock performance.

---

## 2. Dataset

**Dataset:** Apple Inc. (AAPL) Historical Stock Market Data  
**Source:** Yahoo Finance  
**Acquisition:** `yfinance` Python library  
**Period analysed:** 29 July 2021 – 28 July 2026  
**Observations:** 1,254 trading days  
**Original variables:** 7

### Original Variables

| Variable | Description |
|---|---|
| `Date` | Trading date |
| `Open` | Opening stock price |
| `High` | Highest price during the trading day |
| `Low` | Lowest price during the trading day |
| `Close` | Closing stock price |
| `Adj Close` | Adjusted closing price |
| `Volume` | Number of shares traded |

---

## 3. Tools and Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **yfinance**
- **Jupyter Notebook**

---

## 4. Data Cleaning and Transformation

The following preprocessing and transformation techniques were applied:

1. Converted `Date` to datetime format.
2. Sorted observations chronologically.
3. Checked for duplicate rows and duplicate dates.
4. Converted market variables to numeric data types.
5. Checked and handled missing values.
6. Set `Date` as the time-series index.
7. Filtered and sorted observations to investigate market activity.
8. Used Pandas `resample()` for monthly and yearly aggregation.
9. Created calculated columns for price movements and returns.
10. Exported the cleaned and feature-engineered dataset for reuse.

---

## 5. Feature Engineering

The following features were created:

| Feature | Purpose |
|---|---|
| `Daily_Price_Change` | Absolute change in closing price from the previous trading day |
| `Daily_Return` | Percentage change in closing price |
| `MA_7` | 7-trading-day moving average |
| `MA_30` | 30-trading-day moving average |
| `Daily_Range` | Difference between the daily high and low |
| `Range_Percent` | Daily range relative to opening price |
| `Volatility_30D` | 30-trading-day rolling standard deviation of daily returns |
| `Year` | Year extracted from the date |
| `Month` | Numerical month extracted from the date |
| `Month_Name` | Month name extracted from the date |

These features provide additional measures for understanding price movement, trend, trading activity, and short-term variability.

---

## 6. Time-Series Analysis

The project included:

- Daily price-change analysis
- Daily percentage returns
- 7-day rolling averages
- 30-day rolling averages
- Monthly returns
- Yearly returns
- Trading-volume analysis
- 30-day rolling volatility
- Identification of highest and lowest closing prices
- Identification of strongest and weakest return periods

---

# 7. Visualizations

The notebook contains six main analytical visualizations plus a feature correlation matrix.

## 7.1 AAPL Closing Price Trend

The closing-price trend shows the overall movement of AAPL over the analysis period.

![AAPL Closing Price Trend](visualizations/01_aapl_closing_price_trend.png)

---

## 7.2 Trading Volume Trend

Trading volume was analysed to identify periods of increased market activity.

![AAPL Trading Volume Trend](visualizations/02_aapl_trading_volume_trend.png)

---

## 7.3 Moving Average Analysis

The 7-day and 30-day moving averages were used to smooth short-term price fluctuations and make underlying trends easier to observe.

![AAPL Moving Average Analysis](visualizations/03_aapl_moving_average_analysis.png)

---

## 7.4 Daily Percentage Returns

Daily returns show the percentage movement in AAPL's closing price from one trading session to the next.

![AAPL Daily Returns](visualizations/04_aapl_daily_returns.png)

---

## 7.5 30-Day Rolling Volatility

Rolling volatility measures the variability of daily returns over a moving 30-trading-day window.

![AAPL 30-Day Rolling Volatility](visualizations/05_aapl_30_day_rolling_volatility.png)

---

## 7.6 Monthly Returns

Monthly returns provide a higher-level view of AAPL's performance and reduce some of the noise present in daily observations.

![AAPL Monthly Returns](visualizations/06_aapl_monthly_returns.png)

---

## 7.7 Feature Correlation Matrix

A correlation matrix was also used to examine linear relationships among selected numerical variables.

![AAPL Feature Correlation Matrix](visualizations/07_aapl_feature_correlation_matrix.png)

---

# 8. Key Findings

### Overall price performance

AAPL's closing price increased from **$145.64** at the beginning of the analysis period to **$336.91** at the end, representing an overall price increase of **131.33%**.

### Price range

The lowest closing price recorded was **$125.02 on 5 January 2023**, while the highest closing price was **$336.91 on 27 July 2026**.

### Annual performance

The yearly analysis showed substantial variation:

| Year | Annual Return |
|---|---:|
| 2022 | -26.83% |
| 2023 | +48.18% |
| 2024 | +30.07% |
| 2025 | +8.56% |
| 2026* | +23.93% |

`*` 2026 represents year-to-date performance based on the available data in the analysis.

### Daily return behaviour

The average daily return was **0.0822%**, with daily return volatility of **1.75%**. The strongest daily return was **+15.33%**, while the weakest was **-9.25%**.

### Trading activity

The highest recorded trading volume was **318,679,900 shares on 20 September 2024**, highlighting a period of unusually high market activity.

---

# 9. Recommendations

Based on the analysis:

1. **Combine moving averages with daily returns** when monitoring price trends. Moving averages help smooth short-term noise, while daily returns show individual-period movements.

2. **Monitor trading volume alongside price movements.** Unusually high volume can indicate periods of increased market activity and should be examined together with price behaviour.

3. **Track rolling volatility** when comparing different periods. Higher volatility indicates greater short-term variation in returns.

4. **Extend the analysis into predictive modelling** in future projects. Time-series forecasting, risk metrics, and event-based analysis could build on the features developed in this project.

5. **Reuse the engineered dataset** as a foundation for future Python, statistical, or machine-learning projects.

---

# 10. Project Structure

```text
Week-6-AAPL-Advanced-Python/
│
├── README.md
│
├── notebooks/
│   └── Week_6_AAPL_Advanced_Python_Analysis.ipynb
│
├── Data/
│   ├── AAPL_Week6_Feature_Engineered.csv
│   ├── AAPL_Monthly_Summary.csv
│   └── AAPL_Yearly_Summary.csv
│
└── visualizations/
    ├── 01_aapl_closing_price_trend.png
    ├── 02_aapl_trading_volume_trend.png
    ├── 03_aapl_moving_average_analysis.png
    ├── 04_aapl_daily_returns.png
    ├── 05_aapl_30_day_rolling_volatility.png
    ├── 06_aapl_monthly_returns.png
    └── 07_aapl_feature_correlation_matrix.png
```

---

# 11. Deliverables

- [x] Data loading
- [x] Data exploration
- [x] Data cleaning and preprocessing
- [x] Advanced Pandas transformations
- [x] Time-series analysis
- [x] Feature engineering
- [x] Six analytical visualizations
- [x] Feature correlation analysis
- [x] Key findings
- [x] Recommendations
- [x] Feature-engineered dataset export
- [x] Monthly summary export
- [x] Yearly summary export

---

## 12. Conclusion

This project demonstrates how Python and Pandas can be used to transform historical stock-market data into meaningful time-series insights. Data cleaning, aggregation, rolling calculations, feature engineering, and visualization were combined to examine AAPL's long-term price trend, daily performance, trading activity, and volatility.

The project also provides a foundation for progressing from descriptive analytics toward more advanced financial time-series and predictive analysis.
