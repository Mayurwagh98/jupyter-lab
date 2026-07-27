# Credit / Loan Approval — Classification Project

An end-to-end machine learning project that predicts whether a loan application is approved (`Loan_Approved`). It walks through the full workflow — cleaning, EDA, encoding, scaling, model comparison, and feature engineering — and compares three classifiers to pick the best one.

## Contents

| File | Purpose |
|------|---------|
| `credit_wise.ipynb` | Full end-to-end pipeline: cleaning → EDA → encoding → modelling → feature engineering |
| `solution.ipynb` | Reference/solution version of the same workflow |
| `loan_approval_data.csv` | Loan applicant dataset (20 columns) |

## Workflow (both notebooks)

1. **Missing values** — split columns by type, then impute numeric with the mean and categorical with the most frequent value (`SimpleImputer`).
2. **EDA** — class balance pie chart, category bar plots (`bar_label`), income histograms, box plots for outliers, and hue-split histograms comparing approved vs. rejected applicants.
3. **Cleaning** — drops the non-predictive `Applicant_ID`.
4. **Encoding** — `LabelEncoder` for ordinal/binary columns (`Education_Level`, `Loan_Approved`); `OneHotEncoder(drop="first")` for nominal columns (employment, marital status, loan purpose, property area, gender, employer category).
5. **Correlation heatmap** — `sns.heatmap` plus correlation of each feature with the target.
6. **Split & scale** — `train_test_split` then `StandardScaler`.
7. **Model comparison** — trains **Logistic Regression**, **KNN**, and **Naive Bayes**, each evaluated on precision, recall, F1, accuracy, and confusion matrix. Naive Bayes is selected as best on precision.
8. **Feature engineering** — adds squared terms (`DTI_Ratio_sq`, `Credit_Score_sq`), drops the originals, and re-runs all three models to check for improvement.

## Dataset — `loan_approval_data.csv`
Loan applicant records with income (applicant & co-applicant), employment status, age, marital status, dependents, credit score, existing loans, DTI ratio, savings, collateral value, loan amount/term/purpose, property area, education, gender, and employer category. Target: `Loan_Approved` (Yes/No).

## Concepts Covered
- Missing-value imputation (mean / most-frequent)
- Exploratory data analysis with seaborn/matplotlib (pie, bar, histogram, box plots)
- Outlier inspection via box plots
- Label and one-hot encoding
- Correlation analysis and heatmaps
- Feature scaling (`StandardScaler`)
- Comparing multiple classifiers (Logistic Regression, KNN, Naive Bayes)
- Classification metrics: precision, recall, F1, accuracy, confusion matrix
- Choosing a model based on the metric that matters (precision)
- Feature engineering (polynomial/interaction terms)

## Requirements
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

## Usage
Open either notebook in Jupyter and run top to bottom; both read `loan_approval_data.csv` from this folder.
