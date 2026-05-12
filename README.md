# Uber Partner Business Modeling

A data analysis project modeling Uber driver economics — evaluating bonus payout structures and taxi driver profit margins under Uber partnership.

## Overview

This project covers two scenarios:

- **Scenario 1:** Analyse two driver bonus options for a high-demand Saturday using real driver data
- **Scenario 2:** Model a taxi driver's annual profit with and without Uber partnership, and calculate the required fare increase to cover a car purchase in year 1

## Dataset

`dataset_2.csv` — driver-level aggregates for one Saturday (119 drivers):

| Column | Description |
|---|---|
| `Name` | Driver name |
| `Trips Completed` | Total trips on the day |
| `Accept Rate` | % of ride requests accepted |
| `Supply Hours` | Hours online |
| `Rating` | Average driver rating |

> No dataset is used for Scenario 2 — all inputs are hardcoded constants.

## Key Results

**Scenario 1 — Bonus Analysis**

| Metric | Value |
|---|---|
| Option 1 total payout ($50 flat) | $1,050 |
| Option 2 total payout ($4/trip) | $2,976 |
| Drivers in Option 1 but not Option 2 | 2 |
| Drivers with < 10 trips | 33.61% |
| Drivers with acceptance rate < 90% | 46.22% |
| Drivers with rating ≥ 4.7 | 68.91% |

**Scenario 2 — Profit Modeling**

| Metric | Value |
|---|---|
| Annual profit without Uber | $19,700 |
| Extra weekly fares needed (with Uber + $40k car) | $306.73 |

## Setup

```powershell
# Clone the repo and activate the virtual environment
.\venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter lab
```

## Tech Stack

- Python 3
- pandas, numpy
- matplotlib, seaborn
- Jupyter Lab
