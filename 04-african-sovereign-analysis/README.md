# 04 - African Sovereign Investment Analysis
 
## Objective
Test the thesis that Ghana presents a superior risk-adjusted patient-capital opportunity relative to Kenya, using a multi-source, multi-dimensional country attractiveness model across 5 African markets.
 
## Data
- **World Bank API** - 13 indicators (GDP growth, inflation, FDI, debt, digital penetration, etc.) across 5 years
- **IMF World Economic Outlook (April 2024)** - forward estimates filling World Bank data gaps
- **Google Trends (pytrends)** - 5 consumer/business search signals per market
## Methodology
A 100-point weighted Country Attractiveness Index calibrated for 5-10 year patient capital:
 
| Dimension | Weight | Rationale |
|---|---|---|
| Macro Stability | 30% | Protects real returns |
| Growth Trajectory | 25% | Forward return potential |
| Digital Economy | 20% | Future value creation |
| Market Maturity | 15% | Institutional depth |
| Consumer Momentum | 10% | Leading indicator |
 
Validated across 5 sensitivity scenarios (Base Case, Growth Focus, Stability Focus, Digital Focus, Equal Weights).
 
## Key Results
| Rank | Country | Score | Verdict |
|---|---|---|---|
| 1 | South Africa | 68.3/100 | Attractive |
| 2 | Ghana | 60.7/100 | Attractive |
| 3 | Kenya | 57.7/100 | Monitor |
| 4 | Egypt | 48.0/100 | Monitor |
| 5 | Nigeria | 45.2/100 | Selective |
 
**Kenya vs Ghana (core thesis):** Ghana leads by 3.0 points, robust across 4/5 sensitivity scenarios - driven by FDI inflows (2.1% vs 0.8% of GDP) and a perfect digital economy score. Kenya's counter-strength is macro stability (inflation 4.5% vs Ghana's 22.8%).
 
## Recommendation
Sector-dependent dual allocation: **60% Ghana** (growth/fintech/digital infrastructure) / **40% Kenya** (capital preservation, income mandates).
 
## Key Learning - Data Quality
An initial model run used incomplete World Bank data, which suppressed several countries' scores (most notably South Africa). The issue was identified, the pipeline was corrected with verified indicators plus IMF estimates, and **all conclusions, dashboards, and the investment memo were revised accordingly** before finalisation. This is documented as a methodology safeguard, not hidden.
 
## Deliverables
- Full Colab notebook (this folder)
- 2-page Investment Memorandum (PDF)
- HTML executive dashboard
- Power BI interactive dashboard
## Tools
Python, World Bank API, IMF data, Google Trends (pytrends), Pandas, Matplotlib, Power BI
 
