This project focused on building a production-style credit risk scorecard to predict loan default probability, following industry-standard practices used by banks and NBFCs.


Problem Statement

The objective was to develop an interpretable and stable credit risk model that accurately predicts the probability of default (PD) while satisfying business and regulatory requirements such as explainability, robustness, and population stability.

Data Preparation & Feature Engineering, Performed extensive data cleaning, handling missing values, outliers, and inconsistent borrower attributes.

Applied ChiMerge binning to continuous variables to: Enforce monotonic relationship with default risk,  Reduce noise and variance, Improve model interpretability and stability, Transformed binned variables using Weight of Evidence (WOE) encoding to:

Capture predictive power of each bin

Enable linear relationship with log-odds of default

Evaluated variable strength using Information Value (IV) to retain only statistically and business-relevant predictors.

Modeling & Scorecard Development

Built a Logistic Regression model as the core PD estimator due to its:

Transparency

Regulatory acceptance

Ease of scorecard translation

Converted model coefficients into a credit scorecard using:

Base score and points-to-double-odds (PDO) framework

Business-aligned scaling for score interpretation

Optimized decision cutoffs to balance:

Default capture rate

Approval rate

Business risk tolerance

Model Evaluation & Validation

Evaluated model performance using industry-standard metrics:

AUC = 0.88 → strong discriminatory power

KS = 0.55 → excellent separation between good and bad borrowers

Conducted out-of-sample validation to ensure generalization.

Assessed population stability using Population Stability Index (PSI):

Achieved PSI ≈ 0.0001, indicating highly stable feature distributions and minimal data drift.

Benchmarking & Explainability

Benchmarked the scorecard against XGBoost to compare performance with a non-linear model.

Used SHAP values to:

Identify key risk drivers

Validate consistency with WOE trends

Demonstrated that while XGBoost offered marginal performance gains, the logistic scorecard provided superior interpretability and governance compliance, making it more suitable for real-world deployment.
