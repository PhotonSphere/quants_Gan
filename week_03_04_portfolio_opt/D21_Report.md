# Portfolio Management and Optimization: Summary Report (Week 3)

This report summarizes six days of research and analysis (Day 15–Day 20) on portfolio management and optimization.  
The focus was on **diversification, statistical evaluation of strategies, backtesting mean-variance optimization, building multi-asset portfolios, and comparing risk-adjusted performance metrics**.

---

## 📌 D15: Role of Diversification

- **Foundation**: Modern Portfolio Theory (MPT), introduced by Harry Markowitz (1952).  

### Risk–Return Trade-off
- Investors maximize expected returns while minimizing risk (variance/standard deviation).  
- The **Efficient Frontier** represents optimal portfolios balancing this trade-off.

### Portfolio Risk
- Not a weighted average of individual risks.  
- Driven by **covariances** and correlations between assets.

### Power of Diversification
- With imperfectly correlated assets, volatility is reduced.  
- Eliminates idiosyncratic risk without lowering expected returns.  
- Basis of the **Efficient Frontier**.

---

## 📌 D16: Diversification Effect – Statistical Tests

**Strategies Tested (on Nifty50, 3 years daily data):**
- Equal-Weight (baseline)  
- Minimum Variance (Min-Var)  
- Maximum Sharpe (Max-Sharpe)  
- Hierarchical Risk Parity (HRP)  

**Methodology:**
- Quarterly returns and metrics: return, volatility, Sharpe ratio, max drawdown.  
- Tests: Paired t-test, Wilcoxon Signed-Rank Test, Permutation Test, Bootstrap CIs.  

**Key Findings:**
- **Max-Sharpe**: Sharpe 1.70, annual return 42.91%, significant outperformance (*p < 0.05*).  
- **Min-Var**: Lower volatility, weakest returns (small effect size, Cohen’s d = 0.292).  
- **HRP**: No significant improvement over Equal-Weight.  

**Conclusion:**  
Optimization (esp. Max-Sharpe) offered measurable and statistically significant advantages over naïve diversification.

---

## 📌 D17: Mean-Variance Optimization (MVO) Backtest

**Implementation:**
- Data: 2019–2021 (training), 2022–2025 (forward test).  
- Tools: CVXPY vs PyPortfolioOpt.  

**Findings:**
- **Training**: Max-Sharpe concentrated (INFY 37.22%, ASIANPAINT 30.11%).  
  - Return: 36.81%, Sharpe 1.428.  
- **Forward Test**: Performance collapsed.  
  - Sharpe: Negative (-0.131, -0.058).  
  - Equal-Weight benchmark Sharpe = 0.636.  
- Concentration risk caused failure (ASIANPAINT, BAJFINANCE reversed).  

**Insights:**
- Cap single-asset/sector weights.  
- Add **multi-asset diversification** (equities, debt, gold, international).  
- Use **dynamic rebalancing** to adjust for regime shifts.

---

## 📌 D18: Multi-Asset GMV and Tangency Portfolios

**Assets Added:**  
Indian equities + Debt ETFs (EBBETF0430, LTGILTBEES) + Gold (AXISGOLD) + Global equity (^GSPC).  

**Portfolios Constructed:**
- **GMV**: Minimized volatility (3.63%).  
  - Dominated by EBBETF0430 (85.36%).  
- **Tangency**: Maximized Sharpe (1.459).  
  - Debt-heavy (62.88% EBBETF0430) but diversified with Gold (14.32%), Equities (ICICIB22, INFY).  

**Takeaway:**  
Debt assets = stabilizing core.  
Gold + equities = enhanced return potential.

---

## 📌 D19 & D20: Sharpe vs Sortino Analysis

### Metric Distinction
- **Sharpe Ratio** = Return / Total Volatility.  
- **Sortino Ratio** = Return / Downside Volatility (ignores positive swings).

### Results
- **Defensive assets** (EBBETF0430, AXISGOLD) scored higher on Sortino → strong downside protection.  
- **Sharpe ranking**: Tangency (0.0903) > GMV.  
- **Sortino ranking**: GMV (0.1999) > Tangency (0.1864).  

### Strategic Insight
- Tangency → **growth phases**.  
- GMV → **resilient in risk-off environments**.  
- Adaptive blend of both = cycle-robust performance.

---

## 📌 Overall Conclusions

- **Diversification** reduces unsystematic risk and forms the foundation of optimal portfolios.  
- **Max-Sharpe** works in-sample but fails out-of-sample without controls (concentration risk).  
- **Multi-asset allocation** (equities, debt, gold, global) adds stability and resilience.  
- **Risk metrics matter**: Sharpe = efficiency, Sortino = downside resilience.  

**Practical Recommendation:**  
Adopt an **adaptive allocation framework**, shifting between Tangency (Sharpe-optimal) and GMV (Sortino-optimal) depending on market regime.

---
