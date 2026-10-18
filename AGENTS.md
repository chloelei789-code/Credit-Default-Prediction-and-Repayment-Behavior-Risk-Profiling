# Repository Guidelines

This file describes the repository structure, run commands, and collaboration conventions for contributors.

## Project Structure

- `notebooks/`: end-to-end analysis. `Credit_Default_Project2.ipynb` is the project notebook.
- `src/`: standalone Python utilities, currently `generate_portfolio_figures.py`.
- `reports/`: saved result CSVs and the HTML export of the notebook.
- `figures/`: PNG images referenced by `README.md`.
- `data/`: data acquisition notes only; the raw CSV is not committed.
- `dataset/`: the local UCI data copy used by the main notebook.
- `models/`: optional local model artifacts folder.

## Development and Run Commands

```bash
pip install -r requirements.txt      # install dependencies
jupyter notebook notebooks/Credit_Default_Project2.ipynb  # run the full analysis
python src/generate_portfolio_figures.py  # regenerate summary figures from reports/
```

The project has no build step, test framework, or linter configured.

## Code Style and Naming

- Python and notebooks use 4-space indentation, double quotes, and PEP 8 spacing; `src/` uses snake_case function names and UPPER_CASE constants such as `ROOT` and `FIGURES`.
- Keep the original column names (`LIMIT_BAL`, `PAY_AMT1`, `default.payment.next.month`) and use snake_case for engineered features such as `delay_months` and `avg_payment`.
- Notebook cells must be repeatable, and running the notebook from the start should reproduce the same outputs; random processes use `random_state=42`.
- Paths in `src/` are built from `Path(__file__)`; figure filenames start with a two-digit order number, such as `13_repayment_risk_profile_default_rate.png`.

## Testing and Validation

The repository has no automated tests or coverage requirement. After changes, run the affected notebook or script from start to finish and confirm that outputs are finite, dimensions are correct, and results are stable; also check that the `figures/` images and `reports/` CSVs still match `README.md`.

## Commit and Pull Request Guidelines

There is currently no Git history. Use short imperative commit messages such as `Add payment ratio feature` or `Fix figure path handling`, and keep each commit focused on one notebook, script, or result set.

Pull requests should describe the change, the commands that were run, and any updated figures or metrics, and they should link the relevant issue. Screenshots are only needed for visualization or report changes.

## Data and Conclusions

The raw dataset must not be committed; see `data/README.md` for download and placement instructions. Results describe associations in this public dataset only. They should not be interpreted as causal relationships or presented as a production-ready credit scoring conclusion.
