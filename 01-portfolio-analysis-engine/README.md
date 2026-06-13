# 01 - Portfolio Analysis Engine
 
## Objective
Build an end-to-end portfolio risk and optimisation toolkit covering volatility analysis, Sharpe-based allocation, ML price-direction prediction, VaR/CVaR risk measurement, stress testing, and Monte Carlo simulation.
 
## Data
- **Source:** yFinance API
- **Universe:** AAPL, MSFT, GOOGL, AMZN, TSLA, JPM, JNJ (7 stocks across tech, finance, healthcare)
- **Period:** 2022-2025 daily prices
## Methodology
1. **Data cleaning** - handled missing values, outliers, type inconsistencies
2. **Portfolio optimisation** - Sharpe-ratio weighted allocation, backtested across multiple years to avoid overfitting to a single period
3. **ML price prediction** - Random Forest classifier with 12 engineered features (momentum, RSI, volume ratio, S&P 500 relative strength); evaluated with `TimeSeriesSplit` cross-validation to prevent data leakage
4. **Risk measurement** - Historical VaR, Parametric VaR and CVaR (Expected Shortfall) at 95% and 99% confidence
5. **Stress testing** - portfolio performance simulated against 2008 Financial Crisis, COVID-19 Crash, and 2022 Tech Selloff
6. **Monte Carlo simulation** - 1,000 simulated 1-year forward paths
## Key Results
| Metric | Value |
|---|---|
| ML model accuracy (cross-validated) | 54.7% (vs 59% single-split - reported honestly) |
| 95% Historical VaR | -2.56% daily |
| Monte Carlo: probability of profit (1yr) | 72.0% |
| Monte Carlo: median 1-year outcome | $115,629 on $100,000 |
| Monte Carlo: worst 5% scenario | $76,515 |
 
## Key Learning
Single-split accuracy (59%) overstated model performance versus cross-validated accuracy (54.7%) - a reminder that one train/test split can produce misleadingly optimistic results, especially with financial time series.
 
## Deliverables
- Full Colab notebook (this folder)
- HTML executive dashboard
- Power BI interactive dashboard
## Tools
Python, Pandas, NumPy, Scikit-learn, Matplotlib, yFinance, SciPy
