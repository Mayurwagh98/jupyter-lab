# Logistic Regression — Binary Classification

Notebooks demonstrating **Logistic Regression** for binary classification, including feature scaling, evaluation metrics, and **L1 (Lasso) / L2 (Ridge) regularization**.

## Contents

| File | Purpose |
|------|---------|
| `logistic_regression.ipynb` | Heart disease prediction with scaling and evaluation |
| `assignment.ipynb` | Employee turnover prediction comparing baseline, L1, and L2 regularization |
| `heart.csv` | Heart disease dataset (target = disease present) |
| `employee_turnover.csv` | Employee attrition dataset |

## Notebook Details

### logistic_regression.ipynb — Heart Disease
- Splits the data and applies `StandardScaler`.
- Trains `LogisticRegression(max_iter=1000)`.
- Evaluates with accuracy, precision, and recall.

### assignment.ipynb — Employee Turnover + Regularization
- Predicts `Employee_Turnover`.
- Trains a **baseline** Logistic Regression.
- **L1 regularization (Lasso):** `penalty="l1", solver="liblinear", C=0.5`.
- **L2 regularization (Ridge):** `penalty="l2", C=1`.
- Compares all three via accuracy and full classification reports.

## Concepts Covered
- Logistic Regression for binary classification
- Feature scaling with `StandardScaler`
- Classification metrics: accuracy, precision, recall, classification report
- Regularization: L1 (Lasso) vs. L2 (Ridge) and the `C` parameter
- Choosing solvers (`liblinear` for L1)
- Comparing regularized vs. unregularized models

## Requirements
```bash
pip install pandas scikit-learn seaborn
```

## Usage
Open a notebook in Jupyter and run top to bottom; they read `heart.csv` or `employee_turnover.csv` from this folder.
