# 02 - AI Financial Sentiment Analyser
 
## Objective
Deploy a pre-trained transformer model to classify financial news sentiment and combine it with quantitative Sharpe-ratio data into a weighted trading signal framework.
 
## Data
- Financial news headlines (mix of real and representative headlines across AAPL, TSLA, GOOGL, JPM, MSFT)
- Portfolio Sharpe ratios from Project 01
## Methodology
1. **Model:** FinBERT (ProsusAI/finbert) - a 110-million parameter transformer pre-trained on financial text, deployed via Hugging Face `pipeline`
2. **Pipeline design:** confidence scoring per headline, sample-size confidence warnings (LOW/MEDIUM/HIGH based on headline count), contrarian signal flagging for strongly negative sentiment
3. **Signal construction:** combined score = 60% Sharpe ratio (fundamentals) + 40% sentiment score, producing BUY/HOLD/SELL signals per stock
## Key Results
| Stock | Signal | Sharpe | Sentiment | Combined Action |
|---|---|---|---|---|
| MSFT | BUY | 2.10 | Positive | Increase weight |
| TSLA | SELL | 0.82 | Negative | Hold - fundamentals override |
| AAPL | BUY | 1.93 | Positive | Increase weight |
 
## Key Learning
A single negative headline about Tesla (stock crash) produced a "SELL" sentiment signal - but combined with fundamentals (Sharpe 0.82, below the 1.5 threshold), the framework correctly flagged this as a **contrarian opportunity** rather than a blind sell signal. This demonstrates the value of combining AI-derived sentiment with quantitative context rather than acting on either signal alone.
 
## Limitations
Small headline samples (1-2 per stock) reduce statistical reliability - addressed via explicit "Data_Confidence: LOW" flags in the output rather than hiding the limitation.
 
## Tools
Python, Hugging Face Transformers, FinBERT, PyTorch, Pandas
 
