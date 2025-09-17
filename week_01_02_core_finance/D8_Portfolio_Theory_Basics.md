# Portfolio Theory Basics

Markowitz Portfolio Selection, introduced in his seminal **1952 paper**, is the foundation of **Modern Portfolio Theory (MPT)**.  
It provides a mathematical framework for investors to build optimal portfolios by balancing **risk and return**.  

👉 Core principle: An investor should consider the **risk of a portfolio as a whole**, not just the individual assets within it.  

---

## Key Concepts

### Mean-Variance Framework
- Investors select portfolios based on **expected return (mean)** and **risk (variance)**.  
- Portfolios are mathematically evaluated for both risk and return.  
- Goal:  
  - Maximize return for a given level of risk.  
  - Minimize risk for a given level of return.  

### The Power of Diversification
- Markowitz proved that overall portfolio risk is **not** just the weighted sum of individual risks.  
- Instead, it depends on **covariance** (how asset returns move together).  
- By combining assets with low or negative correlation, total risk can be reduced without lowering expected return.  

### The Efficient Frontier
- Plotted on a **risk-return graph** (risk = x-axis, return = y-axis).  
- Represents the set of all **optimal portfolios**.  
- Any portfolio below the frontier is **sub-optimal** because it offers:  
  - Less return for the same risk.  
  - More risk for the same return.  

---

## Practical Implications

- Shifted investment management from **stock picking** to **portfolio construction**.  
- Provided institutional investors with a **roadmap for mathematically optimized portfolios**.  
- Limitations:  
  - Sensitive to input data.  
  - Assumes normally distributed returns.  
- Still remains the **cornerstone of financial theory** and a foundation for advanced models (e.g., **Black-Litterman**).  

---

## Key Takeaways from Markowitz’s Work

- 📄 **Paper**: *“Portfolio Selection”* (1952), *Journal of Finance*, Vol. 7, Issue 1, pp. 77–91.  
- **Risk and Return are Related**: Consider portfolios, not individual stocks in isolation.  
- **Diversification**: More than “not putting all eggs in one basket”; mathematically reduces risk via covariance.  
- **Mean-Variance Optimization (MVO)**:  
  - Maximize return for given risk.  
  - Minimize risk for given return.  
- **Efficient Frontier**: Optimal risk-return curve; portfolios below it are sub-optimal.  

---

## Classic Portfolio Construction

### Modern Portfolio Theory (MPT)
- Developed by **Harry Markowitz (1952)**.  
- Uses **mean-variance optimization** to maximize return for a given risk.  
- Emphasizes **diversification** across imperfectly correlated assets.  
- Produces the **efficient frontier**.  

### Black-Litterman Model
- Developed at **Goldman Sachs (1990s)**.  
- Extension of MPT to address:  
  - High sensitivity to input parameters.  
  - Concentrated/unintuitive portfolios.  
- Starts with **market equilibrium allocation** (e.g., cap-weighted).  
- Investors add **views/forecasts** with confidence levels.  
- Produces more **stable, diversified portfolios**.  

### 60/40 Portfolio
- Allocates **60% equities / 40% bonds**.  
- Equities = growth, Bonds = stability & income.  
- Simple but historically balanced risk-return.  

---

## Asset Allocation

### Strategic Asset Allocation (SAA) 🗺️
- Long-term, top-down approach.  
- Defines target mix (e.g., 60/40) based on:  
  - Risk tolerance.  
  - Liquidity needs.  
  - Investment horizon.  
- Reviewed periodically (not short-term).  
- **MVO in SAA**:  
  - Uses expected returns, standard deviations, and correlations.  
  - Generates portfolios on the efficient frontier.  

### Tactical Asset Allocation (TAA) 🏹
- Short-term, **active deviations** from SAA.  
- Exploits perceived market inefficiencies.  
- Example: Overweight international equities if expected to outperform.  
- **Overlay strategy** → success depends on forecasting skill.  

---

The main operation performed in **mean-variance optimization (MVO)** is minimizing the portfolio's volatility for a target return or maximizing the Sharpe ratio.
---
1. Minimization of Volatility 📉


This is the core mathematical operation. 
Given a target return `R_target`, the optimizer finds the set of portfolio weights `w_i` that minimizes the portfolio's variance, `σ_p²`.


**Objective function (to minimize):**


`w_min σ_p² = wᵀ Σ w`


**Subject to the constraints:**


- Portfolio's expected return equals the target return: 
 `wᵀ μ = R_target`
- Sum of all weights is 1: 
 `∑ w_i = 1`
- No short selling (optional): 
 `w_i ≥ 0`


Here, 
- `w` = vector of portfolio weights 
- `μ` = vector of expected returns for each asset 
- `Σ` = covariance matrix 


By repeating this minimization for a range of target returns, you can trace out the **efficient frontier**.


---


2. Maximization of Sharpe Ratio 🚀


This is a specific type of MVO that finds the single optimal portfolio on the efficient frontier. 
The Sharpe ratio measures **risk-adjusted return**, and maximizing it finds the portfolio with the highest return per unit of risk.


**Objective function (to maximize):**


`Sharpe(w) = (wᵀ μ − R_f) / sqrt(wᵀ Σ w)`


This is typically solved by minimizing the **negative Sharpe ratio**:


`w_min −( (wᵀ μ − R_f) / sqrt(wᵀ Σ w) )`


**Subject to the constraints:**


- Sum of all weights is 1: 
 `∑ w_i = 1`
- No short selling (optional): 
 `w_i ≥ 0`


Here, 
- `R_p` = portfolio's expected return 
- `R_f` = risk-free rate 

---
##### Both operations are forms of **constrained optimization**, where a numerical solver (like `scipy.optimize.minimize` in Python) finds the optimal weights that satisfy all the specified conditions.
---
# Minimum Variance Portfolio (MVP)

The **Minimum Variance Portfolio (MVP)** is a classical method within Modern Portfolio Theory (MPT), introduced by **Harry Markowitz (1952)**. It is a special case of Mean-Variance Optimization (MVO) where the goal is to minimize total portfolio risk (variance/volatility) without explicitly targeting expected returns.  

---

## Definition
The **Minimum Variance Portfolio** is the portfolio of risky assets that has the **lowest possible variance (risk)** among all combinations.  
- It represents the **leftmost point** on the Efficient Frontier.  

---

## Key Characteristics
- **Objective**: Minimize portfolio variance (risk).  
- **Constraint**: Portfolio weights sum to 1 (fully invested).  
- **Inputs required**: covariance matrix of asset returns.  
- **Types**:  
  - **Global Minimum Variance Portfolio (GMVP)** → absolute minimum variance portfolio.  
  - **Minimum Variance Frontier** → set of all variance-minimizing portfolios for given returns.  

---

## Mathematical Formulation

**Optimization Problem**  

$\min_w \sigma_p^2 = w^\top \Sigma w$

Subject to:  

$\sum_{i=1}^{n} w_i = 1, \quad w_i \geq 0 \text{(if short-selling is not allowed)}$

Where:  
- $\w$ = vector of portfolio weights  
- $\Sigma$ = covariance matrix of asset returns  

---

## Relationship with MVO
- **MVO (Markowitz Optimization)**: Balances **risk (variance)** and **reward (expected return)**.  
- **MVP**: Focuses **only** on minimizing risk, regardless of return.  

➡️ MVP is a **subset/special case** of MVO.  

---

## Applications
- Benchmark portfolio to compare against other strategies.  
- Starting point for constructing efficient portfolios.  
- Provides insights into diversification benefits.  

---

# MVP vs. MVO — Portfolio Weights

### 1. Minimum Variance Portfolio (MVP)

**Objective**: minimize variance only  

$w_{MVP} = \frac{\Sigma^{-1} \mathbf{1}}{\mathbf{1}^\top \Sigma^{-1} \mathbf{1}}$

- Inputs: only covariance matrix \(\Sigma\).  
- Result: global minimum variance portfolio (lowest risk).  
- No expected returns required.  

---

### 2. Mean-Variance Optimization (MVO)

**Objective**: balance risk and return.  
If investor targets a required expected return \(\mu_p\):  

$w_{MVO} =
\lambda \cdot \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^\top \Sigma^{-1}\mathbf{1}}
+ (1-\lambda) \cdot \frac{\Sigma^{-1}\mu}{\mathbf{1}^\top \Sigma^{-1}\mu}$

Where:  
- $\mu$ = vector of expected asset returns  
- $\Sigma$ = covariance matrix  
- $\mathbf{1} = vector of ones  
- $\lambda$ = parameter determined by target return \(\mu_p\)  

---

## Key Difference
- **MVP**: only considers risk → single closed-form portfolio.  
- **MVO**: balances risk & return → gives the efficient frontier of portfolios.  

---

## Takeaway
- **MVP = special case of MVO** with no return consideration.  
- **MVO generalizes MVP** by adding expected returns and investor preferences.  

---
## Mean-Variance Optimization (MVO) – Use & Limitations

### Uses of MVO
- 📐 **Quantitative Framework**: Provides a mathematical method to determine optimal portfolios.  
- 🔀 **Diversification Focus**: Emphasizes combining assets with low correlation.  
- 🧩 **Logical Basis**: Defensible rationale for allocation decisions.  

### Limitations of MVO
- ⚠️ **Sensitivity to Inputs**: Small changes in assumptions drastically alter results.  
- ⏳ **Single-Period Framework**: Ignores dynamic/long-term shifts in investor goals or markets.  
- 📊 **Assumptions about Returns**: Assumes normal distributions and variance as risk measure (ignores fat tails/extreme events).  
- 💰 **Real-World Constraints**: Ignores transaction costs, taxes, and security-specific restrictions.  

---

## MVO Summary

- **Use**: Cornerstone of quantitative asset allocation, provides diversification insights.  
- **Limitations**: Practical challenges make results unstable, static, and sometimes unrealistic.  

---
