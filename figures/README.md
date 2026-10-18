# Figures

These PNG files are selected portfolio assets for GitHub display. The notebook generates the model and profiling figures, and `src/generate_portfolio_figures.py` rebuilds the summary versions from the recorded CSV tables in `reports/`.

Files written by the notebook:

- `01_model_performance_comparison.png`: Precision, Recall, F1, ROC-AUC, and PR-AUC for both models.
- `02_confusion_matrices.png`: confusion matrices of both models at the 0.5 threshold.
- `03_roc_curve.png`: ROC curves of both models with AUC values.
- `04_precision_recall_curve.png`: Precision-Recall curves with Average Precision values.
- `05_random_forest_feature_importance.png`: top 10 impurity-based feature importance values.
- `06_feature_group_contribution.png`: ROC-AUC by cumulative feature group.
- `07_repayment_behavior_heatmap.png`: observed default rate by delay and payment-to-bill bins.
- `08_repayment_risk_profile_default_rate.png`: observed default rate by repayment behavior risk profile.

Files rebuilt from `reports/` by the summary script:

- `09_model_discrimination_summary.png`: recorded ROC-AUC and PR-AUC values for the two models.
- `10_confusion_matrices.png`: recorded confusion matrices at the 0.5 threshold.
- `11_random_forest_feature_importance.png`: recorded top 10 feature importance values.
- `12_feature_group_contribution.png`: recorded ROC-AUC by feature group.
- `13_repayment_risk_profile_default_rate.png`: observed default rates for the Low, Medium, and High Risk profiles.

Run `python src/generate_portfolio_figures.py` to rebuild the 09-13 summary figures from the recorded result tables.
