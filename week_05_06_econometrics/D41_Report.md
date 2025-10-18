## **Quantitative Pairs Trading Development Report (Day 36 – Day 40\)**

---

**Executive Summary**

This report documents **Days 36 through 40** of the *Quantitative Pairs Trading Development Project*, focusing on the statistical foundation, model enhancement, and practical implementation of a cointegration-based trading strategy.

The objective of this development phase was to progress from theoretical understanding to the construction of a **fully adaptive and risk-managed trading framework**. Over five consecutive days, the work evolved from foundational econometric testing (Engle–Granger and Johansen methodologies) to sophisticated model refinements involving **Vector Error Correction Models (VECM)**, **dynamic hedge ratio estimation**, and **realistic trade simulations** that account for market frictions.

Each stage systematically addressed a critical layer of the trading architecture:

* **Day 36–37:** Establishing robust statistical relationships and validating cointegration.

* **Day 38–39:** Implementing, testing, and refining the trading logic through rolling backtests and performance tracking.

* **Day 40:** Integrating advanced multivariate modeling and dynamic hedging to align with real-world trading dynamics.

Collectively, these developments represent a significant step toward a **scalable, data-driven pairs trading system** capable of adapting to changing market conditions while maintaining disciplined risk management and performance transparency.

---

### **Day 36: Cointegration Foundations via Engle–Granger**

Day 36 established the foundational statistical requirement for pairs trading: identifying a long-term equilibrium relationship between two non-stationary price series.

#### **Methodology: Engle–Granger (EG) Two-Step Cointegration Test**

1. **Step 1: OLS Regression**  

    yt​=α+βxt​+ϵt​ 
    
    was performed to determine the linear relationship.

   * The coefficient **β** serves as the hedge ratio.

   * The residual **ϵₜ** defines the “spread.”

2. **Step 2: Stationarity Test**  
    The residuals (**ϵₜ**) were tested for stationarity using the **Augmented Dickey–Fuller (ADF)** test.

   * If residuals are stationary (I(0)), the assets are considered **cointegrated**, meaning the spread reverts to a stable mean.

#### **Key Findings and Trading Relevance**

* Successful identification of cointegrated pairs:

  * **ICICIBANK.NS – HDFCBANK.NS**

  * **HDFCBANK.NS – ^NSEI**

  * **HDFCBANK.NS – GLD**

* Indicates suitability for **mean-reversion strategies**.

* Highlighted the importance of calculating the **half-life of mean reversion** — a critical metric for position sizing and optimal holding periods.

---

### **Day 37: Advanced Cointegration Testing via Johansen Multivariate Framework**

The limitations of the bivariate EG approach were addressed by implementing the **Johansen cointegration framework**.

#### **Methodology and Advantages**

1. **Lag Selection**

   * Automated optimal lag selection using **AIC/BIC** criteria on differenced price data.

   * Ensures appropriate model complexity.

2. **Multivariate Testing**

   * Uses **trace** and **maximum eigenvalue (max-eig)** statistics to determine the **cointegration rank (r)** — i.e., the number of cointegrating relationships.

3. **Output**

   * Extracts the **normalized cointegrating vector (β)**, defining the stationary spread’s linear combination.

#### **Actionable Insights**

* Strong consensus pairs: **GLD–HDFCBANK.NS**, **GLD–RELIANCE.NS**.

* “Mixed evidence” pairs (where tests conflicted) were flagged for **visual inspection** and **robustness checks**.

---

### **Day 38: Classic Pairs Trading Framework Implementation**

Building upon confirmed cointegration relationships, Day 38 implemented a **basic systematic trading logic**.

#### **Implementation Steps**

1. **Spread Construction**  

    St​=StockA−β⋅StockB
    
2. **Normalization**

   * The spread was standardized into a **Z-score**, enabling consistent entry/exit thresholds.

3. **Trading Rules**

   * **Entry:**

     * Go **Short** the spread when *z \> 2*

     * Go **Long** the spread when *z \< \-2*

   * **Exit:**

     * Close the position when *z → 0* (mean reversion).

#### **Framework Limitations**

* Static hedge ratio (**β**) estimated over entire history.

* Arbitrary **±2σ** thresholds.

* No inclusion of **transaction costs** or **slippage**.

---

### **Day 39: Rolling Backtest and Trade Tracking Enhancement**

To improve robustness, Day 39 introduced **adaptive methodologies** and **realistic trade management**.

#### **1\. Rolling Backtest**

* The hedge ratio (**β**), spread mean, and standard deviation were recalculated using a **rolling window** (e.g., 252 days).

* Ensures adaptability to time-varying cointegration.

#### **2\. Enhanced Trade Management**

* **Risk Limits:**

  * *max\_holding\_days*, *target\_pnl*, and *stop\_loss* to manage open positions.

* **Exit Reason Logging:**

  * Trades categorized by exit type:

    * **Z-Exit**, **Hit Target**, **Stop Loss**, **Time Limit**.

#### **3\. Performance Metrics**

* Outputs included:

  * **Cumulative PnL**

  * **Drawdown analysis**

  * **Hit ratio**

---

### **Day 40: VAR/VECM Modeling and Dynamic Hedging**

Day 40 integrated advanced **time-series modeling** and **realistic simulation features** to deepen analytical precision.

#### **1\. VECM/VAR Modeling**

* The analytical function (**cointF()**) employed:

  * **VECM** if cointegration detected (*r ≥ 1*).

  * **VAR** (on differenced data) otherwise.

* Captures long-run equilibrium corrections and enables **joint asset forecasting**.

#### **2\. Dynamic Beta Implementation**

* **Rolling OLS:** Moving-window β estimation.

* **Kalman Filter:**

  * Recursive, time-varying β updates.

  * Ideal for intraday or regime-shifting markets.

#### **3\. Real-World Frictions**

* **Transaction Costs:** Fixed *cost\_per\_trade*.

* **Slippage:** Percentage-based *slippage\_pct*, proportional to spread magnitude.

* **Net PnL:** Computed after all frictions.

#### **4\. Drawdown Enforcement**

* A **Drawdown Enforcement Threshold** (percentage of historical max drawdown) was introduced.

* Forces all positions flat and halts trading if breached, ensuring **capital preservation**.

## **Conclusion**

The five-day development cycle from **Day 36 to Day 40** marked a decisive evolution in the quantitative pairs trading framework — transforming it from a theoretical construct into a robust, data-driven trading system.

The journey began with the establishment of **cointegration foundations** through the Engle–Granger methodology, ensuring that selected asset pairs shared stable long-term relationships suitable for mean reversion strategies. Building upon this, the **Johansen framework** expanded analytical depth by incorporating multivariate testing, enabling the identification of multiple cointegrating vectors and improving statistical reliability.

The project then transitioned from theory to practice with the **implementation of a systematic trading framework**, featuring Z-score normalization and rule-based entries and exits. Through the introduction of **rolling backtests** and **enhanced trade management**, the system evolved into a dynamic model capable of adapting to time-varying market structures while maintaining clear risk and performance tracking.

Finally, the integration of **VECM/VAR modeling** and **dynamic hedge ratio estimation** (via rolling OLS and Kalman filtering) positioned the model closer to real-world trading conditions. Incorporation of transaction costs, slippage, and drawdown enforcement further possibly strengthen its realism and capital protection mechanisms.

Overall, this development phase successfully established a **scalable, statistically grounded, and risk-aware framework** for pairs trading. The next phase will focus on **multi-pair portfolio optimization, live market calibration, and execution efficiency**, with the goal of transitioning from research to fully automated deployment.

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>
