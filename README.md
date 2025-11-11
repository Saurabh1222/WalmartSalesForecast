# Walmart Sales Forecast

Time-series forecasting of **weekly store sales** using a clean, leakage-free pipeline with **SARIMAX**, proper **weekly resampling**, and **rolling cross-validation**. The notebook runs end-to-end and produces forecasts and evaluation metrics.

> ✅ Main file: `WalmartSalesForecast.ipynb`  
> ✅ Works in Google Colab or local Jupyter

---

## What we build

- Parse and clean the dataset (dates, sorting, indexing).
- Aggregate to **weekly frequency** (e.g., `W-FRI`) and set explicit frequency.
- **Train/Test split by date** to avoid leakage.
- **SARIMAX** modeling with yearly seasonality on weekly data (`m = 52`).
- Optional **auto-ARIMA** hints (if `pmdarima` installed).
- **Diagnostics & Metrics**: residual diagnostics, MAE/RMSE.
- **Rolling Origin CV** (expand-window) for a quick robustness check.
- **Future Forecast** (e.g., next 12 weeks) with confidence intervals.

---

## Data

- Input CSV expected to include at least:
  - `Date` (parseable to datetime)
  - `Store` (store id)
  - `Weekly_Sales` (numeric)
- We can place the file anywhere; default path in the notebook is:
