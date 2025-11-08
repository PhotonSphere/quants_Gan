#  **Quantifying, Modeling, and Validating Downside Financial Risk: A Multi-Method Approach**

---

## **Introduction**

Financial markets are inherently volatile, and the accurate quantification of downside risk is fundamental to sound risk management and regulatory compliance. Traditional metrics such as **standard deviation** capture overall volatility but fail to describe the magnitude and frequency of **extreme losses**, which often dictate real-world portfolio outcomes.

This study spans **Days 57 to 61** and focuses on the **quantification, modeling, and validation of downside risk** through three advanced frameworks:

* **Value at Risk (VaR)**

* **Conditional Value at Risk (CVaR)**

* **Extreme Value Theory (EVT)**

Additionally, regulatory developments such as the **Basel III Fundamental Review of the Trading Book (FRTB)** are integrated to understand the practical implications of modern risk measurement. The analysis uses **NIFTY 50**, **Bitcoin (BTC)**, and **S\&P 500 (SPX)** data to compare traditional and tail-sensitive methods under normal and crisis conditions.

---

## **Day 57: Establishing the Regulatory and Conceptual Foundation**

The initial phase focused on the conceptual and regulatory framework of risk measurement, explaining why volatility-based metrics are insufficient to assess downside risk.

### **Key Concepts Introduced**

* **Value at Risk (VaR):**  
   Estimates the maximum potential loss over a specific time horizon at a defined confidence level.  
   *Example:* A 99% VaR indicates a 1% chance of exceeding that loss in a given period.

* **Conditional Value at Risk (CVaR) / Expected Shortfall (ES):**  
   Measures the *average* loss beyond the VaR threshold, overcoming VaR’s main limitation—its insensitivity to tail severity.

* **Regulatory Evolution:**  
   Under **Basel III FRTB**, regulators shifted the core metric from **99% VaR** to **97.5% CVaR (Expected Shortfall)** because CVaR is a *coherent* measure (it satisfies sub-additivity).

* **Modeling Extreme Events (EVT):**  
   Introduced as a statistical method to estimate the probability of **rare, catastrophic losses**—so-called “black swan” events—beyond the observed sample.

---

## **Day 58: Value at Risk (VaR) Calculation and Comparison**

This phase involved empirical computation of VaR for two distinct assets — **NIFTY 50** and **Bitcoin (BTC)** — using three approaches.

### **Methods Applied**

1. **Historical VaR:** Based on empirical quantiles of historical return distributions.

2. **Parametric Normal VaR:** Assumes returns follow a Gaussian distribution.

3. **Parametric Student-t VaR:** Incorporates fat tails via Student-t distribution.

### **Findings: BTC vs NIFTY**

* **Tail Risk Disparity:** Bitcoin’s daily tail losses were **4–5× larger** than NIFTY’s.

* **Model Performance:**

  * *Normal VaR* significantly **underestimated** BTC’s losses due to heavy tails.

  * *Student-t VaR* provided a **more realistic fit**, particularly at 99% confidence (Degrees of Freedom ≈ 3), confirming BTC’s extreme tail heaviness.

---

## **Day 59: Conditional Value at Risk (CVaR) and Tail Severity Analysis**

Focus shifted to quantifying *how severe* losses are beyond the VaR threshold, addressing VaR’s blind spot.

### **Concepts and Metrics**

* **CVaR Definition:**  
   The *expected loss* given that returns fall below the VaR quantile — i.e., “How bad can it get once VaR is breached?”

* **Tail Severity Ratio (CVaR / VaR):**  
   Quantifies the “fatness” of the loss distribution tail. A higher ratio implies steeper escalation of losses beyond VaR.

### **Empirical Results**

| Asset | Tail Severity Ratio (CVaR / VaR) | Interpretation |
| ----- | ----- | ----- |
| NIFTY 50 | 1.44–1.47× | Moderately fat tails |
| Bitcoin | 1.57–1.65× | Extremely fat tails |

**Conclusion:** Both assets deviate from normality, but BTC’s tail risk is significantly more severe once losses exceed VaR.

---

## **Day 60: Extreme Value Theory (EVT) Modeling**

To better estimate *rare, unobserved* extremes, EVT was applied using the **Peaks Over Threshold (POT)** approach.

### **Methodology**

* Fitted a **Generalized Pareto Distribution (GPD)** to returns exceeding the 95th percentile (extreme losses).

* Derived **EVT-based VaR** estimates to extrapolate beyond observed data.

### **Results and Comparison**

| Asset | VaR Method | 99% VaR (%) | Interpretation |
| ----- | ----- | ----- | ----- |
| NIFTY 50 | Historical | ≈ Similar to EVT | Moderate tail risk |
| BTC | Normal | 7.866 | Underestimates risk |
| BTC | Historical | 8.588 | Improved but limited |
| BTC | EVT (GPD) | 9.198 | Most accurate for heavy tails |

**Key Insight:**  
 EVT provided the **highest and most reliable VaR estimates** for BTC, validating that standard Gaussian models are unsuitable for assets with heavy-tailed return distributions such as cryptocurrencies.

---

## **Day 61: Backtesting and Stress Testing**

The final stage validated model accuracy and robustness under both normal and crisis market regimes, using **NIFTY 50** and **S\&P 500 (SPX)**.

### **Model Validation**

* **Test Applied:** Kupiec *Proportion of Failures (POF)* Test.

* **Result:** Historical VaR model performed well:

  * Observed breach rates ≈ Expected (NIFTY: 5.0%; SPX: 1.0%).

  * Indicates excellent calibration under long-term, stable conditions.

### **Stress Testing**

* **Crisis Periods Examined:**

  * 2008 Global Financial Crisis (GFC)

  * 2020 COVID Crash

* **Findings:**

  * 95% VaR was breached **≈30–31%** of days during crises (vs expected 5%).

  * Demonstrates VaR’s failure in non-stationary and turbulent markets.

### **Conclusion**

Historical VaR models are **reliable in stable regimes** but **collapse under structural breaks**, underscoring the need for adaptive, stress-aware frameworks (e.g., CVaR or EVT-based methods).

---

## **Executive Summary and Key Insights**

### **Executive Summary**

This multi-day study systematically quantified and validated downside financial risk using **VaR**, **CVaR**, and **EVT**, applied across **traditional (NIFTY, SPX)** and **high-volatility (BTC)** assets. It highlighted how traditional risk measures underestimate tail risk and how advanced models improve accuracy, especially in crisis conditions.

### **Key Insights**

1. **VaR Limitations:**  
    While useful for baseline risk assessment, VaR fails to capture the *magnitude* of tail losses and collapses during crises.

2. **CVaR Superiority:**  
    CVaR provides a *more coherent and tail-sensitive* measure, aligning with Basel III’s shift to Expected Shortfall as the regulatory standard.

3. **EVT Accuracy:**  
    EVT’s GPD framework effectively captures *rare, catastrophic losses* that standard models miss—particularly relevant for assets like Bitcoin.

4. **Market Regime Dependence:**  
    Models calibrated in normal markets perform poorly during structural breaks; **dynamic recalibration** or **stress testing** is essential.

5. **Practical Implication:**  
    Combining **CVaR and EVT** provides a comprehensive view of tail risk—ideal for portfolio stress testing, risk capital estimation, and strategic allocation.

