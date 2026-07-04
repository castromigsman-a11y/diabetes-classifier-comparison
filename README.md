# Comparative Classifiers for Diabetes Risk Prediction

Benchmark of six supervised-learning algorithms for predicting diabetes from routine
clinical measurements.

## Overview

Using the Pima Indians Diabetes dataset, this project trains and compares six classifier
families on a common train/test split, evaluating them on accuracy, precision, and recall
— with particular attention to recall, since missing true cases (false negatives) is the
costly error in a screening setting.

## Data

`patients_diabetis.txt` — 768 patients, eight clinical predictors (glucose, blood pressure,
BMI, age, diabetes pedigree, number of pregnancies, etc.) and a binary diabetes label.
Tab-separated; the publicly available Pima Indians Diabetes dataset.

## Methods

- Standardised features and a stratified 67/33 train/test split (fixed seed).
- Six classifiers: k-nearest neighbours (several values of k), Gaussian naive Bayes, a
  multi-layer-perceptron neural network (three architectures), SVM (linear and RBF
  kernels), a decision tree, and random forests (100 and 200 trees).
- A common evaluation function reporting accuracy, precision, and recall for each model.

## Key results

No single classifier dominated across all three metrics. An **RBF-kernel SVM gave the best
test accuracy (0.76)** with the strongest recall among the top-accuracy models (0.61);
k-nearest neighbours, naive Bayes, and a small neural network followed at ~0.75 accuracy,
and random forest sat mid-pack (0.74 accuracy, 0.54 recall). The highest recall overall came
from a larger neural network (~0.63) at some cost to accuracy — a reminder that, in a
screening context where false negatives are the costly error, the accuracy/recall trade-off
matters more than a single headline number.

## Repository contents

- `classifier_comparison.ipynb` — full analysis notebook (Python)
- `patients_diabetis.txt` — data
- `report.pdf` — rendered notebook (optional)
- `README.md`

## Running the analysis

Requires Python with `pandas`, `numpy`, `scikit-learn`, `matplotlib`, and `seaborn`. Open
the notebook in Jupyter and run all cells, keeping the data file in the same directory.

## Notes

Developed during my MSc in Bioinformatics and Biostatistics. Code comments are in Spanish.
