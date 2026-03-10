# telecomx-churn-prediction
Machine learning models to predict customer churn for Telecom X.

# Telecom X – Churn Prediction (Machine Learning)

## Project Overview

In this project, I developed a machine learning pipeline to predict customer churn for Telecom X. The goal of the project was to identify which customers are more likely to cancel their services and understand the factors that influence that decision.

This project is part of the Telecom X Data Science Challenge, where the objective is to move beyond exploratory data analysis and build predictive models that can help the company anticipate customer churn and design better retention strategies.

## Objectives

The main objectives of this project were:

- Prepare the dataset for machine learning modeling
- Transform categorical variables into numerical format
- Explore correlations between variables
- Train and evaluate classification models
- Identify the most important variables influencing churn
- Provide strategic insights based on the model results

## Dataset

The dataset contains information about Telecom X customers, including:

- Demographic information
- Contract details
- Services subscribed
- Billing and payment information
- Customer churn status

The dataset used in this project was previously cleaned and prepared in the first part of the Telecom X challenge.

## Technologies Used

The project was developed using the following tools and libraries:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## Data Preparation

Before training the models, I performed several preprocessing steps to prepare the data for machine learning:

- Removed columns that do not contribute to prediction, such as customer identifiers
- Converted categorical variables into numerical variables using one-hot encoding
- Evaluated the distribution of churn to understand class balance
- Explored correlations between variables
- Created a derived variable representing daily charges from the monthly billing

These steps ensured that the dataset was properly structured for predictive modeling.

## Machine Learning Models

To predict customer churn, I trained two different classification models:

### Logistic Regression

A linear model used to estimate the probability that a customer will cancel their service based on the relationship between the features and the churn variable.

### Random Forest

An ensemble model based on multiple decision trees that captures complex relationships in the data and provides a measure of feature importance.

## Model Evaluation

Both models were evaluated using common classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

These metrics allowed me to compare the models and evaluate how well they identify customers at risk of churn.

## Key Factors Influencing Churn

Based on the Random Forest feature importance and Logistic Regression coefficients, several variables showed strong influence on churn prediction.

Some of the most relevant factors include:

- Total charges (`Charges.Total`)
- Customer tenure (`tenure`)
- Monthly charges (`Charges.Monthly`)
- Estimated daily charges (`Cuentas_Diarias`)
- Fiber optic internet service
- Electronic check payment method
- Paperless billing

These variables suggest that both customer spending behavior and service configuration play an important role in the likelihood of churn.

## Strategic Insights

The analysis suggests that customers with shorter tenure tend to have a higher risk of canceling their services. This indicates that the first months of the customer lifecycle are critical for retention.

Billing structure and perceived service value may also influence churn decisions. Offering personalized plans, loyalty programs, or targeted promotions could help increase customer satisfaction and retention.

Additionally, certain service types and payment methods may reflect differences in the customer experience, which could be further investigated to improve service quality.

## Conclusion

In this project, I applied machine learning techniques to predict customer churn and identify the key factors influencing cancellation behavior.

The results demonstrate how predictive modeling can help companies anticipate churn risk and implement proactive retention strategies based on data-driven insights.

## Author

Marlon Crespo
