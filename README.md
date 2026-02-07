# Background  
This challenge focuses on signals generated on **illiquid assets**, which are often difficult to trade directly. To address this, signals are projected onto **liquid assets** by modeling the relationships between the two using historical data.  

The task is framed as a **classification problem**: instead of predicting exact returns, the models aim to predict the **trend direction** (positive or negative). Performance is evaluated with a **weighted accuracy metric**, which places greater importance on correctly classifying larger moves, since accuracy on significant changes matters more than on minor fluctuations.  

# Project Development Workflow  
The modeling process follows a structured progression, starting from the simplest linear approach and advancing toward more complex models with backtesting and refinements:

- **Model_1_SLM (Simple Linear Model)**  
  The earliest baseline, applying a straightforward linear regression to capture fundamental relationships in the data.  

- **Model_1 (Multi‑Linear Regression with Single Correlation Filter)**  
  Builds on the simple linear model by introducing multi‑linear regression. A single correlation filter is applied across all illiquid assets to improve explanatory power.  

- **Model_1_BT (Model 1 with Backtesting)**  
  Integrates backtesting into Model_1, estimating optimal parameters such as maximum bounds (X to X) and minimum bounds (X to Y) for more robust evaluation.  

- **Model_1_BT_enhance (Enhanced Backtesting)**  
  Refines the backtesting framework by breaking down the single correlation filter into individual filters for each asset. This stage improves reliability and sets the foundation for Model_2.  

- **Model_2 (Advanced Model)**  
  Expands the framework by replacing the single correlation filter with 100 independent correlation filters to capture deeper, asset‑specific insights.  

- **Model_2_BT (Advanced Model with Backtesting)**  
  Applies backtesting to the advanced model, confirming the optimal global bias parameter and ensuring predictive accuracy.  

# Summary  
The workflow progresses from **SLM → single correlation filter MLM → backtested → enhanced backtested → independent correlation filters MLM → backtested bias**, ensuring each stage is validated and improved iteratively.
