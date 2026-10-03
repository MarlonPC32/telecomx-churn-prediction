# Telecom X — Churn Prediction (Machine Learning)

![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![pandas](https://img.shields.io/badge/pandas-data-green)
![Jupyter](https://img.shields.io/badge/Jupyter-notebook-orange)

Machine learning models to predict customer churn for Telecom X.

## Project Overview

In this project, I developed a machine learning pipeline to predict customer churn for Telecom X. The main goal is to identify which customers are more likely to cancel their services and understand the factors that influence that decision.

By building predictive models and analyzing the most relevant variables, this project provides insights that help anticipate churn and design more effective customer retention strategies.

This project is part of the Telecom X Data Science Challenge (Oracle Next Education), where the objective is to move beyond exploratory data analysis and develop predictive models capable of identifying churn risk.

> **Why this matters for fintech:** churn prediction is a binary classification problem — the same family of problems as credit default prediction and fraud detection. The pipeline here (EDA → feature engineering → Logistic Regression / Random Forest → precision/recall/F1 evaluation) transfers directly to risk modeling in financial services.

## Project Structure

```
telecomx-churn-prediction
├── TelecomX_Churn_Prediction.ipynb   # full workflow: prep, EDA, training, evaluation
├── .gitignore
└── README.md
```

## Dataset

Customer data from Telecom X: demographics, subscribed services, contract information, billing data, and churn status.

The data was cleaned and preprocessed in the first part of the challenge (see [telecomx-churn-analysis](https://github.com/MarlonPC32/telecomx-churn-analysis)) and used here as input for the ML pipeline.

## Data Preparation

- **Variable classification:** categorical (gender, contract type, internet service, payment method, add-on services) and numerical (tenure, monthly charges, total charges)
- **Feature engineering:** one-hot encoding for categorical variables; derived variable `Cuentas_Diarias` (estimated daily cost from monthly billing); dropped non-predictive identifiers
- **Train/test split:** 70% training / 30% testing

## Exploratory Data Analysis (EDA)

Before modeling: churn vs. non-churn distributions, tenure vs. churn, billing variables vs. cancellation. Boxplots, scatter plots, and correlation heatmaps to surface relationships between variables.

## Machine Learning Models

### Logistic Regression
Linear model estimating the probability a customer cancels, based on input variables. Useful for interpreting how individual variables contribute to the prediction.

### Random Forest
Ensemble of decision trees capturing complex non-linear relationships, with built-in feature importance.

## Model Evaluation

Both models evaluated with **accuracy, precision, recall, F1-score, and confusion matrices** on the held-out test set. (Full evaluation outputs are in the notebook.)

## Key Factors Influencing Churn

From Random Forest feature importance and Logistic Regression coefficients, the strongest predictors include: total charges, customer tenure, monthly charges, estimated daily charges, fiber optic internet service, electronic check payment method, and paperless billing.

Spending patterns, service configuration, and contract characteristics play the most important role in predicting churn.

## Strategic Insights

- Customers with shorter tenure are more likely to cancel — the early lifecycle stage is critical for retention
- Billing structure and perceived service value influence churn decisions
- Personalized packages, loyalty incentives, or targeted promotions could reduce churn risk

## How to Run the Project

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

Open `TelecomX_Churn_Prediction.ipynb` in Jupyter or Google Colab and run all cells.

## Author

**Marlon P. Crespo** — Computer Science @ Columbia University
[LinkedIn](https://www.linkedin.com/in/marlonpc) · mp4628@columbia.edu
