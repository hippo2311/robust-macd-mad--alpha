# robust-macd-mad--alpha

Alpha name: robust-macd-mad--alpha

## Overview
This project implements a stateful, event-based trading strategy that combines
MACD Histogram, Bollinger Bands (in log-space), and ATR-based risk controls.
It evaluates four trading legs (Long Momentum, Short Momentum, Long Reversion,
Short Reversion) on MAANG stocks with daily data.

Goals:
- In-sample Sharpe >= 1.5
- Max drawdown < 20%
- Net returns outperform an equal-weighted MAANG portfolio

## Data
- Assets: MAANG stocks
- Frequency: Daily
- Window: 2010-01-01 to 2019-12-31
- Train: 2010-01-01 to 2017-12-31
- Test: 2018-01-01 to 2019-12-31
- Source: Yahoo Finance (via `yfinance`)

## Repository Contents
- `Group6_FinalTerm.ipynb` — main notebook with strategy design, optimizer, and backtest
- `Group6_FinalTerm.pdf` — exported report
- `result.png` — baseline results (pre-optimization)
- `result_using_portfolio.png` — results using optimized portfolio

## Requirements
Python 3.9+ recommended.

Key dependencies (from the notebook):
- numpy, pandas, scipy, matplotlib, plotly
- scikit-learn, ta, yfinance
- optuna
- gurobipy (optional, only if you run parts that require it)

Install example:
```bash
python -m venv .venv
source .venv/bin/activate
pip install numpy pandas scipy matplotlib plotly scikit-learn ta yfinance optuna
```

## Usage
Open the notebook and run the cells in order:
```bash
jupyter lab
```
Then open `Group6_FinalTerm.ipynb`.

## Results: Before vs After Optimization
Baseline (before optimization):
![Baseline results](result.png)

After portfolio optimization:
![Optimized portfolio results](result_using_portfolio.png)

## Notes
- Results depend on data availability from Yahoo Finance.
- If you do not have Gurobi installed, skip any optimizer sections that require it.

## Authors
Group 6:
- To Bao Chau (A0276224E)
- Bryan Ngu (A0276298J)
- Ho Xin Yi (A0281754X)
- Lauren Dana Ho Min (A0278037X)
- Phua Xing Xi Charlene (A0282609X)
- Bach Nguyen (A0258905U)
