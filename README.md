# 📈 Bank Stock Analysis — Financial Crisis to Recovery (2006–2016)

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=flat&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat&logo=jupyter)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?style=flat&logo=pandas)
![yfinance](https://img.shields.io/badge/yfinance-Stock%20Data-9cf?style=flat)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-blueviolet?style=flat)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat)

An in-depth exploratory data analysis of six major US bank stocks across one of the most turbulent decades in financial history — from the lead-up to the 2008 financial crisis all the way through the recovery to 2016.

This project goes beyond standard price and return analysis to answer questions like: *How correlated did banks become during the panic? Who recovered fastest? Which bank gave the best risk-adjusted return?*

---

## 🏦 Banks Analysed

| Ticker | Bank |
|--------|------|
| `BAC` | Bank of America |
| `C` | CitiGroup |
| `GS` | Goldman Sachs |
| `JPM` | JPMorgan Chase |
| `MS` | Morgan Stanley |
| `WFC` | Wells Fargo |

**Period:** January 2006 → January 2016 (~2,500 trading days)

---

## 📊 What's in the Notebook

### Part 1 — Core Analysis
| Section | Description |
|---------|-------------|
| Data Loading | Pull 10 years of OHLCV data via `yfinance` |
| Max Close Prices | Peak closing price per bank over the full period |
| Daily Returns | `pct_change()` on close prices; returns DataFrame |
| Pairplot | Visualise return correlations and outliers across all banks |
| Best & Worst Days | Dates of peak gains and losses — 4 banks share the same worst day |
| Risk (Std Dev) | Riskiest bank for full period vs 2015 only |
| Return Distributions | Histogram + KDE for MS 2015 and Citi 2008 |
| Close Price Charts | Individual and combined line plots for all 6 banks |
| Moving Averages | 30-day rolling average vs close price for BAC during 2008 |
| Correlation Heatmap | Static and clustered correlation between bank close prices |
| Technical Analysis | Candlestick chart, SMA, and Bollinger Bands via Plotly |

### Part 2 — Extended EDA
| Section | Description |
|---------|-------------|
| Crisis Impact Score | % drop from pre-crisis peak to crisis trough — ranked |
| Sharpe Ratio | Risk-adjusted returns across 4 time periods: full, pre-crisis, crisis, recovery |
| Max Drawdown | How far each bank fell from its running peak at any point in time |
| Rolling Correlation | 90-day rolling correlation vs JPMorgan — did banks converge during the panic? |
| Volatility Regimes | 30-day rolling annualised volatility — calm vs storm periods |
| Volume Analysis | Did panic show up in trading volume? (Spoiler: yes) |
| Recovery Timeline | Normalised price from crisis low — who bounced back fastest? |
| Final Insights | Summary of 8 key findings with written narrative |

---

## 💡 Key Findings

1. **CitiGroup was the hardest hit** — ~95% peak-to-trough price drop, requiring a US government bailout
2. **Jan 20, 2009 was the worst day for most banks** — four of six hit their lowest single-day return on the same date
3. **JPMorgan had the best Sharpe Ratio** over the full period — consistently the best risk-adjusted performance
4. **Wells Fargo recovered the fastest** from the crisis low — strongest relative rebound by 2016
5. **Rolling correlations spiked to ~0.95 during the crisis** — banks stopped behaving independently and moved in lockstep
6. **Volatility exploded 5–10× in 2008** — Citi's annualised vol went from ~20% to over 100%
7. **Volume confirmed the panic** — trading volume hit multi-year highs in September–October 2008
8. **Most banks hadn't returned to pre-crisis prices by 2016** — the recovery took the full 7-year window and then some

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `yfinance` | Pull historical stock data directly from Yahoo Finance |
| `pandas` | Data manipulation, multi-level indexing, rolling calculations |
| `numpy` | Numerical operations, Sharpe ratio calculations |
| `matplotlib` | Base plotting |
| `seaborn` | Statistical visualisations, heatmaps, pairplots |
| `plotly` + `cufflinks` | Interactive candlestick charts and technical analysis plots |

---

## 📁 Project Structure

```
bank-stock-analysis/
│
├── 03-Finance_Project_Extended.ipynb   
└── README.md
```

---

## 📌 Notes

- Data is fetched live via `yfinance` every time the notebook runs — prices may differ slightly from historical records due to dividend adjustments
- The technical analysis section (candlestick, SMA, Bollinger Bands) requires `cufflinks` and `plotly` — these are optional and the rest of the notebook runs without them
- All analysis is for educational purposes only — **not financial advice**

---

## 📄 License

This project is open source under the [MIT License](LICENSE).
