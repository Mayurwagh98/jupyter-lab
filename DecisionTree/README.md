# Decision Trees — Classification & Regression

A hands-on collection of Jupyter notebooks exploring **Decision Tree** models with scikit-learn: how to build them, tune them, prune them, and apply them to real datasets. The notebooks progress from a minimal classifier to full preprocessing pipelines with hyperparameter tuning.

## Contents

| File | Purpose |
|------|---------|
| `DecisionClassifier.ipynb` | Decision tree classification on the Titanic dataset + pre-pruning and post-pruning |
| `DecisionRegressor.ipynb` | Decision tree regression on the Diabetes dataset + overfitting control |
| `shop_smart.ipynb` | End-to-end classification pipeline on e-commerce data with GridSearch tuning |
| `assignment.ipynb` | Same e-commerce problem with EDA, practised as an exercise |
| `shop_smart_ecommerce.csv` | Online shoppers dataset (12,330 sessions, 18 columns) used by the last two notebooks |

## Notebook Details

### 1. DecisionClassifier.ipynb — Classification & Pruning
Uses the Titanic dataset (via seaborn) to predict passenger survival.

- **Data cleaning:** handles missing values with `SimpleImputer` (median for `age`, most-frequent for `embarked`).
- **Encoding:** converts categorical `sex` and `embarked` to numbers with `LabelEncoder`.
- **Model:** trains a `DecisionTreeClassifier`, evaluates with `accuracy_score`, and visualizes the tree using `plot_tree`.
- **Pre-pruning:** loops over `max_depth` (2–10) and `min_samples_split` (5–30) to limit tree growth and reduce overfitting.
- **Post-pruning:** uses **cost-complexity pruning** (`cost_complexity_pruning_path` / `ccp_alpha`) — trains a tree for each alpha, then selects the alpha that maximizes test accuracy.
- **Combined:** applies pre- and post-pruning together (`max_depth` + best `ccp_alpha`).

### 2. DecisionRegressor.ipynb — Regression & Overfitting
Uses the scikit-learn Diabetes dataset to predict a continuous target.

- **Model:** `DecisionTreeRegressor`, evaluated with `mean_squared_error` and `r2_score` on both train and test sets.
- **Overfitting demo:** the default tree fits the training data almost perfectly but generalizes poorly (train vs. test gap).
- **Pre-pruning fix:** constrains the tree with `max_depth=3` and `min_samples_leaf=20` to improve test performance.

### 3. shop_smart.ipynb — Production-style Pipeline
Predicts whether an online shopping session generates `Revenue` from the e-commerce dataset.

- **Preprocessing:** `ColumnTransformer` combining `StandardScaler` (numeric) and `OneHotEncoder` (categorical).
- **Pipeline:** wraps preprocessing + `DecisionTreeClassifier` into a single scikit-learn `Pipeline`.
- **Imbalance handling:** `class_weight="balanced"` plus `max_depth` and `min_samples_leaf` constraints.
- **Stratified split:** `train_test_split(..., stratify=y)` to preserve class ratios.
- **Evaluation:** `f1_score`, `classification_report`, and `confusion_matrix`.
- **Tuning:** `GridSearchCV` over `max_depth` and `min_samples_leaf` with 5-fold cross-validation scored on F1.

### 4. assignment.ipynb — Practice Exercise
Reworks the same e-commerce classification problem, adding **exploratory data analysis** (a pie chart of the Revenue class balance), feature-type inspection with `.info()`, and repeating the full pipeline + GridSearch workflow.

## Dataset — `shop_smart_ecommerce.csv`
Online shoppers' purchasing-intention data: 12,330 rows, 18 columns. Features cover page-visit counts and durations (`Administrative`, `Informational`, `ProductRelated`), behavioural metrics (`BounceRates`, `ExitRates`, `PageValues`), and session context (`Month`, `VisitorType`, `Weekend`, `Region`, etc.). The target `Revenue` (True/False) indicates whether the session ended in a purchase — a notably imbalanced class.

## Concepts Covered
- Decision Tree **classification** and **regression**
- Handling **missing data** (`SimpleImputer`)
- **Encoding** categoricals (`LabelEncoder`, `OneHotEncoder`)
- **Feature scaling** (`StandardScaler`)
- **Train/test split** and **stratified** sampling
- **Overfitting** and how to detect it (train vs. test metrics)
- **Pre-pruning** (`max_depth`, `min_samples_split`, `min_samples_leaf`)
- **Post-pruning** via **cost-complexity pruning** (`ccp_alpha`)
- **Class imbalance** handling (`class_weight="balanced"`)
- **Pipelines** and **ColumnTransformer**
- **Hyperparameter tuning** with `GridSearchCV` and cross-validation
- **Model evaluation:** accuracy, F1, precision/recall, confusion matrix, MSE, R²
- **Tree visualization** with `plot_tree`

## Requirements
```
pandas, numpy, scikit-learn, matplotlib, seaborn
```
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

## Usage
Open any notebook in Jupyter and run the cells top to bottom. The Titanic and Diabetes datasets load automatically; the e-commerce notebooks read `shop_smart_ecommerce.csv` from the same folder.
