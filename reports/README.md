# Reports and Recorded Results

This folder stores the lightweight result tables produced by the executed notebook, the exported HTML report, and the source data used to rebuild the portfolio figures in `figures/`. The recorded numbers match the current notebook run and are rounded to four decimals.

## Contents

| File | Written by | What it records |
|---|---|---|
| `model_results.csv` | Notebook, section 4.2 | Accuracy, Precision, Recall, F1, ROC-AUC, and PR-AUC (Average Precision) for Logistic Regression and Random Forest on the test set |
| `confusion_matrices.csv` | Notebook, section 4.3 | True negatives, false positives, false negatives, and true positives for both models at the 0.5 threshold |
| `feature_importance.csv` | Notebook, section 5.1 | Top 10 impurity-based Random Forest importances with readable feature names |
| `feature_group_results.csv` | Notebook, section 6 | ROC-AUC, F1, and the incremental ROC-AUC change for the five cumulative feature sets |
| `repayment_risk_profiles.csv` | Notebook, section 7.2 | Customer count and observed default rate for the Low, Medium, High, and Unknown descriptive profiles |
| `Credit_Default_Project.html` | `jupyter nbconvert --to html` | Full HTML export of the executed notebook with all tables and figures |

## Notes

- Every CSV file is written by the notebook on a full run, so the files always reflect the latest execution rather than a separate manual export.
- Default rates in `repayment_risk_profiles.csv` are percentages computed on the full 30,000-customer sample, because the profile describes the whole dataset. The model metrics in `model_results.csv` and `confusion_matrices.csv` come from the 6,000-customer test set.
- Values are rounded for display only; the notebook keeps full precision in memory.
- The result tables are not a replacement for rerunning the analysis on the raw UCI dataset, which lives at `dataset/default_of_credit_card_clients_dataset.csv`.

## Reproduce

Run the notebook from top to bottom:

```bash
jupyter nbconvert --to notebook --execute --inplace notebooks/Credit_Default_Project2.ipynb --ExecutePreprocessor.timeout=900
```

Rebuild the static portfolio figures from these tables:

```bash
python src/generate_portfolio_figures.py
```

Re-export the HTML report:

```bash
jupyter nbconvert --to html --output Credit_Default_Project --output-dir reports notebooks/Credit_Default_Project2.ipynb
```
