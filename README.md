# SaaS Customer Churn Prediction

## Project Overview

This project analyzes customer churn risk for a simulated SaaS business using Python and machine learning.

The analysis covers data cleaning, exploratory data analysis, feature engineering, machine learning model development, model evaluation, and identification of customers with elevated churn risk.

## Business Objective

The primary objective is to identify customers with elevated churn risk and provide evidence-based insights that can help prioritize customer retention efforts.

## Business Question

**Which customers are most likely to churn, and what customer characteristics are associated with churn risk?**

## Dataset

The dataset contains 500 SaaS customer accounts and includes:

- Account information
- Industry
- Country
- Signup date
- Referral source
- Plan tier
- Number of seats
- Trial status
- Churn status

Target variable:

- `churn_flag`

Overall observed churn rate: **22%**

## Data Preparation

The data preparation process included:

- Checking for missing values
- Checking for duplicate records
- Validating categorical values
- Converting `signup_date` to datetime
- Validating seat values
- Creating time-based features
- Creating customer tenure in days
- Preparing categorical and numerical features for machine learning

## Exploratory Data Analysis

The analysis examined churn patterns across:

- Industry
- Country
- Plan tier
- Trial status
- Customer seats
- Signup year

Some observed differences were identified across industries and countries, while plan-tier churn rates were very similar.

## Feature Engineering

Additional features were created to improve the model:

- `signup_year`
- `signup_month`
- `signup_day`
- `tenure_days`

The analytical reference date for tenure calculations was **2024-12-31**.

## Machine Learning Models

Two classification models were developed:

1. Logistic Regression
2. Random Forest Classifier

The models were evaluated using:

- Accuracy
- Precision
- Recall
- Confusion matrix

Because the business objective is to identify customers who may churn, **recall is an important evaluation metric**.

## Model Results

| Model | Accuracy | Precision | Recall |
|---|---:|---:|---:|
| Logistic Regression | 79.0% | 66.7% | 9.1% |
| Random Forest | 79.0% | 60.0% | 13.6% |

The models produced similar accuracy, while the Random Forest identified a larger proportion of actual churners in the test set.

## High-Risk Customer Identification

The Random Forest model was used to estimate churn probabilities for customers in the test set.

Five customers had predicted churn probabilities of **50% or higher**.

These predictions should be treated as **risk signals rather than guarantees of future churn**.

## Business Recommendations

Based on the analysis:

- Prioritize high-risk accounts for retention review.
- Investigate customer usage and engagement data.
- Incorporate support-ticket and customer-feedback data into future analysis.
- Consider customer value or MRR when prioritizing retention resources.
- Continue monitoring model performance as new customer data becomes available.

## Limitations

This project has several limitations:

- The dataset is simulated.
- No MRR, ARR, or customer lifetime value data is available.
- No detailed product-usage or engagement data is available.
- The analysis does not establish causal relationships.
- The churn model is based on a relatively small dataset.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- GitHub

## Project Structure

```text
saas-churn-prediction/
├── data/
│   └── ravenstack_accounts.csv
├── notebooks/
│   └── SaaS_Churn_Prediction.ipynb
└── README.md
