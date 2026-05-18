# Energy Demand Forecasting — Netherlands

**MSc Data Science Thesis · University of Amsterdam**

> *Investigating Climate and Economic Predictors for Energy Demand Forecasting*

This repository contains the analysis pipeline for the thesis, which studies how multicollinearity mitigation strategies (correlation filtering, PCA, Ridge, ElasticNet) affect both the forecast accuracy and interpretability of SARIMAX models for Dutch electricity demand. A two-stage SARIMAX approach is used to isolate the contribution of climate and economic predictors from the underlying temporal dynamics, evaluated across six forecast horizons (H ∈ {1, 3, 7, 30, 90, 180} days). An LSTM is included as an accuracy reference benchmark.

---

## Repository Layout

```
.
├── EDA.ipynb                        # Exploratory data analysis
├── 01_feature_engineering.ipynb     # Build daily modelling dataset (2009–2025)
├── 02_predictor_strategies.ipynb    # Four multicollinearity mitigation strategies
├── 03_sarimax_models.ipynb          # Two-stage SARIMAX fitting & forecasting
├── 04_interpretability.ipynb        # H1 / H2 / H3 hypothesis tests
├── 05_lstm_benchmark.ipynb          # LSTM accuracy reference benchmark
│
├── data/                            # Intermediate pipeline artifacts
├── plots/                           # Generated figures
├── raw_data/                        # Raw climate and economic source files
└── loadConsumption/                 # Raw load data (TenneT/ENTSO-E) + preprocessing
```

Notebooks are designed to run sequentially — each saves outputs to `data/` consumed by the next. Any single notebook can be re-run in isolation as long as its upstream `data/` files are present.

---

## Setup

**Python 3.10+ recommended.**

```bash
pip install -r requirements.txt
pip install pandas numpy scikit-learn matplotlib seaborn shap torch
```

```bash
jupyter lab
```
