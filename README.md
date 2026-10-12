<<<<<<< HEAD
# ML_EDA_full_fledge: Loan Default EDA & Feature Selection Project

A production-grade, end-to-end Exploratory Data Analysis (EDA), Feature Engineering, and Feature Selection project structured according to the [Cookiecutter Data Science](https://cookiecutter-data-science.drivendata.org/) (CCDS) standard.

---

## Directory Structure

```text
.
├── .github/workflows/       # GitHub Actions CI/CD
├── data/
│   ├── raw/                 # Original datasets
│   ├── interim/             # Intermediate datasets
│   └── processed/           # Processed modeling datasets
├── docs/                    # Project documentation
├── models/                  # Trained model artifacts
├── notebooks/               # EDA and feature selection notebooks
├── references/              # Data dictionary and references
├── reports/                 # Metrics and evaluation figures
├── src/                     # Source code
│   ├── config.py
│   ├── dataset.py
│   ├── features.py
│   ├── train.py
│   ├── predict.py
│   ├── reports.py
│   ├── api.py
│   └── modeling/
├── tests/                   # Automated tests
├── LICENSE
├── Makefile
├── pyproject.toml
├── requirements.txt
└── README.md
```

---

## Quickstart & Environment Setup

### 1. Create Virtual Environment & Install Dependencies

```bash
# Create virtual environment (.venv) and install dependencies
make venv

# Activate virtual environment
source .venv/bin/activate
```

---

## Running the End-to-End Pipeline

You can run individual pipeline stages via `make` or direct module execution:

```bash
# 1. Verify Dataset Loading & Schema
make data

# 2. Feature Engineering & Preprocessing Pipeline
# Processes raw data, creates missingness flags, constructs financial ratios, fits ColumnTransformer, and saves train/test CSVs
make features

# 3. Model Training & Evaluation
# Trains Logistic Regression and Random Forest models, evaluates performance, and saves model binary to models/
make train

# 4. Batch Prediction Inference
# Generates default probabilities on test data
make predict

# 5. Generate Metrics & Evaluation Figures
# Creates reports/metrics.json and saves figures to reports/figures/
make reports

# 6. Sample Single Application API Inference
make api

# 7. Run Automated Pytest Unit Tests
make test

# 8. Lint Codebase with Ruff
make lint

# 9. Execute Full End-to-End Pipeline
make all
```

---

## Key Business & Technical Findings

1. **Target Leakage Remediation:** Post-decision interest rate attributes (`rate_of_interest`, `Interest_rate_spread`, `Upfront_charges`) were identified as future leakage (missing in 100% of defaults) and removed from pre-underwriting decisioning.
2. **Missingness Indicator Flags:** Missing property appraisals (`property_value_isna`) and debt ratios (`dtir1_isna`) carried a **+0.4132** correlation with default, converting missingness into high-precision binary predictors.
3. **Compound Risk Surfaces:** Debt-to-Income multiplied by Loan-to-Value (`DTI_x_LTV`) captured non-linear layered risk.
4. **Benchmark Model Performance:**
   - **ROC-AUC:** **0.8847**
   - **PR-AUC:** **0.8272**
   - **Accuracy:** **87.92%**
=======
# ML_Full_fledge
>>>>>>> e09dc5aae5299e7fa0c77a0d67f554f66470376d
