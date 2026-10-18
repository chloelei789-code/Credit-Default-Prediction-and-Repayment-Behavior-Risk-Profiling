# Models

This folder is reserved for saved model artifacts. It is intentionally empty because the project is designed for learning and reproducibility rather than deployment.

## What the notebook does

`notebooks/Credit_Default_Project2.ipynb` trains Logistic Regression and Random Forest on every full run but keeps them in memory only. The fitted pipelines are not written to disk, and no `.pkl` or `.joblib` files are produced or required. All recorded results are exported as CSV tables to `reports/`, and the run ends with predictions, metrics, and figures.

## If model artifacts are added later

For example, to reuse a fitted pipeline without retraining:

```python
import joblib

joblib.dump(logistic_model, "../models/logistic_regression.joblib")
```

Suggested naming: `logistic_regression.joblib`, `random_forest.joblib`, or a name that records the date and data version, such as `random_forest_2026-10.joblib`. Saved artifacts are local outputs and should not be committed, because they depend on the dataset version and library versions used at training time.
