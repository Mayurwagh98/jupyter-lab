# K-Nearest Neighbors (KNN) — Classification

Notebooks exploring the **K-Nearest Neighbors** classifier: choosing the right `k`, tuning it with cross-validation, wrapping preprocessing in a pipeline, and comparing KNN against other classifiers on the Iris dataset.

## Contents

| File | Purpose |
|------|---------|
| `knn.ipynb` | KNN on the Heart dataset — tuning `k`, GridSearchCV, and pipelines |
| `assignment.ipynb` | Iris classification comparing KNN, Logistic Regression, and Naive Bayes |
| `iris_flower.ipynb` | Iris classification (similar multi-model comparison) |
| `1-heart.csv` | Heart disease dataset (target = disease present) |
| `Iris.csv` | Classic Iris flower dataset (3 species) |

## Notebook Details

### knn.ipynb — Tuning KNN
- Loads the heart dataset, splits, and applies `StandardScaler` (KNN is distance-based, so scaling matters).
- Manually compares `k = 3, 5, 7, 9` using recall, accuracy, and precision (k=7 gave the best result).
- **GridSearchCV** — 5-fold cross-validation over `n_neighbors` scored on recall, inspecting `cv_results_` and `best_params_`.
- **Pipeline** — chains `StandardScaler` + `KNeighborsClassifier` inside a `Pipeline` so scaling happens correctly inside cross-validation, tuned again with GridSearchCV.

### assignment.ipynb & iris_flower.ipynb — Model Comparison
- Encode the 3 Iris species with `LabelEncoder`.
- Train **Logistic Regression**, **Naive Bayes**, and **KNN**, then compare accuracy, confusion matrix, and classification report for each.

## Concepts Covered
- K-Nearest Neighbors classification
- Why feature scaling matters for distance-based models
- Choosing the hyperparameter `k`
- Cross-validation and hyperparameter tuning with `GridSearchCV`
- Building scikit-learn `Pipeline`s to prevent data leakage
- Multi-class classification
- Comparing multiple models (KNN vs. Logistic Regression vs. Naive Bayes)
- Metrics: accuracy, precision, recall, confusion matrix, classification report

## Requirements
```bash
pip install pandas scikit-learn
```

## Usage
Open a notebook in Jupyter and run top to bottom. Notebooks read `1-heart.csv` or `Iris.csv` from this folder (`iris_flower.ipynb` expects the file as `iris.csv`).
