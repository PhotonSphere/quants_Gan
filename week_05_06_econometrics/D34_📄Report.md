# **Quantitative Finance Progression Report**

### ***Days D29–D33: From Stylized Facts to Validated Risk Forecasting***

---

## **1\. Overview**

This report summarizes activities across **Days D29 through D33**, outlines their analytical connection, provides a detailed interpretation of results, and concludes with key insights.

The five-day sequence represents a coherent **analytical pipeline in quantitative finance** — from identifying empirical market anomalies to building, applying, and validating dynamic risk models.

---

## **2\. Summary of Each Day (D29–D33)**

| Day | Focus | Purpose | Key Insight / Finding |
| ----- | ----- | ----- | ----- |
| **D29** | Stylized Facts of Returns | Examine statistical patterns (heavy tails, clustering, skewness) to understand true market risk beyond averages. | Financial returns violate Normality assumptions, exhibiting heavy tails and skewness — necessitating non-Gaussian models. |
| **D30** | Introduction to ARCH/GARCH | Model and forecast time-varying volatility reflecting clustering and persistence. | GARCH(1,1) outperforms ARCH(1). For NIFTY 50, volatility persistence (α₁ \+ β₁ ≈ 0.97) is key; Student’s t errors improve fit. |
| **D31** | Advanced GARCH (EGARCH) | Capture asymmetry (leverage effects) where negative shocks raise volatility more than positive ones. | EGARCH(1,1)-t provides best fit for NIFTY 50, balancing persistence (β₁ ≈ 0.97) and tail realism (ν ≈ 6.3). |
| **D32** | Forecasting Volatility | Translate EGARCH-t results into volatility forecasts and risk intervals. | 30-day EGARCH-t forecasts imply stable volatility but realistic asymmetric, fat-tailed risk (e.g., VaR₉₅% \= −1.465%). |
| **D33** | VaR Backtesting | Validate forecast accuracy using Kupiec and Christoffersen tests. | At 99% VaR, EGARCH(1,1)-t is the only model passing all statistical backtests, confirming its reliability. |

---

## **3\. Analytical Connection Across the Five Days**

The days form a **structured methodological sequence**, connecting theory, modeling, and validation:

**• D29 – Establishing the Problem:**  
 Confirms that **financial markets are non-Gaussian** with volatility clustering. Classical constant-volatility models are insufficient.

**• D30–D31 – Building the Solution:**  
 **ARCH/GARCH** capture volatility persistence; **EGARCH** adds asymmetry. Empirically, **EGARCH(1,1)-t** emerges as the optimal specification (lowest AIC/BIC).

**• D32 – Applying Forecasts:**  
 The **EGARCH-t model** projects forward volatility and VaR, making risk **forecastable** rather than static.

**• D33 – Validating the Model:**  
 **Backtesting** confirms EGARCH-t’s predictive validity — a necessary step for practical institutional risk management.

---

## **4\. Detailed Report**

### **I. D29 — Necessity of Non-Normal Modeling**

Financial return distributions exhibit **heavy tails, volatility clustering, and skewness**, defying Normal assumptions. Key findings from 2015–2025 data confirm that risk cannot be accurately modeled using constant-variance Gaussian methods.

* **Heavy Tails (High Kurtosis):** NIFTY 50 (8.6), NIFTYBANK (17.3), TITAN (28.4); Student’s t ν between 2.5–3.6.

* **Negative Skew:** Market indices show downside bias; select equities (INFY, RELIANCE) show mild positive skew.

* **Indices vs. Equities:** Indices offer diversification but remain crash-prone; select equities show better convexity.

**Implication:**  
 Stylized facts demonstrate the need for **non-normal, dynamic volatility models** to accurately measure and manage risk.

---

### **II. D30–D31 — Dynamic Volatility Modeling(Nifty 50 10Yrs data)**

**A. D30: GARCH vs. ARCH Fit**

* **GARCH(1,1)** provides a stronger fit (LLF Δ \+91.68) than ARCH(1).

* Persistence (α₁ \+ β₁ ≈ 0.97) shows long memory in volatility.

* Fat tails modeled effectively with Student’s t (ν ≈ 6.4).

**B. D31: Introducing EGARCH**

* **EGARCH(1,1)-t** achieves lowest AIC/BIC (6697.87 / 6727.28).

* Captures **leverage effects**: volatility reacts more to negative shocks.

* **Model parameters:** Persistence β₁ ≈ 0.9742; Tail thickness ν ≈ 6.332.

**Outcome:**  
 Transition from static to adaptive volatility modeling completed — a robust foundation for forecasting and risk control.

---

### **III. D32 — Volatility Forecasting and Risk Metrics**

Applying **EGARCH(1,1)-t** for 30-day forecasts:

| Metric | Result | Interpretation |
| ----- | ----- | ----- |
| Mean daily σ | 0.7332% (≈11.6% annualized) | Stable short-term volatility regime |
| 95% return range | ±1.47% | Daily fluctuations typically within this bound |
| VaR₉₅% | −1.4653% | Expected daily loss exceeded once every \~20 days |

**Strategic Implication:**  
 Forecasts enable **proactive risk management** — adjusting leverage or hedging based on anticipated volatility regimes.

---

### **IV. D33 — VaR Backtesting and Model Validation**

Backtesting compared **Historical, GARCH-norm, GARCH-t, and EGARCH-t** models using **Kupiec (POF)**, **Christoffersen Independence**, and **Conditional Coverage** tests at **99% confidence**.

| Model | Failure Rate (Expected 1%) | Kupiec | Independence | Conditional Coverage |
| ----- | ----- | ----- | ----- | ----- |
| Historical | 1.46% | REJECT | REJECT | REJECT |
| GARCH-norm | 1.96% | REJECT | PASS | REJECT |
| GARCH-t | 0.04% | REJECT | PASS | REJECT |
| **EGARCH-t** | **1.40%** | **PASS** | **PASS** | **PASS** |

**Conclusion:**  
 Only **EGARCH(1,1)-t** passes all three tests at 99% confidence — proving its superior dynamic calibration and tail accuracy.

---

## **5\. Key Insights and Strategic Implications**

1. **Normality Assumption Fails:**  
    Real markets exhibit fat tails and asymmetry. Normal-based models underestimate extreme risks.

2. **EGARCH(1,1)-t is Empirically Superior:**

   * Heavy tails: ν ≈ 6.3

   * Persistence: α₁ \+ β₁ ≈ 0.97

   * Asymmetry: Leverage effect properly modeled

3. **Forecastable Volatility \= Strategic Advantage:**  
    Treating volatility as a **dynamic, forecastable variable** allows portfolio managers to:

   * Anticipate regime shifts

   * Adjust exposure proactively

   * Enhance tail-risk resilience

---

### **Final Note**

The Day 29–Day 33 analytical progression transforms volatility from a static measure of uncertainty into a **predictive and actionable dimension of strategic risk management**, enabling informed, adaptive, and resilient investment decision-making.

