# Apple vs Microsoft: Compound Growth Analysis (2015-2025)

## 1. Problem & User

**Problem**: Which company (Apple or Microsoft) achieved higher compound growth from 2015 to 2025? How do their risk-adjusted returns compare?

**Target User**: Individual investors seeking stock selection guidance and financial analysts comparing risk-return trade-offs.

## 2. Data

- **Source**: WRDS (Wharton Research Data Services) - CRSP Monthly Stock Database
- **Access Date**: April 18, 2026
- **Time Period**: January 2015 - December 2025
- **Key Fields**: Monthly returns (ret), date
- **Stocks**: Apple (PERMNO: 14593), Microsoft (PERMNO: 10107)

## 3. Methods

1. Download monthly return data using Python `wrds` library
2. Clean data and remove missing returns with `dropna()`
3. Calculate cumulative returns using compound interest formula: `(1 + r).cumprod()`
4. Compute annualized return, volatility (std × √12), and Sharpe ratio ((return - 2%)/volatility)
5. Calculate maximum drawdown and win rate
6. Generate comparison visualizations using matplotlib

## 4. Key Findings

| Metric | Apple | Microsoft |
|--------|-------|-----------|
| Cumulative Return | 10.18x (917.9%) | 10.56x (955.9%) |
| Sharpe Ratio | 0.883 | 1.134 |
| Max Drawdown | -30.4% | -30.5% |
| Annual Volatility | 27.58% | 21.88% |
| Future Value ($10k) | $101,793 | $105,589 |

**Conclusion**: Microsoft achieved higher total returns, better risk-adjusted performance, and lower volatility.

## 5. Product Link / Demo

**Demo Video**: [Insert your demo video link here]

## 6. Limitations & Next Steps

### Limitations

- Historical data does not guarantee future performance
- Assumes constant 2% risk-free rate
- Does not account for transaction costs or taxes
- Limited to two stocks

### Next Steps

- Include more stocks for broader comparison
- Add dividend reinvestment calculation
- Test different time periods (e.g., pre-COVID vs post-COVID)
- Build an interactive Streamlit app for user-defined stock comparison
