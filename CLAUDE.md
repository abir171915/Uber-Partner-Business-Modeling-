# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Uber Partner Business Modeling** — two-scenario assignment:

- **Scenario 1:** Bonus payout analysis for drivers on a busy Saturday using `dataset_2.csv`. Evaluate two bonus structures (flat $50 vs $4/trip) and compute qualifying driver counts and percentages.
- **Scenario 2:** Pure arithmetic — model taxi driver annual profit with/without Uber partnership, then solve for the required fare increase to cover a $40,000 car purchase and maintain the same profit margin.

All work lives in `uber.ipynb`. No dataset for Scenario 2 — it is fully formula-driven.

## Environment Setup

```powershell
# Activate venv (PowerShell)
.\venv\Scripts\Activate.ps1

# Launch Jupyter
jupyter lab
```

## Data

- `dataset_2.csv` — driver-level aggregates for one Saturday: `trips_completed`, `acceptance_rate`, `hours_on_duty`, `avg_rating`
- Scenario 2 uses no data file — all inputs are hardcoded constants from the problem statement

## Notebook Structure

Sections in `uber.ipynb` follow this order:

1. Imports & data load
2. EDA (shape, dtypes, nulls, distributions)
3. Scenario 1 — Bonus analysis (Options 1 & 2, qualification filters, percentage breakdowns)
4. Scenario 2 — Expense projection & profit margin model

## Key Business Logic

**Option 1 qualifications:** hours_on_duty ≥ 8, acceptance_rate ≥ 0.90, trips_completed ≥ 10, avg_rating ≥ 4.7 → $50 flat  
**Option 2 qualifications:** trips_completed ≥ 12, avg_rating ≥ 4.7 → $4 × trips_completed  
**Scenario 2 baseline:** $200/day × 6 days × 49 weeks; expenses include gas ($200/week × 49), insurance ($400/month × 12), rent ($500/week × 49)  
**Scenario 2 Uber:** gas +5%, insurance −20%, no rent, car cost $40,000 amortized in year 1
