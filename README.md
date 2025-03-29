# EV Demand Forecasting in India 🚗⚡

![EV Demand Forecasting](https://img.shields.io/badge/Project-EV%20Demand%20Forecasting-blue) ![Python](https://img.shields.io/badge/Python-3.x-yellow) ![License](https://img.shields.io/badge/License-MIT-green)

This project forecasts the demand for Electric Vehicles (EVs) in India using time-series analysis techniques. By analyzing historical vehicle registration data across various fuel types—Electric Vehicles (EVs), Hybrid, CNG, Petrol, and Diesel—we aim to predict future trends to support policymakers, industry stakeholders, and market analysts in shaping the future of sustainable transportation.
---

## 🌟 Project Overview

The Indian automotive industry is witnessing a transformative shift toward sustainable fuel types, particularly EVs. This project leverages time-series methods to:
- Analyze trends in vehicle registrations from multiple fuel categories.
- Forecast future EV demand using advanced statistical models.
- Provide actionable insights into the adoption of alternative fuel vehicles.


## 📊 Dataset

The dataset, sourced from [Parivahan.gov.in](https://parivahan.gov.in/), contains monthly vehicle registration counts in India across various fuel types, including:
- `CNG ONLY`
- `DIESEL`
- `DIESEL/HYBRID`
- `ELECTRIC(BOV)`
- `PURE EV`
- `PETROL/HYBRID`
- And more (originally 24+ columns).

Key features:
- **Date**: Timestamp of observations.
- **Fuel Categories**: Registration counts for EVs, Hybrids, CNG, Petrol, Diesel, etc.

---

## 🛠️ Methodology

The forecasting pipeline involves the following steps:

1. **Data Cleaning**:
   - Handle missing values, outliers, and inconsistencies.
   - Prepare a clean dataset for analysis.

2. **Data Decomposition**:
   - Decompose the time series into **trend**, **seasonality**, and **residuals** using `seasonal_decompose` (period = 12 months).

3. **Stationarity Testing**:
   - Use the **Augmented Dickey-Fuller (ADF)** test to ensure stationarity.
   - Apply differencing where necessary (e.g., 1st differencing for Diesel, Petrol; 2nd differencing for EV, CNG).

4. **Smoothing Techniques**:
   - **Simple Exponential Smoothing (SES)**: For data without trends or seasonality.
   - **Double Exponential Smoothing (DES)**: Incorporates trends.
   - **Triple Exponential Smoothing (TES)**: Captures trends and seasonality.

5. **Granger Causality**:
   - Test relationships between fuel types (e.g., Petrol Granger-causes EV at lag 3; CNG strongly influences EV across all lags).

6. **Modeling**:
   - **Vector AutoRegression (VAR)**: Selected for its ability to model multivariate time series and interdependencies.
   - **PCA**: Applied to reduce dimensionality and mitigate multicollinearity before VAR fitting.

7. **Forecasting**:
   - Predict EV registrations for the next 12 months using the VAR model.

8. **Evaluation**:
   - Compare VAR with ARIMA and GARCH using error metrics (MAE, RMSE, MAPE).

---

## 🚀 Getting Started

### Prerequisites
- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `sklearn`

Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn
```

### Running the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/Say2hub/EV-Demand-Forecasting.git
   cd EV-Demand-Forecasting
   ```
2. Add the dataset (e.g., `vehicle_registrations.xlsx`) to the root directory.
3. Open the Google Colab notebook
4. Run all cells to preprocess data, fit models, and visualize forecasts.

---

## 📈 Key Results

- **Stationarity**: Most series (e.g., EV, CNG, Petrol) became stationary after differencing, confirmed by ADF tests (p < 0.05).
- **Granger Causality**:
  - **CNG → EV**: Strong causality across all lags (p ≈ 0.0000).
  - **Petrol → EV**: Causality at lag 3 (p = 0.0176).
  - **Hybrid → EV**: Strong causality at lags 3 and 4 (p = 0.0000).
  - **Diesel → EV**: No significant causality.
- **VAR Model Performance**:
  - MAE: 7192.98
  - RMSE: 19939.93
  - R²: 0.83
- **Forecast**: The 12-month EV sales forecast shows growth, influenced by CNG and Hybrid trends.

### Visualizations
- Historical vs. Forecasted EV Sales.
- Impulse Response Functions (IRFs) showing EV response to shocks in CNG (positive), Petrol (negative), and Hybrid (mixed).

---

## ⚠️ Challenges & Improvements

- **Challenges**:
  - Incomplete data sections (e.g., missing error metrics for ARIMA/ARCH).
  - Multicollinearity in the original dataset required PCA.
- **Future Improvements**:
  - Incorporate external factors (e.g., fuel prices, subsidies).
  - Explore deep learning models like LSTM for non-linear patterns.
  - Add regional granularity to the analysis.

---

## 📚 References

- Dataset: [Parivahan.gov.in](https://parivahan.gov.in/)
- Brownlee, J. "Regression Metrics for Machine Learning" - [Machine Learning Mastery](https://machinelearningmastery.com/)
- Burba, D. "An Overview of Time Series Forecasting Models" - [Towards Data Science](https://towardsdatascience.com/)
- [Statsmodels Documentation](https://www.statsmodels.org/)
- [Matplotlib](https://matplotlib.org/) & [Seaborn](https://seaborn.pydata.org/) Documentation

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⭐ **Star this repository if you find it useful!** Let’s accelerate the transition to sustainable mobility together! ⚡

---
