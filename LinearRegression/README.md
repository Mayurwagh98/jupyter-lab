# Linear Regression & Regularization

Notebooks covering **Linear Regression** end to end — from a basic model to feature engineering, evaluation metrics, over/underfitting, and **Lasso (L1) regularization** with cross-validated alpha selection.

## Contents

| File | Purpose |
|------|---------|
| `insurance.ipynb` | Predict medical charges — feature engineering, evaluation, interaction terms, over/underfit |
| `lasso_regression.ipynb` | Lasso (L1) regression on the insurance data with alpha tuning (LassoCV) |
| `house_price.ipynb` | Predict house sale price — cleaning, encoding, and regression metrics |
| `insurance.csv` | Medical insurance dataset |
| `HousePricePrediction.csv` | House price dataset |

## Notebook Details

### insurance.ipynb — Linear Regression Fundamentals
- Predicts `charges` from age, sex, BMI, children, smoker, region.
- Scatter plot of BMI vs. charges colored by smoker to motivate the features.
- Manual encoding (`map` for binary sex/smoker) and one-hot encoding of `region`.
- Trains `LinearRegression`; evaluates with **R²** and **Adjusted R²**.
- **Interaction features** — `age × smoker` and `bmi × smoker` to capture combined effects.
- Compares training vs. test R² to reason about **underfitting vs. overfitting**.

### lasso_regression.ipynb — L1 Regularization
- Same engineered insurance features.
- Sweeps `alpha` values manually, plotting MSE vs. alpha to find the sweet spot.
- Uses **`LassoCV`** to automatically select the best alpha via cross-validation.

### house_price.ipynb — Regression on House Prices
- Drops `Id`, fills missing `SalePrice` with the mean, drops remaining nulls.
- One-hot encodes categorical columns (`MSZoning`, `LotConfig`, `BldgType`, `Exterior1st`).
- Trains `LinearRegression` and evaluates with **R², MAE, RMSE, and MAPE**.

## Concepts Covered
- Simple and multiple linear regression
- Manual encoding (`map`) and one-hot encoding (`get_dummies`)
- Feature engineering and interaction terms
- Regression metrics: R², Adjusted R², MAE, RMSE, MAPE, MSE
- Underfitting vs. overfitting (train vs. test comparison)
- Lasso (L1) regularization and its effect
- Hyperparameter (alpha) tuning manually and with `LassoCV`

## Requirements
```bash
pip install pandas numpy scikit-learn seaborn matplotlib
```

## Usage
Open a notebook in Jupyter and run top to bottom; they read `insurance.csv` or `HousePricePrediction.csv` from this folder.
