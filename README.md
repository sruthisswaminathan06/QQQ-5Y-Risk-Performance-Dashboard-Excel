# QQQ (Nasdaq-100) — 5-Year Performance & Risk Dashboard (Excel)

An executive-friendly **portfolio performance + risk dashboard** built in **Excel** using **5 years of daily historical prices** for **Invesco QQQ (QQQ)**.  
Designed to showcase core finance analytics skills: returns, compounding, drawdowns, volatility, and clear reporting.

---

## 📌 Dashboard Highlights (5-Year Summary)
**Key metrics from this analysis:**
- **CAGR (Annualized Return): 14%**
- **Annualized Volatility: 23%**
- **Sharpe Ratio: 0.43** *(based on chosen risk-free rate assumption)*
- **Max Drawdown: -36%**

**What this tells us (in plain English):**
- QQQ delivered strong growth over 5 years (**14% CAGR**) but with meaningful risk (**23% vol**) and substantial downside during stress periods (**-36% max drawdown**).

---

## 🖼️ Dashboard Preview
> Add your screenshots to the repo and update the paths below.

- Main Dashboard: ![image alt](https://github.com/sruthisswaminathan06/QQQ-5Y-Risk-Performance-Dashboard-Excel/blob/c46fb56e0e8fab0d893356555c116e2c224861aa/Dashboard.png)
- Equity Curve: `screenshots/equity_curve.png
- Drawdown: `screenshots/drawdown.png`
- Rolling Volatility: `screenshots/rolling_vol.png`

---

## 🎯 Objective
Build a simple, recruiter-ready dashboard that answers:
1. **How did QQQ perform over the last 5 years?**
2. **How risky was it (volatility + max drawdown)?**
3. **When did risk spike (rolling volatility regimes)?**

---

## 📊 Data Source
- **QQQ daily historical prices** downloaded from Nasdaq (Historical Data page). [1](https://excel-tutorial.com/add-slicer-with-excel-online/)

---

## 🧰 Tools & Compatibility
- **Microsoft Excel (web/free compatible)**
- Formulas + charts only (no VBA/macros)  
  - Note: **Excel for the web does not support creating/running/editing VBA macros**, so this project intentionally avoids macros for maximum portability. [2](blob:https://www.microsoft365.com/a3ed745e-59d4-42c2-93ae-e91fc1a599fa)

---

## 🧠 Methodology (How the metrics were built)
This project uses standard portfolio analytics:

### 1) Daily Returns
Computed using close-to-close returns:
- `Daily Return = (Close_t / Close_(t-1)) - 1`

### 2) Equity Curve (Growth of $1)
Compounded daily returns to show growth of $1 invested:
- `Equity_t = Equity_(t-1) * (1 + Daily Return_t)`

### 3) Drawdown
Measures percentage drop from the running peak of the equity curve:
- `Running Peak_t = MAX(Running Peak_(t-1), Equity_t)`
- `Drawdown_t = (Equity_t / Running Peak_t) - 1`

### 4) Rolling 20-Day Annualized Volatility
Uses the last 20 daily returns and annualizes using √252:
- `RollingVol_t = STDEV(returns last 20 days) * SQRT(252)`

> Annualization convention assumes **252 trading days** per year (standard in finance).

---

## 📈 Charts Included (3-Core Chart Setup)
To keep the dashboard executive-friendly, only three charts are used:
1. **Equity Curve (Start = $1)**
2. **Drawdown Over Time**
3. **Rolling 20-Day Annualized Volatility**

These three visuals cover performance, downside risk, and changing risk regimes.

---

## 📂 Repository Structure
```text
QQQ-5Y-Risk-Performance-Dashboard-Excel/
  QQQ_5Y_Risk_Performance_Dashboard.xlsx
  QQQ_1Page_Memo.pdf
  screenshots/
    dashboard.png
    equity_curve.png
    drawdown.png
    rolling_vol.png
  README.md
