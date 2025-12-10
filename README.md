# credit-card-fraud-detection
Credit Card Fraud Detection

This project implements an end-to-end Credit Card Fraud Detection System using machine learning.
It includes EDA, class imbalance handling, sampling (SMOTE/undersample/oversample),
model training (Random Forest / XGBoost), evaluation (Precision, Recall, ROC-AUC),
and saving a reusable fraud detection pipeline.

 Features

Exploratory Data Analysis (EDA)

Class imbalance visualization

Amount & time distribution

Correlation heatmap

Fraud vs Legit comparison

Imbalanced Data Handling

Undersampling

Oversampling

SMOTE (default)

Models

Random Forest

XGBoost

GridSearchCV tuning

Evaluation Metrics

Precision, Recall, F1

ROC-AUC

Confusion Matrix

Precision–Recall & ROC curves

Model Saving

Saves final pipeline as:

models/fraud_pipeline.joblib

 Project Structure
.
├── credit_card_fraud_detection.py
├── creditcard.csv        # dataset (user provided)
├── models/
│   └── fraud_pipeline.joblib
├── artifacts/
│   └── eda_plots/
│       ├── class_distribution.png
│       ├── amount_distribution.png
│       ├── amount_by_class_boxplot.png
│       ├── time_distribution.png
│       ├── correlation_matrix.png
│       ├── precision_recall_curve.png
│       └── roc_curve.png
├── reports/
│   └── metrics_report.txt
└── README.md

Dataset

Use the popular credit card fraud dataset:

284,807 transactions

492 fraud cases (severely imbalanced)

File required:

creditcard.csv

 Installation

Install dependencies:

pip install -r requirements.txt

requirements.txt
pandas
numpy
scikit-learn
matplotlib
seaborn
imbalanced-learn
xgboost
joblib

 Run the Project
Default run (SMOTE + XGBoost)
python credit_card_fraud_detection.py --data creditcard.csv

Choose sampling technique
--sampling none
--sampling undersample
--sampling oversample
--sampling smote

Choose model
--model rf
--model xgb


Example:

python credit_card_fraud_detection.py --data creditcard.csv --sampling smote --model xgb

 Output Files
 Saved Model
models/fraud_pipeline.joblib

 EDA Plots
artifacts/eda_plots/*.png

 Metrics Report
reports/metrics_report.txt

 Business Threshold Decision

Fraud detection focuses more on recall because:

Missing a fraud → high financial loss

A false positive → only requires manual review

Use the Precision-Recall curve to select a decision threshold that fits the business requirement.
