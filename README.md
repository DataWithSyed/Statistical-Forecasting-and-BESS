# Statistical Forecasting and Battery Energy Storage System (BESS) Optimization

This repository presents a comprehensive project that integrates **statistical forecasting of energy prices** with an **optimization model for Battery Energy Storage Systems (BESS)**.
The aim is to demonstrate how data-driven forecasting techniques and decision algorithms can be combined to enhance energy market operations and maximize profitability from storage assets.

> **Note:**
> The dataset used in this analysis is confidential and **cannot be shared** publicly.
> Therefore, this repository contains only the **code** and **methodology**, not the original data files.

---

## Project Overview

Energy markets are increasingly influenced by the rise of renewables, storage, and dynamic pricing mechanisms.
This project demonstrates a simplified yet powerful workflow for:

1. **Forecasting short-term energy prices** using statistical learning.
2. **Optimizing BESS operation** based on predicted prices to maximize economic returns.

The workflow combines **machine learning, time-series analysis**, and **operational strategy modeling**, making it an excellent example for analysts and researchers working in the energy domain.

---

## Part 1: Energy Price Forecasting

The first module focuses on building a **predictive model** for energy prices using historical market data.

### Methodology

* **Data Processing:** Cleans and prepares historical price and demand data.
* **Feature Engineering:** Creates lagged price features and integrates renewable generation data.
* **Modeling Technique:** Uses a **Random Forest Regressor** to predict next-period prices.
* **Performance Visualization:** Compares predicted and actual prices over time.

### Example Workflow

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split
import pandas as pd
import matplotlib.pyplot as plt
```

1. Load and preprocess historical market data.
2. Create lagged and derived features.
3. Train and test a forecasting model.
4. Visualize predicted vs. actual price trends.

The results help determine when market prices are expected to rise or fall — a crucial input for storage operation strategies.

---

## Part 2: Battery Energy Storage System (BESS) Optimization

The second module develops a simplified **optimization strategy for BESS operation** based on the forecasted prices.

### Objective

To maximize profit by charging the battery when prices are low and discharging when prices are high.

### Decision Logic

* Charge when price < 90% of average price.
* Discharge when price > 110% of average price.
* Hold otherwise.

### Implementation

```python
profit, decisions = optimize_bess(hourly_prices, capacity, initial_charge_level, charge_eff, discharge_eff)
```

### Parameters

| Parameter              | Description                        | Example              |
| ---------------------- | ---------------------------------- | -------------------- |
| `hourly_prices`        | List of 24-hour price data         | `[100, 95, 90, ...]` |
| `capacity`             | Battery capacity (kWh)             | `100`                |
| `charge_efficiency`    | Energy retained during charging    | `0.95`               |
| `discharge_efficiency` | Energy retained during discharging | `0.95`               |

### Output

* **Total Profit:** Numerical value representing cumulative gains.
* **Hourly Decisions:** “Charge”, “Discharge”, or “Hold” for each hour.

---

## Combined Use Case

The **forecasted prices** from the statistical model can be **fed into the BESS optimization function** to evaluate profit potential based on predicted market trends — demonstrating the synergy between **predictive analytics** and **operational decision-making**.

---

## Technologies Used

* **Python 3.10+**
* **Pandas** – Data manipulation
* **Scikit-learn** – Forecasting model (Random Forest)
* **Matplotlib** – Visualization
* **Statistics** – Mean-based decision rules

---

## How to Run

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/Statistical-Forecasting-and-BESS.git
   cd Statistical-Forecasting-and-BESS
   ```

2. **Install Required Packages**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Notebook**

   ```bash
   jupyter notebook "Statistical Forecasting and BESS.ipynb"
   ```

---

## Example Visualization

The notebook produces time-series plots comparing:

* Actual vs. Predicted Energy Prices
* Optimal Charge/Discharge Schedule for BESS

---
  
## Future Enhancements

* Integrate **LSTM or ARIMA** models for more accurate forecasting.
* Introduce **market constraints and degradation costs** in BESS optimization.
* Expand to **multi-day and multi-market** operations.
* Deploy a **dashboard interface** for interactive forecasting and simulation.

---
