# econ5200-lab05-risk-model

# Diagnosing a Flawed Risk Model: VaR, Expected Shortfall & Monte Carlo

## Objective
I tested a junior analyst's normal-distribution VaR model against historical data to find out how much risk it was missing, and I checked whether better methods and a variance-reduction technique would fix it.

## Methodology
- Diagnosed the analyst's normal-distribution VaR model by comparing its 99% VaR to historical VaR on the same portfolio.
- Computed VaR and Expected Shortfall (ES) with three methods: historical, normal, and Student-t (fitted df = [YOUR VALUE]).
- Used the `risk_metrics.py` module (`calculate_var`, `calculate_es`, `mc_var`) and ran its self-tests to confirm it behaved correctly.
- Applied antithetic variates to the Monte Carlo VaR simulation to reduce its standard error.
- Had an AI write a VaR backtest. I revised my prompt once, then checked the result against my own count of breaches.

## Key Findings
- At 99%, the normal-distribution model overstated historical VaR by 17.31%, which is $40806 on the portfolio.
- Antithetic variates cut the Monte Carlo standard error by 1.259x.
- In the backtest, the normal 99% VaR was breached on 1.7% of days. My own count agreed with the AI-written backtest.
