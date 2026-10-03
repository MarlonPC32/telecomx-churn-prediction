# Telecom X — Customer Churn Prediction

Binary classification on 7,267 telecom customers: Logistic Regression vs. Random Forest to predict who cancels.

## Data

- `telecomx_datos_tratados.csv` — customer records with demographics, services, contract, billing, and churn label. Cleaned in the [EDA stage](https://github.com/MarlonPC32/telecomx-churn-analysis).
- 7,267 rows × 32 features after encoding. Imbalanced target: 25.7% churn (1,869) vs. 74.3% retained (5,398).
- Train/test split 70/30 (`random_state=42`); test n = 2,181.

## Pipeline

1. Dropped `customerID` (identifier, no signal).
2. One-hot encoded categoricals (`drop_first=True`).
3. Engineered `Cuentas_Diarias` = monthly charges / 30 (estimated daily spend).
4. Trained Logistic Regression (`max_iter=1000`) and Random Forest (`random_state=42`).

## Results

Test set (n = 2,181), metrics for the churn class:

| Model | Accuracy | Precision | Recall | F1 |
|---|---|---|---|---|
| Logistic Regression | 0.81 | 0.64 | 0.54 | 0.58 |
| Random Forest | 0.80 | 0.61 | 0.51 | 0.55 |

Logistic Regression outperformed Random Forest on every metric here — the linear model generalized better on this dataset. Full classification reports and confusion matrices are in the notebook.

## What drives churn

Random Forest feature importance (top 5):

| Feature | Importance |
|---|---|
| Charges.Total | 0.170 |
| tenure | 0.155 |
| Cuentas_Diarias | 0.129 |
| Charges.Monthly | 0.129 |
| Contract_two year | 0.035 |

Logistic Regression coefficients (top 5):

| Feature | Coefficient |
|---|---|
| InternetService_fiber optic | 0.545 |
| PaperlessBilling_Yes | 0.358 |
| PaymentMethod_electronic check | 0.245 |
| SeniorCitizen | 0.237 |
| MultipleLines_No phone service | 0.234 |

Reading: spending behavior and tenure dominate the tree model; service configuration and payment method dominate the linear model. Fiber-optic customers paying by electronic check with paperless billing churn the most.

## Reproduce

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

Open `TelecomX_Churn_Prediction.ipynb` and run all cells. The notebook reads `telecomx_datos_tratados.csv` from the repo directory.

## Context

Built for the Telecom X Data Science Challenge (Oracle Next Education). Same problem structure as credit default prediction — binary classification on tabular customer data.
