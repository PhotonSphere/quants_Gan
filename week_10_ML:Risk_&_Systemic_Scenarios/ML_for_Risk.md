Week 10 flow:

## ML for Risk

### Usage and tools:
#### Intro to ML for Risk – Mind Map

- ML for Risk
  - Classification → Predict risk categories
    - Logistic Regression
    - Decision Trees / Random Forests
    - Gradient Boosting (XGBoost, LightGBM)
    - Neural Networks
    - Use Cases:
      - Loan default prediction
      - Fraud detection
  - Clustering → Identify patterns without labels
    - K-Means
    - Hierarchical Clustering
    - DBSCAN
    - Use Cases:
      - Segment customers by risk profile
      - Detect fraud clusters
  - Systemic Risk Propagation → Model risk spread
    - Graph-based models (nodes = entities, edges = exposures)
    - Network Analysis
      - Centrality → Identify critical nodes
      - Contagion → Model failure propagation
    - Simulation Models (Monte Carlo)
    - Use Cases:
      - Stress-testing financial networks
      - Interbank contagion analysis
  - Challenges
    - Data quality and missing values
    - Model interpretability
    - Dynamic and evolving risk
    - Overfitting historical patterns

---

#### ML for Investment – Mind Map

- ML for Investment
  - Risk Classification → Categorize assets/portfolios
    - Logistic Regression
    - Decision Trees / Random Forests
    - Gradient Boosting
    - Neural Networks / LSTM
    - Use Cases:
      - Classify stocks by drawdown risk
      - Predict portfolio breaches (VaR)
  - Clustering → Group similar investments
    - K-Means / K-Prototypes
    - Hierarchical Clustering
    - DBSCAN
    - Use Cases:
      - Segment stocks by risk-return profiles
      - Identify similar investment strategies
      - Detect anomalies or unusual assets
  - Time-Series & Predictive Modeling → Forecast returns/volatility
    - ARIMA / SARIMA
    - LSTM / GRU Networks
    - Random Forest / Gradient Boosting Regressors
    - Use Cases:
      - Stock price prediction
      - Portfolio volatility forecasting
  - Systemic & Market Risk → Model shock propagation
    - Network Analysis (nodes=assets, edges=correlations)
    - Stress Testing / Monte Carlo
    - Scenario Analysis
    - Use Cases:
      - Contagion risk during market crash
      - Sector vulnerability analysis
  - Challenges
    - Noisy financial data / missing values
    - Non-stationary market behavior
    - Overfitting historical patterns
    - Interpretability for investment advice

---

