# 💼 Corporate Finance: DCF & Cost of Capital

Corporate finance is a branch of finance that focuses on how companies manage **funding sources, capital structure, investment decisions, and allocation of financial resources** to maximize shareholder value.  

Two cornerstone concepts are:  
1. **Discounted Cash Flow (DCF) analysis**  
2. **Cost of Capital (WACC)**  

---

## 📉 Discounted Cash Flow (DCF)

DCF is a **valuation method** that estimates the value of an investment or company by projecting **future cash flows** and discounting them to the present value using a discount rate.  

**Core Principle:** *Time value of money* — money today is worth more than the same amount in the future.  

### 🔢 Formula

$$
DCF = \frac{CF_1}{(1+r)^1} + \frac{CF_2}{(1+r)^2} + \cdots + \frac{CF_n}{(1+r)^n} + \frac{TV}{(1+r)^n}
$$

Where:  
- $CF_t$ = Free Cash Flow (FCF) in year *t*  
- $r$ = Discount rate  
- $n$ = Projection period (years)  
- $TV$ = Terminal Value (beyond projection period)  

---

### 📝 Steps to Perform DCF

1. **Forecast Free Cash Flows (FCF):**  
   - Typically projected for **5–10 years**.  
   - FCF = Cash generated after covering operations & capital expenditures.  

2. **Estimate Terminal Value (TV):**  
   - Often represents a large share of total valuation.  
   - Methods:  
     - **Perpetuity Growth Model:** Cash flows grow at constant rate forever.  
     - **Exit Multiple Method:** Apply EBITDA/earnings multiple at end of forecast.  

3. **Determine the Discount Rate:**  
   - Most common: **Weighted Average Cost of Capital (WACC)**.  

4. **Discount the Cash Flows:**  
   - Sum of present values of projected FCFs + terminal value = **Intrinsic Value**.  

---

## 💵 Cost of Capital

The **cost of capital** is the return investors expect for providing funds (equity + debt).  
It reflects the **minimum required return** a company must earn to satisfy providers of capital.  

The most widely used measure: **Weighted Average Cost of Capital (WACC).**

---

### 📊 Calculating the Components

#### 1. Cost of Equity (\( R_e \))  
Calculated using **Capital Asset Pricing Model (CAPM):**

$$
R_e = R_f + \beta (R_m - R_f)
$$

Where:  
- $R_e$ = Cost of equity  
- $R_f$ = Risk-free rate  
- $\beta$ = Beta (stock volatility relative to the market)  
- $R_m - R_f$ = Equity risk premium  

---

#### 2. Cost of Debt (\( R_d \))  
- Based on **interest rates** paid on debt.  
- Estimated using **yield to maturity** on bonds or average interest expense.  
- Since interest is tax-deductible, **after-tax cost of debt** is used in WACC.  

---

#### 3. Weights (\( E/V \) and \( D/V \))  
- Determined by **market values** (not book values).  
- Market value of equity = **market capitalization**.  
- Market value of debt = estimated from bond prices.  

---

✅ Together, **DCF and WACC** form the foundation of **corporate valuation**, guiding capital budgeting, M&A decisions, and financial strategy.  

## 📊 Advanced DCF Analysis

An advanced DCF analysis addresses key challenges that are often oversimplified in basic models.

### 🔹 FCFF vs. FCFE
- **Free Cash Flow to Firm (FCFF):**  
  Represents the cash flow available to **all capital providers** (both debt and equity holders) after paying all operating expenses and capital expenditures.  
  - Used for **Enterprise Value (EV)**.  
  - Discounted using **WACC**.

- **Free Cash Flow to Equity (FCFE):**  
  Represents the cash flow available only to **equity holders** after all debt payments have been made.  
  - Used for **Equity Value**.  
  - Discounted using **Cost of Equity ($R_e$)**.

- **The Choice:**  
  - For a company with a **stable capital structure**, both methods should yield the same result.  
  - For a company with a **changing debt-to-equity ratio**, the **FCFF approach** is more practical.  

---

### 🔹 Terminal Value (TV)
The **TV** often represents **70–80%** of the total DCF valuation, making it the most sensitive input.

- **Perpetuity Growth Method:**  
  Assumes a company’s cash flows will grow at a constant rate forever.  
  - Growth rate must be ≤ **long-term nominal GDP growth** of the country.  

- **Exit Multiple Method:**  
  Values the company at the end of the forecast period based on a **multiple of EBITDA or EBIT**, derived from comparable companies.  
  - Used as a **cross-check** to ensure the perpetuity method aligns with market valuations.  

---

### 🔹 Sensitivity & Scenario Analysis
- DCF valuations are **highly sensitive** to both the **discount rate** and the **growth rate**.  
- Advanced analysts don’t present a **single-point estimate**. Instead, they:  
  - Build **data tables** to show valuation ranges across different **WACC** and **terminal growth rate** assumptions.  
  - Provide a **valuation range**, which is more **realistic and robust**.  

## 🔹 WACC Calculation with Example Weights

### 1️⃣ Cost of Equity (CAPM)

$$
R_e = R_f + \beta (R_m - R_f)
$$

Where:  
- $R_f$ = Risk-free rate  
- $\beta$ = Beta (stock volatility relative to the market)  
- $(R_m - R_f)$ = Market risk premium  

---

### 2️⃣ Cost of Debt (After-Tax)

$$
R_d (1 - T_c)
$$

Where:  
- $R_d$ = Pre-tax cost of debt  
- $T_c$ = Corporate tax rate  

---

### 3️⃣ Weighted Average Cost of Capital (WACC)

$$
WACC = \frac{E}{V} \times R_e + \frac{D}{V} \times R_d \times (1 - T_c)
$$

#### Hypothetical Example:

- Equity weight ($E/V$) = 0.7  
- Debt weight ($D/V$) = 0.3  
- Cost of equity ($R_e$) = 12%  
- Cost of debt ($R_d$) = 8%  
- Tax rate ($T_c$) = 30%  

$$
WACC = (0.7 \times 0.12) + (0.3 \times 0.08 \times (1 - 0.3))
$$

$$
WACC = 0.084 + 0.0168 = 0.1008 \quad \text{or} \quad 10.08\%
$$

## 💹 Cost of Capital: Advanced Considerations

The cost of capital is **not a single, fixed number**; it varies based on a company's financial structure, risk, and the valuation method used.

---

### 🔹 Levered vs. Unlevered Beta

- **Levered Beta ($\beta_L$):**  
  - The beta from a financial database (e.g., Bloomberg).  
  - Measures **equity risk**, including the additional risk from debt.  

- **Unlevered Beta ($\beta_U$):**  
  - Removes the effect of debt.  
  - Shows the **pure business risk** of the company's assets.  

- **Relationship Formula:**  

$$
\beta_L = \beta_U \times \left[ 1 + \frac{D}{E} (1 - T_c) \right]
$$

- **Advanced Use:**  
  1. Identify **comparable public companies**.  
  2. **Unlever their betas** to remove debt effect.  
  3. Calculate the **average unlevered beta**.  
  4. **Re-lever** using the target company's/project's capital structure.  

> This approach is crucial for investment bankers and private equity analysts.

---

### 🔹 APV vs. WACC

- **WACC:**  
  - Standard approach.  
  - Incorporates the **tax shield** of debt directly into the discount rate.  
  - Assumes a **constant debt-to-equity ratio**.

- **Adjusted Present Value (APV):**  
  - Two-step method used when **capital structure changes significantly**:  
    1. Calculate firm value as if **all-equity financed**.  
    2. Separately calculate the **present value of tax shields** and add to unlevered value.  

- **Choice:**  
  - APV is preferred for **highly-leveraged transactions** (e.g., LBOs) or projects with **non-constant debt schedules**.

---

### 🔹 Market Values vs. Book Values

- Always use **market values** for equity and debt when calculating WACC.  
- Book values from the balance sheet may **misrepresent the true proportion of capital** in the market.

---

## 📊 Additional Valuation Methods

There are several valuation methods beyond basic equity and firm valuation, each suited for different scenarios.

---

### 1️⃣ Relative Valuation (Multiples)

- Compare a company's valuation to that of its peers.  
- Key idea: **similar companies should be valued similarly**.  
- Common multiples used by quants:  
  - **P/E Ratio (Price-to-Earnings):** Stock price vs. earnings per share  
  - **P/B Ratio (Price-to-Book):** Stock price vs. book value  
  - **EV/EBITDA (Enterprise Value-to-EBITDA):** Useful for comparing firms with different debt/tax structures  
  - **P/S Ratio (Price-to-Sales):** Used for early-stage or distressed companies  

> A quant performs a **multiples analysis**, comparing a company's metrics against a pre-selected peer group to identify over- or undervaluation relative to the market.

---

### 2️⃣ Sum-of-the-Parts (SOTP) Valuation

- Used for **conglomerates or diversified companies** with multiple business units.  
- Steps:  
  1. Value each business unit separately using the most appropriate method (DCF, multiples, etc.)  
  2. Sum the values of all business units  
  3. Subtract corporate-level debt  
  4. Add value of corporate assets (cash, investments, etc.)  

> Reveals if the market is **undervaluing or overvaluing** the company due to a conglomerate discount or premium.

---

### 3️⃣ Real Options Valuation

- Applies an **options pricing framework** to value strategic decisions or assets.  
- Recognizes the **flexibility of management** to make future choices.  
- Examples of real options:  
  - **Abandonment option:** Can stop a project if unsuccessful  
  - **Expansion option:** Can scale a project if successful  
  - **Timing option:** Can defer investment until favorable conditions arise  

> Uses models like **Black-Scholes** to quantify the value of embedded options, which a standard DCF would ignore.  
> Especially relevant for **startups, R&D projects, and natural resource exploration**.

---

### 4️⃣ Liquidation Valuation

- Determines the value if the company is **shut down and assets sold**.  
- Relevant for financially **distressed or bankrupt companies**.  
- Steps:  
  1. Estimate fair market value of all tangible assets (property, inventory, equipment)  
  2. Subtract all liabilities (debt, accounts payable)  
  3. The remaining value represents potential **cash distributed to shareholders**  

---

> These methods form the **fundamental building blocks** of valuation, but a top-tier quant integrates them into a **comprehensive, data-driven framework** for robust company analysis.

---
## Integration of Multiple Valuation methods

Use multiple models to create a valuation range, which provides a more robust and defensible conclusion. For instance, a quant would build:
- A DCF model to establish an intrinsic, long-term value.
- A Relative Valuation model to benchmark the company against a carefully selected peer group using various multiples (P/E, EV/EBITDA, etc.).
- A Sum-of-the-Parts (SOTP) model for a diversified company like Reliance to capture the individual value of its distinct business units.

The final valuation is not a single number but a convergence of these different approaches, which confirms the result's validity.

---
