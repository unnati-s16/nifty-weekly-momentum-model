# nifty-weekly-momentum-model
NSE weekly cross sectional momentum trading model with Nifty 200 SMA filter
# NSE Weekly Cross-Sectional Momentum Strategy

A quantitative multi-block weekly momentum trading model tested across NSE equities, incorporating relative strength ranking and a broad-market regime filter.

---

## Strategy Rules

### 1. Universe Selection
* **Lookback Buffer:** Top 500 liquid stocks selected based on total turnover over a 1-year lookback buffer.
* **Testing Structure:** Multi-block 2-year rolling execution blocks to mitigate lookahead and survivorship bias.

### 2. Market Regime Filter
* **Benchmark:** Nifty 50 / BSE Sensex against its 200-day Simple Moving Average (SMA).
* **Filter Rule:** New trade entries are strictly permitted only when the index trades above its 200-day SMA.

### 3. Entry & Execution Logic
* **Signal Scan:** Friday weekly close.
* **Execution:** Monday market open (with slippage and transaction fee modeling).
* **Entry Filters:**
  * Weekly RSI(14) > 60
  * Weekly Supertrend(8, 2.5) Direction == Bullish (1)
  * Cross-Sectional Relative Strength (RS) Percentile ≥ 92
* **Portfolio Sizing:** Maximum 15 positions, equally allocated across available cash.

### 4. Exit Rules
* Exit on Monday open if:
  * Individual stock RSI drops below 40.
  * Supertrend reverses to Bearish (-1).
  * Benchmark index breaks below its 200-day SMA.
  * End of 2-year block force-liquidation.

---

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
