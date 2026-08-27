# Naive Bayes — Classification

A concise notebook demonstrating the **Gaussian Naive Bayes** classifier on the heart disease dataset.

## Contents

| File | Purpose |
|------|---------|
| `naive_bayes.ipynb` | Gaussian Naive Bayes for heart disease prediction |
| `heart.csv` | Heart disease dataset (target = disease present) |

## Workflow
1. Load the heart dataset and split features/target (`target`).
2. `train_test_split` (80/20).
3. Train `GaussianNB`.
4. Predict and evaluate with accuracy, recall, and precision.

## Dataset — `heart.csv`
Clinical features: age, sex, chest pain type (`cp`), resting blood pressure (`trestbps`), cholesterol (`chol`), fasting blood sugar (`fbs`), resting ECG (`restecg`), max heart rate (`thalach`), exercise-induced angina (`exang`), `oldpeak`, `slope`, `ca`, `thal`, and the binary `target`.

## Concepts Covered
- Gaussian Naive Bayes classification
- Train/test splitting
- Classification metrics: accuracy, precision, recall
- The assumption of feature independence behind Naive Bayes

## Requirements
```bash
pip install pandas scikit-learn
```

## Usage
Open `naive_bayes.ipynb` in Jupyter and run top to bottom; it reads `heart.csv` from this folder.
