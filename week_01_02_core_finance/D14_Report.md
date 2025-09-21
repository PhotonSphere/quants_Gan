# 📄 Report  
## Sharpe vs Drawdown – My Portfolio Recommendation  

---

### 1. Introduction  

Portfolio construction is a balance between maximizing returns and minimizing risk. Three popular strategies are:  

- **Mean-Variance Optimization (MVO):** Finds the portfolio with the maximum Sharpe ratio.  
- **Risk Parity (Inverse Volatility):** Balances risk contributions across assets.  
- **Equal Weighted (EW):** Simplest approach with equal allocation to each asset.  

This report compares these strategies using a **5-year backtest** on five NIFTY50 stocks (Reliance, HDFC Bank, Infosys, TCS, ITC).  

---

### 2. Efficient Frontier & Sharpe Ratio  

- The **Efficient Frontier** shows the set of optimal portfolios for a given risk level.  
- The **Sharpe ratio** measures excess return per unit of risk.  

**Maximizing Sharpe ratio → identifies the optimal portfolio on the Efficient Frontier.**  

**Key Insight:**  
- Higher Sharpe ratio = better risk-adjusted returns.  
- But Sharpe does **not directly account for drawdowns** (large losses from peak).  

---

### 3. Allocation Comparison  

| Strategy         | Allocation Summary                                    | Key Features                               |
|------------------|--------------------------------------------------------|--------------------------------------------|
| **MVO (Max Sharpe)** | INFY ~65%, Reliance ~24%, HDFC ~12%, TCS/ITC ~0%     | Concentrated allocation, highest Sharpe     |
| **Risk Parity**  | ~19.5% median weight                                         | Balanced risk contributions                 |
| **Equal Weighted** | 20% per stock                                         | Simplest, baseline comparison               |  

---

### 4. Performance Results (5-Year Backtest)  

| Strategy         | Total Return | Annualized Return | Volatility | Sharpe Ratio |
|------------------|--------------|-------------------|------------|--------------|
| **MVO (Max Sharpe)** | 141.7%       | 19.3%             | 1.04%      | 18.5         |
| **Risk Parity**  | 86.3%        | 13.3%             | 0.91%      | 14.6         |
| **Equal Weighted** | 74.9%        | 11.8%             | 0.94%      | 12.6         |  

---

### 5. Sharpe vs Drawdown Analysis  

- **MVO (Max Sharpe):**  
  - Highest Sharpe ratio and returns.  
  - Concentrated in Infosys → higher drawdown risk.  

- **Risk Parity:**  
  - More stable with lower volatility.  
  - Drawdowns controlled by balancing across stocks.  

- **Equal Weighted:**  
  - Simplest, but least efficient.  
  - No optimization → weaker Sharpe ratio and returns.  

---

### 6. Recommendation  

- If the goal is **maximum returns and efficiency** → choose **MVO**.  
- If the goal is **capital protection and minimizing drawdowns** → choose **Risk Parity**.  

**Final Call:**  
- Recommend **MVO with constraints** (e.g., cap sector/stock weights at 30%).  
- This delivers strong risk-adjusted returns while mitigating concentration risk.  
- Risk Parity can serve as a fallback option for **risk-averse investors**.  

---

### 7. Conclusion  

The comparative analysis shows that:  
- **MVO dominates** in Sharpe ratio and total returns, but at the cost of **concentration risk**.  
- **Risk Parity provides** more balanced exposure and lower drawdown potential.  
- A **blended or constrained MVO** approach represents the best compromise for long-term investors seeking both **performance and stability**.  
