# telecomx-churn-prediction
Machine learning models to predict customer churn for Telecom X.

# Telecom X – Churn Prediction (Machine Learning)

# Telecom X – Churn Prediction (Machine Learning)

## Project Overview

In this project, I developed a machine learning pipeline to predict customer churn for Telecom X. The main goal of the analysis is to identify which customers are more likely to cancel their services and understand the factors that influence that decision.

By building predictive models and analyzing the most relevant variables, this project aims to provide insights that can help Telecom X anticipate churn and design more effective customer retention strategies.

This project is part of the Telecom X Data Science Challenge, where the objective is to move beyond exploratory data analysis and develop predictive models capable of identifying churn risk.

## Project Structure

The repository is organized as follows:

telecomx-churn-prediction  
│  
├── TelecomX_Churn_Prediction.ipynb  
├── telecomx_datos_tratados.csv  
└── README.md  

TelecomX_Churn_Prediction.ipynb  
This notebook contains the complete workflow of the project, including data preparation, exploratory data analysis, model training, evaluation, and interpretation of results.

telecomx_datos_tratados.csv  
This file contains the cleaned dataset produced during the first part of the challenge after preprocessing and correcting inconsistencies.

README.md  
This document explains the purpose of the project, methodology, models used, and the insights obtained.

## Dataset

The dataset contains customer information from Telecom X, including demographic characteristics, services subscribed, contract information, billing data, and customer churn status.

The data used in this project was previously cleaned and processed during the first part of the challenge. The cleaned dataset was exported as a CSV file and used as the input for the machine learning pipeline.

## Data Preparation

Before training the models, several preprocessing steps were applied to prepare the data for machine learning.

### Classification of Variables

The dataset contains both categorical and numerical variables.

Categorical variables include information such as gender, type of contract, internet service, payment method, and additional services subscribed by the customer.

Numerical variables include tenure, monthly charges, total charges, and a derived variable representing daily charges.

### Feature Engineering

Categorical variables were transformed into numerical format using One-Hot Encoding. This allows machine learning algorithms to properly interpret categorical information.

A new variable called Cuentas_Diarias was created to represent the estimated daily cost of the service based on the monthly billing.

Additionally, irrelevant columns such as customer identifiers were removed because they do not contribute to predicting churn and could introduce noise into the model.

## Train/Test Split

To evaluate the predictive performance of the models, the dataset was divided into training and testing subsets.

70% of the data was used for training the models and 30% was reserved for testing. This approach allows the models to learn patterns from the training data and then be evaluated using unseen data.

## Exploratory Data Analysis (EDA)

Before building the predictive models, I performed exploratory data analysis to understand the distribution of the variables and identify patterns related to churn.

Some of the analyses included examining the distribution of churn versus non-churn customers, analyzing how tenure relates to churn, and evaluating how billing variables such as monthly charges and total charges are associated with customer cancellation.

Visualization techniques such as boxplots, scatter plots, and correlation heatmaps were used to better understand the relationships between variables.

## Machine Learning Models

Two classification models were trained to predict customer churn.

### Logistic Regression

Logistic Regression is a linear model that estimates the probability that a customer will cancel their service based on the relationship between the input variables and the churn outcome.

This model is also useful for interpreting how individual variables contribute to the prediction.

### Random Forest

Random Forest is an ensemble model that combines multiple decision trees to improve predictive performance. It can capture complex relationships between variables and also provides a measure of feature importance.

## Model Evaluation

Both models were evaluated using common classification metrics including accuracy, precision, recall, F1-score, and confusion matrix.

These metrics help assess how well the models identify customers who are likely to cancel their services.

## Key Factors Influencing Churn

Based on the analysis of feature importance from the Random Forest model and the coefficients from Logistic Regression, several variables were identified as strong predictors of churn.

Some of the most relevant variables include total charges, customer tenure, monthly charges, estimated daily charges, fiber optic internet service, electronic check payment method, and paperless billing.

These results suggest that customer spending patterns, service configuration, and contract characteristics play an important role in predicting churn behavior.

## Strategic Insights

The analysis indicates that customers with shorter tenure are more likely to cancel their services. This suggests that the early stages of the customer lifecycle are critical for retention.

Billing structure and perceived service value may also influence churn decisions. Offering personalized service packages, loyalty incentives, or targeted promotions could help reduce churn risk.

Additionally, further analysis of customer experience in specific service segments could help identify opportunities to improve satisfaction and reduce cancellations.

## How to Run the Project

To reproduce this project, install the required libraries:

pip install pandas numpy matplotlib seaborn scikit-learn

Then open the notebook TelecomX_Churn_Prediction.ipynb and ensure that the dataset telecomx_datos_tratados.csv is located in the same directory. Run all cells in the notebook to reproduce the full analysis and model training.

## Conclusion

In this project, I applied machine learning techniques to predict customer churn and identify the main factors influencing cancellation behavior.

The results demonstrate how predictive modeling can support data-driven decision making and help companies design more effective customer retention strategies.

## Author

Marlon Crespo
