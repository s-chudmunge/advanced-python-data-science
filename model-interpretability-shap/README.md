# Model Interpretability with SHAP & LIME

## Project Overview: Credit Scoring Model Interpretation

This project focuses on interpreting a high-performance machine learning model trained for credit scoring. While accuracy is crucial for credit risk assessment, understanding *why* a model makes a decision is equally important for transparency and regulatory compliance (e.g., GDPR, ECOA).

**Model:** XGBoost Classifier trained on a synthetic credit dataset.

### Key Insights: What the Model Learned
- **Primary Feature:** `Credit_Score` was the most significant predictor, showing a strong positive correlation with approval probability in SHAP beeswarm plots.
- **Secondary Feature:** `Debt_to_Income_Ratio` had a non-linear relationship with approval; exceeding a threshold of 0.4 led to a sharp decrease in approval probability, as visualized in SHAP dependence plots.
- **Local Explanations:** Using LIME, we analyzed individual "edge cases" to explain why a high-income applicant with a low credit score was denied, highlighting the local influence of `Credit_Score` over `Income`.

### Fairness and Bias Considerations
- **Fairness:** The SHAP analysis revealed that certain features like `Marital_Status` and `Gender` (synthetic proxies) had low overall importance, but their dependence plots showed slight biases that could lead to disparate impacts.
- **Mitigation:** Future iterations should include adversarial debiasing or re-weighting techniques to ensure equitable outcomes across demographic groups.

## Implementation Details
The accompanying Jupyter notebook (`interpretability.ipynb`) provides a full end-to-end implementation including:
1. **Model Training:** Training an XGBoost model on a credit dataset.
2. **SHAP Analysis:** Generating waterfall, beeswarm (summary), and dependence plots.
3. **LIME Explanations:** Local interpretation of a single prediction.
4. **Permutation Importance:** Assessing feature importance by measuring the impact of shuffling each feature's values.
