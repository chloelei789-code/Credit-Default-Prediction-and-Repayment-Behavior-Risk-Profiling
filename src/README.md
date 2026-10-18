# Source Utilities

This folder holds the standalone helper scripts used by the project.

## `generate_portfolio_figures.py`

Rebuilds the five summary figures in `figures/` from the saved CSV tables in `reports/`:

- `09_model_discrimination_summary.png`
- `10_confusion_matrices.png`
- `11_random_forest_feature_importance.png`
- `12_feature_group_contribution.png`
- `13_repayment_risk_profile_default_rate.png`

The script does not train any model. It only reads the recorded result tables, so the notebook must be run at least once before these figures are generated.

### Requirements

```bash
pip install -r requirements.txt
```

### Run

```bash
python src/generate_portfolio_figures.py
```

Paths are built from `Path(__file__).resolve().parents[1]`, so the script writes to the repository's own `figures/` folder regardless of the current working directory.
