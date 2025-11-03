# 📘 Risk Measures and Regulatory Evolution

## 1. Introduction: Understanding Risk Measures

In financial risk management, **risk measures** are quantitative tools that assess the potential loss an investment portfolio might face due to adverse market movements.  
They are essential for setting capital requirements, managing exposures, and ensuring regulatory compliance.

A **good risk measure** should capture not only the expected loss but also the uncertainty and the tail behavior of loss distributions.  
Traditional measures like standard deviation or beta capture **volatility**, but they fail to describe **extreme losses** — the kind of events that cause financial crises.  

To address this limitation, modern risk management relies on **tail risk measures**, the most prominent of which are:

- **Value at Risk (VaR)**  
- **Conditional Value at Risk (CVaR)**  
- **Extreme Value Theory (EVT)**

---

## 2. Value at Risk (VaR)

### Definition

**Value at Risk (VaR)** estimates the maximum potential loss a portfolio could face over a specified time horizon at a given confidence level.

Formally, for a confidence level: 

$$ \alpha $$

$$
P(L > \text{VaR}_{\alpha}) = 1 - \alpha
$$

where  **L** is the portfolio loss.

### Interpretation

A 99% daily VaR of \$1 million means there is a 1% chance that the portfolio will lose **more than \$1 million** in a single day.

### Methods of Calculation

1. **Parametric (Variance–Covariance):** assumes normal distribution of returns.  
2. **Historical Simulation:** uses empirical historical data.  
3. **Monte Carlo Simulation:** simulates future scenarios via statistical modeling.

### Strengths

- Intuitive and widely used by banks and regulators (e.g., Basel framework).  
- Provides a clear threshold for potential losses.

### Weaknesses

- Does **not capture the severity of losses beyond VaR**.  
- Not always **sub-additive**, meaning diversification benefits might be misrepresented.  
- Sensitive to assumptions about distribution and correlations.

---

## 3. Conditional Value at Risk (CVaR)

### Definition

**Conditional Value at Risk (CVaR)** — also called **Expected Shortfall (ES)** — measures the **average loss beyond the VaR threshold**.

Formally:

$$
\text{CVaR}_{\alpha} = E[L \mid L > \text{VaR}_{\alpha}]
$$

### Interpretation

While VaR answers *“What is the most I can lose?”*,  
CVaR answers *“If I do lose more than that, how bad can it get on average?”*

### Advantages

- **Coherent risk measure**: satisfies sub-additivity, monotonicity, homogeneity, and translation invariance.  
- Provides insight into **tail risk** (the magnitude of extreme losses).  
- Preferred in regulatory frameworks like **Basel III (FRTB)**.

### Limitations

- Harder to compute for complex portfolios.  
- Sensitive to tail sample size and estimation errors.

---

## 4. Extreme Value Theory (EVT)

### Definition

**Extreme Value Theory (EVT)** focuses on **statistical modeling of the tails** of loss distributions, rather than the entire distribution.  
It estimates the probability of **rare, extreme losses** that go beyond observed historical data.

### Two Common EVT Approaches

1. **Block Maxima (BM):** divides data into blocks (e.g., months) and models their maxima using the **Generalized Extreme Value (GEV)** distribution.  
2. **Peaks Over Threshold (POT):** models all values exceeding a chosen threshold using the **Generalized Pareto Distribution (GPD)**.

---

## 5. Why Regulators Focused on VaR

### Historical Context

The **Basel Committee on Banking Supervision (BCBS)** adopted VaR in the 1996 **Market Risk Amendment**, providing a standardized approach for market risk capital.  
It offered **comparability**, **simplicity**, and **empirical verifiability** through back-testing.

### Reasons for Regulatory Preference

- **Simplicity:** A single, intuitive number easily communicated.  
- **Standardization:** Common basis for capital comparison across banks.  
- **Flexibility:** Can be estimated with parametric, historical, or simulated methods.  
- **Back-testing feasibility:** Actual outcomes can be compared with VaR predictions.  
- **Computational practicality:** Easy to calculate daily across large portfolios.

---

## 6. Why VaR Alone Is No Longer Sufficient

Although VaR transformed market risk regulation, the **2008 Global Financial Crisis** revealed its limitations.

### (a) Lack of Tail Sensitivity

VaR captures only the cutoff point of loss distribution and ignores losses beyond it — the **severity** of tail events.  
During crises, this blind spot can understate systemic risk.

### (b) Non-Coherency and Diversification Issues

VaR is not always a **coherent risk measure**, as it can violate **sub-additivity**:

$$
\text{VaR}(A + B) > \text{VaR}(A) + \text{VaR}(B)
$$

This means combining two portfolios may appear riskier than holding them separately, contradicting diversification principles.

### (c) Model Instability

VaR is sensitive to distributional assumptions and can provide **false security** during low-volatility periods.

---

## 7. Basel III / FRTB Transition to Expected Shortfall (CVaR)

The **Fundamental Review of the Trading Book (FRTB)**, finalized in 2016, replaced VaR with **Expected Shortfall (ES)** as the primary regulatory metric.

### Key Changes

- Move from **99% VaR** to **97.5% Expected Shortfall**.  
- Inclusion of **liquidity horizons** for different instruments.  
- Stronger emphasis on **back-testing** and **profit & loss attribution**.  
- Capital based on **average tail losses**, not just the threshold.

### Impact

Expected Shortfall provides a **more stable, coherent, and tail-sensitive** assessment of risk, aligning regulatory capital with true downside exposure.

---

## 8. Incorporating EVT, Back-Testing, and Stress Testing

### (a) Extreme Value Theory (EVT)

EVT improves estimation of rare, catastrophic losses that lie beyond historical data.  
It helps regulators and banks simulate **black swan** events and design **stress scenarios**.

### (b) Back-Testing

Used to validate the accuracy of VaR and ES estimates by comparing predicted losses with realized outcomes.  
Exceedances trigger model reviews or capital adjustments.

### (c) Stress Testing

Assesses portfolio resilience under **severe but plausible** macroeconomic or market scenarios.  
Used by central banks and supervisory agencies to identify systemic vulnerabilities.

### Integrated Framework

| Measure | Purpose | Regulatory Role |
|----------|----------|----------------|
| **VaR** | Threshold loss | Daily risk monitoring |
| **CVaR (ES)** | Average tail loss | Capital calculation (Basel III FRTB) |
| **EVT** | Extreme loss modeling | Scenario generation |
| **Back-Testing** | Model validation | Supervisory control |
| **Stress Testing** | Systemic resilience | Macroprudential oversight |

---

## 9. Executive Summary

- **VaR** offered a breakthrough in risk quantification and remains central to reporting and model validation.  
- However, its **lack of tail awareness** and potential incoherency limit its effectiveness during crises.  
- **Basel III FRTB** introduced **Expected Shortfall (CVaR)** to provide a fuller picture of tail losses.  
- **Extreme Value Theory (EVT)** enhances the statistical modeling of rare events, supporting **stress testing** and **capital adequacy**.  
- Combined with **back-testing** and **stress testing**, these approaches form a **multi-layered regulatory framework** that balances simplicity, accuracy, and robustness.

**In essence:**  
The global regulatory paradigm has evolved from focusing on *probable losses (VaR)* to understanding and mitigating *extreme, systemic risks (CVaR, EVT, and stress tests)* — ensuring financial stability in an increasingly uncertain world.
