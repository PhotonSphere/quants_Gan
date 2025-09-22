# 📊 Risk & Return in Portfolio Construction

---

## 📌 Return  

The **return of a portfolio** is the weighted average of the expected returns of the individual assets.  

**Formula:**  

$$
E(R_p) = \sum_{i=1}^n w_i \, E(R_i)
$$

Where:  
- $$w_i$$ = weight of asset $i$  
- $E(R_i)$ = expected return of asset $i$  

👉 **Return reflects the reward investors expect for bearing risk.**

---

## 📌 Risk  

The **risk of a portfolio** is measured by the variance (or standard deviation) of returns.  
Unlike return, risk is **not** simply the weighted average of individual risks.  

**Formula (Variance of Portfolio Returns):**  

$$
\sigma_p^2 = \sum_{i=1}^n w_i^2 \sigma_i^2 + \sum_{i \neq j} w_i w_j \, \text{Cov}(R_i, R_j)
$$

Where:  
- $\sigma_i^2$ = variance of asset $i$  
- $\text{Cov}(R_i, R_j)$ = covariance between returns of assets $i$ and $j$  

👉 **Diversification effect:**  
If assets are not perfectly correlated, combining them reduces overall risk.  
This is the **key benefit of portfolio construction.**

---

## 📌 Risk-Return Tradeoff  

- Investors aim to **maximize return for a given level of risk**, or **minimize risk for a given return**.  
- The set of optimal portfolios is called the **Efficient Frontier**.  
- The actual portfolio choice depends on the **investor’s risk tolerance**.  

---

## 👉 In Short  

- **Return** = the reward for investing.  
- **Risk** = the uncertainty in achieving that return.  
- **Effective portfolio construction** balances both, using **diversification** to manage risk while targeting desired returns.  

---

# 📊 What Trade-off Does Markowitz MPT Formalize, and Why is Diversification Powerful?

---

## 1. The Trade-off in Markowitz’s Modern Portfolio Theory (MPT)  

Markowitz (1952) formalized the **risk–return trade-off**:  

- **Return:** Investors want to maximize expected returns.  
- **Risk:** Returns are uncertain, so investors must also minimize risk, typically measured as the **variance (or standard deviation)** of portfolio returns.  

👉 The key idea:  
Investors don’t just care about return in isolation; they care about the **combination of return and risk**.  

- For any given expected return, there exists an **efficient portfolio** with the lowest possible risk.  
- Conversely, for a given level of risk, there exists a portfolio with the **maximum achievable return**.  

This trade-off produces the **Efficient Frontier** — the set of portfolios that offer the best achievable balance between expected return and risk.  

---

## 2. Why Diversification is Powerful  

Diversification works because of **correlation**:  

- If you invest in **just one asset**, your risk is entirely tied to that asset.  
- If you combine **multiple assets**, the portfolio variance is not simply the average of individual variances — it also depends on how the assets’ returns move **together**.  

**Portfolio Variance Formula:**  

$$
\sigma_p^2 = \sum_i w_i^2 \sigma_i^2 + \sum_{i \neq j} w_i w_j \, \text{Cov}(R_i, R_j)
$$

Where:  
- $w_i$ = weight of asset $i$  
- $\sigma_i^2$ = variance of asset $i$  
- $\text{Cov}(R_i, R_j)$ = covariance between returns of assets $i$ and $j$  

👉 **Diversification Effect:**  
- If assets are **less than perfectly correlated** $\rho < 1$, the covariance term reduces overall portfolio variance.  
- In the extreme case, if assets are **perfectly negatively correlated**, risk can be reduced dramatically — even eliminated in theory.  

Thus, diversification reduces **idiosyncratic risk (asset-specific risk)** without sacrificing expected return.  
What remains is mainly **systematic risk**, which cannot be diversified away.  

---

## ✅ In Summary  

- **MPT formalizes** the risk–return trade-off:  
  - Maximum return for a given risk, or  
  - Minimum risk for a given return.  

- **Diversification is powerful** because:  
  - Imperfect correlations between assets reduce overall portfolio volatility.  
  - Investors can achieve **more attractive risk–return profiles** through smart diversification.  
