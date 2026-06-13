# 06 - Consumer Brand Health Index (Alternative Data Pilot)
 
## Objective
Construct a composite "Brand Health Index" combining product review sentiment and search-trend momentum, and test whether it leads, lags, or coincides with stock price movement - a pilot for alternative-data-driven equity signals.
 
## Data
- **Google Trends (pytrends)** - 4 Apple-related search signals (iPhone, Apple Intelligence, problem searches, purchase intent), 2025-2026
- **FinBERT sentiment** - 15 representative Apple product/news headlines (2025-2026 cycle)
- **yFinance** - AAPL weekly price data, 2025-2026
## Methodology
1. Composite trend score (70% weight): weighted combination of positive search signals minus "problem" search volume, normalised 0-100
2. Review sentiment score (30% weight): FinBERT-scored headlines, normalised 0-100
3. Brand Health Index = 0.70 × trend score + 0.30 × sentiment score
4. Lead/lag correlation testing against AAPL weekly returns across -2 to +2 week offsets
## Key Results
| Lag | Correlation | Interpretation |
|---|---|---|
| -2 weeks | +0.101 | BHI lags price |
| -1 week | +0.211 | BHI lags price (strongest) |
| 0 (coincident) | +0.168 | — |
| +1 week | +0.073 | BHI leads price |
| +2 weeks | +0.150 | BHI leads price |
 
## Finding
**No statistically reliable lead/lag relationship detected.** All correlations are weak (0.07–0.21) and, given the small sample (15 reviews, ~70 weekly price observations), not distinguishable from noise. The original hypothesis - that the index would lead price - is **not supported** by this pilot.
 
## Bug Found & Fixed
A label-case mismatch (`'Positive'` vs `'positive'`) caused an initial summary statistic to incorrectly report "100% neutral" sentiment. Root-caused via inspection of raw model outputs and corrected before final analysis - underlying index calculations were unaffected, but the reporting bug would have produced a misleading narrative if left uncorrected.
 
## Path to Production
To make this a viable signal: (1) scrape 500+ reviews per week via BeautifulSoup/Selenium across Amazon, Reddit, and tech press, (2) extend the time series to 2+ years for statistical power, (3) test multiple brands to assess generalisability.
 
## Tools
Python, FinBERT (Hugging Face), pytrends, yFinance, Pandas
