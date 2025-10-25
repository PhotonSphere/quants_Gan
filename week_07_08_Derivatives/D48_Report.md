## **Executive Summary**

The reporting period from **Day 42 to Day 47** of the Portfolio Management and Optimization modules focused on the integration of **option pricing theory**, **quantitative financial modeling**, and **risk management applications**. The week’s work advanced progressively from conceptual understanding to computational implementation, emphasizing the translation of theoretical finance into actionable portfolio strategies.

The activities covered four core areas:

1. **Foundational Theory:** Understanding the role of derivatives and the Option Greeks in quantifying and managing portfolio risk.

2. **Quantitative Modeling:** Implementing the **Black-Scholes-Merton (BSM)** and **Binomial (CRR)** models to estimate theoretical prices, compare with live market data, and identify mispricing opportunities.

3. **Market Analysis:** Developing a **Python-based market scanner** to analyze pricing deviations in **NIFTY** and **M\&M** options, generating systematic buy/sell insights.

4. **Applied Risk Management:** Conducting a **Delta-hedging simulation** to demonstrate real-time risk neutralization and volatility control in a self-financing framework.

The findings revealed that while **BSM and Binomial models remain indispensable benchmarks**, real-world deviations due to **volatility smiles**, **illiquidity**, and **stale quotes** necessitate more sophisticated stochastic extensions. Moreover, the **application of Greeks** provided a quantitative foundation for **dynamic hedging**, **volatility trading**, and **portfolio optimization**, significantly reducing exposure to directional market risks.

Overall, the week consolidated theoretical knowledge with data-driven analytics, highlighting how **quantitative tools enhance portfolio resilience, identify inefficiencies, and optimize risk-adjusted returns**.

## **Summary of Weekly Work**

### **Day 42: Missing Content**

The provided materials did not include specific outputs or documentation for Day 42\.

---

### **Day 43: Derivatives Foundations and the Importance of Greeks**

**File:** `D43_Derivatives_Foundations.ipynb`

Day 43 established the conceptual foundation for options and introduced the **Option Greeks**, key metrics used for sensitivity analysis and risk control.

**Key Highlights:**

* **Role of Options:** Options serve as powerful instruments for **risk management**, **income generation**, and **strategic portfolio construction**, extending investment flexibility beyond traditional equity holdings.

* **Flexibility and Leverage:** By offering high notional exposure for limited capital, options enable efficient capital deployment and sophisticated strategies like **spreads**, **collars**, and **covered positions**.

* **Portfolio Management Use Cases:**

  * **Protective Puts** act as downside insurance.

  * **Covered Calls** and **Cash-Secured Puts** enhance portfolio yields.

  * **Volatility Trading:** Options allow volatility to be treated as a tradable asset class (e.g., via **VIX options**).

* **Introduction to Greeks:**

  * **Delta (Δ):** Sensitivity to underlying price.

  * **Gamma (Γ):** Sensitivity of Delta; vital for dynamic hedging.

  * **Theta (Θ):** Measures time decay of option value.

  * **Vega (ν):** Sensitivity to volatility.

  * **Rho (ρ):** Sensitivity to interest rate changes.

* **Risk Management:** Aggregated Greeks across positions provide insight into total portfolio exposures, enabling **dynamic hedging** and compliance with **risk limits**.

---

### **Day 44: Black-Scholes Model (Closed Form) and Market Scanning**

**File:** `D44_Black_Scholes_Model_(Closed_Form)[ModelVSMarket].ipynb`

Day 44 focused on implementing the **Black-Scholes-Merton (BSM)** model for European options and applying it to live **NSE market data** for pricing validation and mispricing detection.

**Key Components:**

* **Model Overview:** The BSM model offers a closed-form pricing solution for European options, enabling efficient computation of theoretical prices and Greeks.

* **Limitations:** Assumes constant volatility and risk-free rate, excludes transaction costs, and applies only to European options.

* **Market Scanner:**

  * Collected live data (NIFTY and M\&M options).

  * Computed **At-The-Money (ATM)** implied volatility.

  * Generated **Buy/Sell/Hold** signals based on pricing deviations using a configurable **Decision Threshold (0.03)**.

**Key Findings:**

* **NIFTY:** Significant mispricing observed — **Puts undervalued (up to \-84%)**, likely due to illiquidity; **Calls mildly overvalued (+16.7%)**.

* **M\&M:** Smaller deviations; **OTM puts undervalued (10–23%)**, **calls slightly overvalued (3–4%)**.

---

### **Day 45: BSM vs. Binomial (CRR) Option Pricing Comparison**

**File:** `D45_Black_Scholes_Model_vs_Binomial_(CRR)_Option_Pricing.ipynb`

This day extended pricing analysis by comparing **Black-Scholes (BSM)** and **Binomial Tree (Cox–Ross–Rubinstein, CRR)** models.

**Highlights:**

* **Model Comparison:**

  * **BSM:** Continuous-time, closed-form analytical model.

  * **Binomial (CRR):** Discrete-time, numerical model suitable for **American options** (supports early exercise).

  * Binomial prices **converge to BSM** as the number of steps increases.

* **Pipeline Output:** Computed and compared:

  * BSM analytical price.

  * Binomial European price.

  * Binomial American price.

* **Findings:**

  * Reinforced **undervalued puts** and **overvalued calls** in NIFTY.

  * M\&M options also reflected mild put undervaluation.

* **Strategic Implications:** Suggested potential **downside exposure (Buy PUT / Sell CALL)** and anticipation of **volatility uptick**.

* **Modern Context:** While BSM and CRR remain foundational, real-world markets require **Stochastic Volatility** and **Jump-Diffusion** extensions to capture volatility smiles and fat tails.

---

### **Day 46: In-Depth Greek Analysis**

**File:** `D46_Option_Greeks.ipynb`

Day 46 deepened the understanding of Greeks through quantitative visualization of **Delta, Gamma, Vega, Theta, and Rho** across strike prices.

**Observations:**

* **Delta:** Increases (calls) or decreases (puts) monotonically with moneyness.

* **Gamma:** Peaks near ATM — critical for hedge adjustment sensitivity.

* **Vega:** Highest near ATM — indicates maximum sensitivity to volatility.

* **Theta:** Negative for long options, with steepest decay near ATM.

* **Rho:** Most significant for deep ITM calls and OTM puts.

**Applications:**

* Informs **hedging**, **volatility trading**, **time decay management**, and **portfolio optimization**.

* Enables structured, quantitative decision-making beyond directional speculation.

---

### **Day 47: Greeks in Practice (Delta Hedging Simulation)**

**File:** `D47_Greeks_in_Practice_(Delta_Hedging).ipynb`

The final day implemented a **Delta-Hedging Simulator** to demonstrate real-world application of Greeks for **risk neutralization** and **volatility management**.

**Methodology:**

* Simulated 2000 price paths under risk-neutral conditions.

* Applied daily rebalancing with a **self-financing constraint** (realistic capital allocation).

* Compared **unhedged vs. delta-hedged PnL** performance.

**Key Results:**

* **Variance Reduction:**

  * M\&M Call PnL volatility reduced by \~4.69x.

  * M\&M Put PnL volatility reduced by \~4.02x.

* **Directional Neutrality:** Mean terminal PnL ≈ 0 — confirms effective delta hedging.

* **Residual Risks:** Persist due to **Gamma**, **Vega**, and **Theta** effects, particularly from discrete rebalancing and assumed constant volatility.

* **Visualizations:** Included histograms (hedged vs. unhedged PnL), MTM volatility decay curves, and sensitivity plots over time.

---

## **Key Insights**

1. **Option Greeks are indispensable** for quantifying and managing multi-dimensional risk exposures in portfolios.

2. **Model-driven mispricing detection** can identify potential arbitrage or structural inefficiencies, though liquidity factors must be carefully considered.

3. **Dynamic hedging strategies**, especially Delta hedging, significantly stabilize returns by mitigating directional exposure.

4. **Black-Scholes and Binomial models**, while foundational, must be supplemented by modern stochastic and jump models to address real-world complexities.

5. **Visualization-driven analysis** enhances intuition about option sensitivity, aiding both traders and risk managers in decision-making.

---

## **Conclusion**

Days 42–47 marked a significant advancement in integrating **theoretical finance**, **quantitative modeling**, and **practical application**. The work bridged the gap between academic option theory and applied portfolio management.  
 Through modeling, market scanning, and dynamic hedging simulations, the week’s exercises highlighted how quantitative tools can **enhance portfolio resilience, identify inefficiencies**, and **control risk dynamically**.

This phase concludes with a strong foundation for further exploration into **stochastic volatility modeling**, **volatility surface analysis**, and **multi-asset hedging frameworks**.
