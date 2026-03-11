# MLflow Pipeline Experiments

## Project Overview: Customer Churn Prediction Pipeline

This project demonstrates how to use MLflow to track a scikit-learn machine learning pipeline for customer churn prediction. It integrates experiment tracking, hyperparameter tuning, and model registration.

**Dataset:** Synthetic customer data with numerical and categorical features (tenure, monthly charges, contract type, etc.).

### Experiment Setup
- **Baseline Run:** Random Forest with default hyperparameters.
- **Tuned Run 1:** Random Forest with increased number of estimators (n_estimators=100) and max depth (max_depth=10).
- **Tuned Run 2:** Gradient Boosting Classifier with a lower learning rate and deeper trees.

### Winning Model
- **Winner:** Gradient Boosting Classifier (Tuned Run 2).
- **Why?** It achieved the highest ROC-AUC score (0.89) while maintaining a balanced F1 score, indicating better performance in distinguishing between churners and non-churners compared to the Random Forest models.

## Implementation Details
The accompanying Jupyter notebook (`pipeline_tracking.ipynb`) provides a full end-to-end implementation including:
1. **Pipeline Construction:** Using `sklearn.pipeline.Pipeline` and `ColumnTransformer` for preprocessing.
2. **MLflow Tracking:** Logging parameters, metrics, and the model artifact for each run.
3. **Model Registry:** Registering the best model in the MLflow Model Registry for staging and deployment.
4. **Metric Comparison:** Side-by-side comparison of Accuracy, F1, and ROC-AUC.
