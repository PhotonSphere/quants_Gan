# Portfolio Optimization & Robustness Report: BL vs. RP vs. Kelly  

---

## I. Introduction and Methodology  

This analysis evaluates three advanced portfolio optimization strategies—**Black–Litterman (BL)**, **Risk Parity (RP)**, and **Kelly Criterion (KC)**—applied to a multi-asset portfolio including Indian equities, Bonds, Gold, S&P 500 ETF, Bitcoin, and Ethereum.  

The primary goal is to overcome the instability and extreme allocations associated with traditional Mean-Variance Optimization (MVO).  

| Method           | Key Feature                                   | Primary Input                        | Best When                                                                 |
|------------------|-----------------------------------------------|--------------------------------------|----------------------------------------------------------------------------|
| Black–Litterman  | Incorporates subjective views                 | Blended Expected Returns (Market Equilibrium + Views) | You want to blend market consensus with private insights |
| Risk Parity (ERC)| Equalizes risk contribution per asset         | Covariance Matrix (Σ)                 | You distrust return forecasts but trust risk models                        |
| Kelly Criterion  | Maximizes expected log growth rate of wealth  | Highly accurate Expected Returns (μ)  | You seek aggressive growth with reliable forecasts                         |

---

## II. Day 23: Asset Correlation and Diversification Analysis  

**1. VIX as a Crisis Hedge**  
- The India Volatility Index (INDIAVIX) acted as the best defensive tool and true crisis hedge, with strong negative correlation (-0.571) to equity/bond portfolios.  
- VIX rises when equities fall, but since VIX instruments are not investable long-term (due to contango decay), proxies like **Gold ETFs** and **Long-term Government Bonds (LTGILTBEES.NS)** were considered for hedging.  

**2. Cryptocurrency Diversification**  
- Bitcoin (BTC-USD) and Ethereum (ETH-USD) were classified as **moderate diversifiers** with average correlations of 0.33 and 0.38, respectively.  
- They reduce domestic Indian concentration risk but remain tied to global risk-on cycles.  
- High correlation between BTC and ETH (0.73) suggests that including both increases intra-crypto concentration risk.  

**3. Dynamic Allocation Suggestion**  
- Assuming a 65% equity weight, a dynamic allocation was suggested:  
  - **VIX proxies (Diversifier):** ~9.8%  
  - **BTC/ETH (Moderate Diversifiers):** ~3.2% each  

---

## III. Day 24: Black–Litterman Robustness and Pipeline Development  

**1. Initial Concentration Issues**  
- Early BL implementations with weak priors or historical returns as views led to concentrated allocations.  
- Example: Min-vol optimization yielded ~73% in Bharat Bond ETF (EBBETF0430.NS), and max Sharpe optimization allocated ~66% to the same asset.  

**2. Enhanced Robust BL Pipeline**  
- A robust pipeline was introduced using:  
  - **Market-implied priors** (market capitalization & risk aversion δ).  
  - **Controlled view uncertainty (Ω)** with iterative scaling to avoid concentration.  
  - **Post-Optimization Capping** (e.g., 15–25% max per asset), redistributing excess weight proportionally.  

- *Result Example:* With a 15% cap across all assets, the portfolio achieved a Herfindahl index of 0.118, indicating strong diversification.  

---

## IV. Day 25: Comparative Performance and Solver Enhancement  

**1. Naive Out-of-Sample (OOS) Results (Pre-Improvement)**  
- **Risk Parity:** Sharpe 2.98, lowest Max Drawdown (-3.0%), volatility 0.0512.  
- **Black–Litterman:** Sharpe 2.39, CAGR 0.1768, consistently strong.  
- **Kelly Criterion:** Sharpe 2.09, CAGR 0.0752, lagged significantly.  

**2. Transition to Robust Solvers**  
- **Robust Kelly:** Upgraded to a CVXPY-based quadratic formulation with fractional leverage control.  
- **Robust Risk Parity:** Improved solver using SciPy minimization to equalize risk contributions more stably.  

---

## V. Day 26 & 27: Stress Testing and Final Comparative Analysis  

**1. Stress Testing Framework**  
Stress testing was applied to evaluate hidden vulnerabilities against five hypothetical shocks:  
1. Equities -10%  
2. Crypto -20%  
3. Gold +5%, Bonds +3%  
4. All risk assets -15% (systemic downturn)  
5. Safe haven rally (Bonds +5%)  

**2. Robust Out-of-Sample Performance**  

| Strategy          | CAGR   | Ann. Vol | Sharpe | Max DD  | End Value |
|-------------------|--------|----------|--------|---------|-----------|
| Black–Litterman   | 0.1768 | 0.0656   | 2.39   | -5.3%   | 1.38      |
| Risk Parity       | 0.1857 | 0.0694   | 2.39   | -4.6%   | 1.40      |
| Kelly Criterion   | 0.2190 | 0.0962   | 2.07   | -6.5%   | 1.48      |

- **Kelly Criterion:** Highest CAGR but highest volatility and drawdown.  
- **Risk Parity & BL:** Identical Sharpe ratios with lower risk.  

**3. Comparative Stress Test Results**  

| Scenario                  | BL Return | RP Return | KC Return |
|----------------------------|-----------|-----------|-----------|
| Equities -10%              | -2.08%    | -5.30%    | -6.50%    |
| All risk assets -15%       | -7.73%    | -11.05%   | -13.39%   |
| Gold +5%, Bonds +3%        | +1.62%    | +0.96%    | +0.39%    |

**Key Insights:**  
- **Downside Protection:** BL was the most resilient. Its equity shock loss (-2.08%) was less than half of RP and KC.  
- **Systemic Risk:** KC suffered the largest systemic loss (-13.39%), BL the smallest (-7.73%).  
- **Safe Haven Capture:** BL captured the largest positive gains (+2.00%) from gold/bond rallies. KC showed minimal benefit.  
- **Crypto Risk:** BL showed no loss in crypto shock (0.00%), whereas KC lost the most (-1.43%).  

---

## VI. Strategic Implications and Conclusion  

**1. Optimal Strategy Selection**  
- **Black–Litterman:** Most resilient and balanced; ideal for stable growth with strong diversification.  
- **Risk Parity:** Strong Sharpe, diversified, but weaker in systemic crises.  
- **Kelly Criterion:** Aggressive, high-growth but fragile; requires leverage discipline.  

**2. Value of Stress Testing**  
Stress testing enhances strategy and supports decisions by:  
- Validating diversification effectiveness.  
- Identifying which shocks cause the largest losses.  
- Translating insights into actionable strategies (e.g., hedging, rebalancing, scenario-specific playbooks).  

**Final Takeaway:**  
Black–Litterman emerges as the most robust approach for long-term portfolio construction. Risk Parity provides a strong core strategy but should be paired with hedging, while Kelly Criterion suits only high-risk investors with capacity for volatility and drawdowns.  
