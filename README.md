# Robust Multi-Class Benchmarking on Dry Bean Morphology

## Dataset

UCI Dry Bean Dataset.

Dataset ID: 602

DOI: 10.24432/C50S4B

Observed dataset:
- Rows: 13611
- Features: 16
- Classes: 7

## Algorithms

Four classifiers from four model families were evaluated:

1. Logistic Regression
2. k-NN
3. Decision Tree
4. RBF SVM

## Validation

Repeated nested stratified cross-validation:

- Outer CV: 5-fold
- Repetitions: 3
- Outer folds per algorithm: 15
- Inner CV: 2-fold
- Primary tuning metric: f1_macro

Repetition seeds:

[42, 43, 44]

## Hyperparameter tuning

Each algorithm uses three candidate configurations.

Logistic Regression:
- C = 0.1, 1, 10
- solver = lbfgs

k-NN:
- n_neighbors = 5, 11, 21

Decision Tree:
- max_depth = 10, 20, None

RBF SVM:
- C = 1, 10, 100
- gamma = scale

## Evaluation metrics

- Macro-F1
- Balanced Accuracy
- Cohen's Kappa
- Per-class Recall
- Training/Tuning Time
- Prediction Time

## Statistical analysis

- Friedman test
- Kendall's W
- Pairwise Wilcoxon signed-rank tests
- Holm multiple-comparison correction
- Wilcoxon effect size r

## Ablation

The reduced feature experiment removes:

- Perimeter
- ConvexArea
- EquivalentDiameter
- Compactness

The same 15 outer folds and nested tuning procedure are used.

## Reproducibility

All experiment outputs are generated programmatically.

The `results/` directory contains raw fold-level data and statistical results.

The `figures/` directory contains the generated figures.

The notebook downloads the UCI dataset programmatically.
