# WTI Short-Term Forecasting Model

Short-term WTI forecasting model combining SARIMAX with inventory and term structure signals to capture market structure dynamics and generate forward price projections.

## Overview

This project builds a short-term WTI forecasting framework inspired by the U.S. Energy Information Administration (EIA) Short-Term Energy Outlook (STEO). The model uses a combination of statistical forecasting techniques and market structure analysis to model short-term changes in WTI crude oil prices.

The framework prioritizes interpretability and market relevance over unnecessary complexity, emphasizing observable supply, inventory, and futures curve dynamics commonly referenced in physical and financial oil markets.

---

## Methodology

The model uses a SARIMAX framework with exogenous variables selected through both statistical testing and economic intuition.

### Core Features

* Spot–CL1 spread (front-end structure / mean reversion signal)
* Brent–WTI spread changes
* Cushing crude inventory changes
* Rolling market structure indicators

### Statistical Validation

Feature selection and model construction included:

* Stationarity testing and transformations
* ACF/PACF analysis
* Granger causality testing
* SARIMAX specification analysis
* GARCH volatility modeling for conditional volatility estimation

### Scenario Framework

The model incorporates Monte Carlo simulation and conditional volatility estimates to generate forward price distributions and scenario-based projections under varying market regimes.

---

## Results

The final framework demonstrated:

* Improved RMSE relative to a naive benchmark
* Approximately 60% directional accuracy in out-of-sample testing
* Stable walk-forward performance across multiple forecast windows

Example forecast outputs and simulated paths are included in the `outputs/` directory.

![Forecast Projection](outputs/WTI%20Spot%20Projection%20w:%20MC%20Band.png)

---

## Repository Structure

```text
WTI-STEO-Model/
│
├── notebooks/
│   ├── STEO_PULL.ipynb
│   ├── STEO_Feature_Engineering.ipynb
│   ├── STEO_Target_Projection.ipynb
│   └── Assumption_Formulation.ipynb
│
├── outputs/
│   ├── WTI Spot Projection w: MC Band.png
│   ├── 25 Week Simulated Path.png
│   ├── Base, Bear, Bull Median Projections.png
│   └── Feature Projection Visualization.png
│
├── README.md
└── requirements.txt
```

---

## Design Philosophy

This framework was intentionally designed to balance:

* statistical rigor
* interpretability
* market intuition
* practical forecasting utility

Rather than maximizing feature count or model complexity, the project focuses on economically meaningful signals and transparent modeling assumptions.

---

## Future Improvements

Future iterations may incorporate:

* global supply-demand balances
* OPEC / non-OPEC production dynamics
* refined product consumption proxies
* expanded macroeconomic regime analysis

The current version prioritizes high-frequency market structure and inventory signals to preserve responsiveness in short-term forecasting applications.

---

## Disclaimer

This project is intended for educational and research purposes only and does not constitute investment advice or a trading recommendation.
