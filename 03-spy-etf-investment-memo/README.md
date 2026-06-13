# 03 - SPY ETF Investment Memo
 
## Objective
Conduct an independent quantitative and fundamental analysis of the SPDR S&P 500 ETF (SPY) and produce a formal investment recommendation for a conservative client profile.
 
## Data
- **Source:** yFinance API
- **Period:** 2020–2025
## Methodology
1. **Performance analysis** - annualised return, volatility, Sharpe ratio
2. **Risk analysis** - Historical/Parametric VaR, CVaR at 95%/99% confidence, maximum drawdown
3. **Crisis behaviour** - COVID-19 drawdown and recovery analysis
4. **Forward-looking** - 1,000-path Monte Carlo simulation
5. **Valuation context** - EV/EBITDA and DCF framing applied to index-level analysis
## Key Results
| Metric | Value |
|---|---|
| Annualised return (2020-2025) | 16.16% |
| Annualised volatility | 20.75% |
| Sharpe ratio | 0.68 |
| Maximum drawdown (COVID) | -33.72% |
| Monte Carlo: 1-year profit probability | 74.5% |
 
## Verdict
**Not recommended as a sole holding for a strictly conservative client.** A 33.72% maximum drawdown and 20.75% volatility exceed typical capital-preservation mandates. Recommended alternative: a 60/40 bond-equity blend incorporating SPY as the equity sleeve, reducing portfolio volatility to an estimated ~12% while retaining meaningful upside participation.
 
## Key Learning
Quantitative metrics alone (positive long-run returns, 74.5% profit probability) do not automatically translate into a suitable recommendation - client risk tolerance and capital preservation objectives must frame the final verdict, even when the underlying asset has strong historical performance.
 
## Tools
Python, yFinance, Pandas, Matplotlib, SciPy
