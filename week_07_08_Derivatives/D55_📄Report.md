### **Executive Summary**

This week’s portfolio optimization initiative focused on advancing the analytical framework for **option pricing and market modeling** beyond the traditional **Black–Scholes–Merton (BSM)** paradigm.  
 The objective was to enhance pricing accuracy and market realism by integrating **stochastic volatility**, **jump-diffusion**, and **numerical PDE** techniques into the modeling architecture.

Key highlights from Days 50 to 54 include:

* **Model Evolution:** Transition from the constant-volatility BSM model to **Heston Stochastic Volatility** and **Merton Jump Diffusion** frameworks to address volatility smiles, fat tails, and jump risks.

* **Numerical Validation:** Implementation and convergence testing using **Monte Carlo (MC)** and **Finite Difference (FD)** methods to ensure model robustness and computational accuracy.

* **Instability Diagnostics:** Identification of numerical divergence in the FD scheme and development of refinements in grid design, boundary conditions, and time-stepping stability.

* **Risk Premium Insights:** Quantification of **jump risk premiums** and their impact on call and put prices, highlighting the real-world deviations from theoretical baselines.

* **Integrated Framework:** Development of a unified pricing comparison across **BSM, FD, MC GBM, Heston, and Jump Diffusion** methods, providing a benchmark for model behavior under various volatility and market regimes.

The week’s work establishes a strong foundation for **multi-model calibration**, **scenario testing**, and **risk-adjusted performance assessment**, paving the way for more resilient and adaptive portfolio strategies in subsequent phases.

#  **Weekly Portfolio Management and Optimization Report (Days 50–54)**

### **Overview**

This report summarizes the portfolio management and optimization activities conducted over **Days 50 to 54**.  
 The week’s focus was to move beyond the classical **Black–Scholes–Merton (BSM)** framework by implementing **advanced stochastic and numerical models** for more realistic option pricing and market analysis.

---

## **Day 50: Limitations of BSM and the Necessity of Stochastic Volatility (SV) Models**

Day 50 established the **Black–Scholes–Merton (BSM)** model as the foundational analytical model for option pricing.  
 Its primary assumption of constant volatility (σ) was critically examined, revealing several practical shortcomings:

* **Volatility Smile/Skew:** Market-implied volatility varies with strike price and maturity, forming the volatility smile or skew.

* **Return Distribution:** BSM assumes lognormal returns, while real markets exhibit leptokurtic (fat-tailed) distributions.

* **Dynamic Effects:** The model ignores volatility clustering and the leverage effect, where volatility rises as prices fall.

* **Jumps:** BSM assumes continuous paths and cannot capture sudden jumps or shocks in market prices.

These limitations motivated the transition to **Stochastic Volatility (SV)** models, where volatility itself is modeled as a **dynamic, random, and mean-reverting process** correlated with the asset.  
 The **Heston model (1993)** was emphasized as a canonical framework capable of capturing volatility clustering and realistic smile behavior while retaining analytical tractability.

---

## **Day 51: Heston Stochastic Volatility Model and Numerical Convergence**

Day 51 focused on the **implementation and validation** of the Heston model through **Monte Carlo (MC)** simulations.  
 The model defines asset prices and their variances using **Stochastic Differential Equations (SDEs)**. Key parameters include:

* Mean reversion speed (κ)

* Long-term variance (θ)

* Volatility of volatility (ξ)

* Correlation (ρ), typically negative to capture the leverage effect

Simulation results for the **M\&M ticker** confirmed **numerical convergence**: as grid resolution increased (M=N=100, 200, 400, 800), **Heston MC prices approached analytical BSM prices**.  
 This validated both the **accuracy and stability** of the numerical implementation and showed that the Heston model allows greater flexibility in capturing market-implied volatility structures.

---

## **Day 52: Finite Difference (PDE Pricing) and Instability Analysis**

Day 52 implemented the **Finite Difference (FD)** method using the **Crank–Nicolson scheme** with **Rannacher smoothing** to numerically solve the Black–Scholes PDE.  
 This approach is essential for pricing options with complex features such as **American-style exercise** or **variable volatility regimes**, where no closed-form solution exists.

Testing against BSM benchmarks for the **M\&M ticker** revealed **numerical instability**.  
 Errors **increased with grid refinement** — the mean absolute error for calls rose from **8.435 at M100 to 97.459 at M800**, producing **negative convergence orders** (e.g., \-1.1559 for calls).  
 This highlighted issues with **boundary conditions**, **domain truncation (Smax)**, and **time-stepping ratios**, necessitating further refinement of the FD numerical engine.

---

## **Day 53: Jump Diffusion Models and Jump Risk Premium**

Day 53 introduced the **Merton Jump Diffusion (MJD)** model, which augments standard diffusion dynamics with a **Poisson jump process** to model discontinuous price movements and fat-tailed return distributions.

Model calibration was performed by minimizing the **Mean Squared Error (MSE)** between model prices and observed market data.  
 Results for the **M\&M ticker** showed that **MJD prices exceeded BSM values**, with the largest difference of **\+2.16 for the 3700 call**, reflecting the **jump risk premium**.

Sensitivity analyses demonstrated how option prices respond to changes in:

* Jump frequency (λ)

* Mean jump size (μₙ)

* Jump volatility (σₙ)

These analyses confirmed the MJD model’s ability to capture **event-driven risks** and **tail behaviors** observed in real markets.

---

## **Day 54: Unified Stochastic Models Framework and Comparative Analysis**

Day 54 consolidated the week’s work into a **comparative analytical framework** encompassing five pricing approaches:  
 **BSM, Finite Difference (FD), Monte Carlo GBM, Monte Carlo Heston, and Monte Carlo Jump Diffusion.**

### **Comparative Findings:**

* **Finite Difference (FD):** Stable FD implementations align closely with BSM (typically \<0.3% deviation).

* **Monte Carlo GBM:** Slightly lower prices than BSM due to path sampling variance.

* **Monte Carlo Heston:** Produces lower values reflecting stochastic volatility and mean reversion.

* **Monte Carlo Jump Diffusion:** Generates higher call prices (+14.44 for the 3600 call) and marginally lower put prices, capturing tail risk premiums.

---

### 

### **Conclusion**

Each model serves a distinct analytical purpose:

* **BSM and FD** are ideal for **benchmarking and accuracy validation**.

* **Heston and Jump Diffusion** models are well-suited for **stress testing and scenario analysis**.

Collectively, these models provide a **multi-layered understanding of market efficiency**, volatility structures, and the complex dynamics underlying option pricing.

