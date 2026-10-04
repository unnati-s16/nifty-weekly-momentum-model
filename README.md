# Weekly Momentum & Relative Strength Model (Nifty 500)

A quantitative backtesting framework that evaluates cross-sectional momentum and relative strength across the Nifty 500 universe on weekly OHLCV data.

The system implements multi-factor signal ranking, dynamic regime filtering, volatility adjusted position sizing and transaction cost accounting to simulate realistic deployment.

## 1. Investment Thesis and Strategy Logic
Intermediate term outperformance tends to persist over 3-12 month horizons. However, raw momentum in emerging markets like India suffers from severe tail risk events and high turnover during chop.

This model addresses these vulnerabilities by:
- **Operating on weekly Timeframe:** It filters out daily market noise and reduces transaction drag while allowing momentum trends spanning months to play out.
- **Cross-Sectional Ranking:** Identifies leaders relative to the Nifty 500 universe rather than relying solely on absolute price trend.
- **Regime Filtering:** Allocates dynamically to cash or defensive holdings when broad market index momentum breaks down.

## Performance Summary (2017 – 2026 Unified Run)

| Metric | Result |
| :--- | :--- |
| **Initial Capital** | ₹10,00,000.00 |
| **Final Capital** | ₹65,09,327.04 |
| **Total Return** | +550.93% |
| **CAGR** | 21.65% |
| **Unified Sharpe Ratio** | 0.72 |
| **Max Drawdown** | -53.32% |
| **Total Trades** | 384 |
| **Win Rate** | 37.50% |

---

## Data Sources
* Historical data (2000–2024): Kaggle NSE Historical Dataset.
* Live & forward data (2024+): Nifty 500 via Yahoo Finance (`yfinance`).
