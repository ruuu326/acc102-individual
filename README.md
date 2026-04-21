# Interactive Stock Comparison Tool

## 1. Problem & User

**Problem**: Which company performs better in terms of compound growth and risk-adjusted returns?

**Target User**: Individual investors and financial analysts.

## 2. Data

- **Source**: WRDS CRSP Monthly Stock Database
- **Access Date**: April 21, 2026
- **Time Period**: January 2015 - December 2025
- **Key Fields**: Monthly returns (ret), S&P 500 benchmark, 10-year Treasury yield

## 3. Methods

1. Download stock data from WRDS using Python `wrds` library
2. Calculate cumulative returns using compound interest formula: `(1 + ret).cumprod()`
3. Compute annualized return, volatility, Sharpe ratio, max drawdown, win rate, and beta
4. Generate 9 comparison charts including cumulative returns, Sharpe ratio, rolling beta, and correlation heatmap
5. Provide automated investment recommendation based on scoring system

## 4. Key Findings

Example: Apple vs Tesla (2015-2025)

| Metric | Apple | Tesla | S&P 500 |
|--------|-------|-------|---------|
| Total Return | 10.18x | 27.24x | 2.50x |
| Sharpe Ratio | 0.88 | 0.60 | 0.67 |
| Volatility | 27.58% | 62.34% | 15.00% |
| Max Drawdown | -30.4% | -67.7% | -33.0% |
| Beta | 0.95 | 1.85 | 1.00 |

- Tesla offers higher growth (27x vs 10x) but with much higher risk (62% volatility, -68% drawdown)
- Apple provides better risk-adjusted returns (Sharpe ratio: 0.88 vs 0.60)
- Tesla is more volatile than the market (Beta > 1), Apple is roughly in line with the market (Beta ≈ 1)
- Tesla experienced a much deeper drawdown (-68% vs -30%), indicating higher downside risk
- Both stocks outperformed the S&P 500 benchmark in total return

## 5. How to Run

### Steps
1. Run **Cell 1**: Connect to WRDS (enter your username and password when prompted)
2. Run **Cell 2**: Enter two stock tickers (e.g., AAPL, TSLA)
3. Run **Cell 3**: Wait for analysis to complete (downloads data, calculates metrics, generates 9 charts and report)
4. Run **Cell 4**: Close WRDS connection

## 6. Product Link / Demo

**Demo Video**: ACC102 video

## 7. Limitations & Next Steps

### Limitations

- Past performance does not guarantee future results
- Does not account for transaction costs or taxes
- Limited to CRSP database stocks
- Risk-free rate is estimated from Treasury yields

### Next Steps

- Allow users to select custom time periods
- Add more technical indicators (RSI, MACD)
- Build a Streamlit web interface
- Include dividend-adjusted returns
