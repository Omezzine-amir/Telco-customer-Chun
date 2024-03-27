# Telco_customer_Churn_Prediction
""Machine Learning models for predicting customer churn using telecom data."

# Customer Churn Prediction Project

## Introduction

This project is dedicated to the development of machine learning models to predict customer churn in the telecom industry. The purpose of this predictive analysis is to identify customers who are likely to cancel their services and understand the key factors contributing to customer attrition. By doing so, we can develop targeted customer retention strategies and improve overall customer satisfaction.

## About the Dataset

The dataset used in this project is an IBM Sample Data Set, which provides a comprehensive view of customer demographics, service usage patterns, and account information. The dataset includes the following key columns:

- `customerID`: The unique identifier for the customer.
- `gender`: The customer’s gender (male/female).
- `SeniorCitizen`: Indicates if the customer is a senior citizen.
- `Partner`: Indicates if the customer has a partner.
- `Dependents`: Indicates if the customer has dependents.
- `tenure`: Number of months the customer has stayed with the company.
- `PhoneService`: Indicates if the customer has phone service.
- `MultipleLines`: Indicates if the customer has multiple lines.
- `InternetService`: Customer’s internet service provider (DSL, Fiber optic, etc.).
- `OnlineSecurity`: Indicates if the customer has online security services.
- `OnlineBackup`: Indicates if the customer has online backup services.
- `DeviceProtection`: Indicates if the customer has device protection services.
- `TechSupport`: Indicates if the customer has tech support services.
- `StreamingTV`: Indicates if the customer has streaming TV services.
- `StreamingMovies`: Indicates if the customer has streaming movies services.
- `Contract`: The term of the customer’s contract (Month-to-month, One year, Two year).
- `PaperlessBilling`: Indicates if the customer has paperless billing.
- `PaymentMethod`: The customer’s payment method.
- `MonthlyCharges`: The amount charged to the customer monthly.
- `TotalCharges`: The total amount charged to the customer.
- `Churn`: Indicates if the customer left within the last month.

## Context

In the competitive telecom industry, customer retention is as crucial as acquiring new customers. This dataset and the ensuing analysis offer insights into customer behavior and allow us to predict churn, which is vital for maintaining a strong customer base.

## Content

The project includes scripts for data preprocessing, exploratory data analysis, model training and evaluation, and predictions. It also includes Jupyter notebooks that provide a detailed walkthrough of the analyses and visualization of the data.

## Inspiration

The objective of this project is to apply machine learning techniques to real-world data and gain a deeper understanding of the factors that influence customer churn. Insights from this project can help telecom companies to tailor their marketing and customer service efforts more effectively.


## Requirements

The following libraries are required to run the code in this repository:

- R:
  - `tidyverse`
  - `caret`
  - `randomForest`
  - `e1071`
  - `ggplot2`

Install these packages in R using the command `install.packages(c("tidyverse", "caret", "randomForest", "e1071", "ggplot2"))`.
## EDA 
The dataset comprises 7,043 customers from a telecom company, providing a rich set of characteristics including demographic information, services subscribed to, account details, and churn status. A preliminary exploration reveals several noteworthy observations:

1) Demographics and Account Information: The customer base shows a near-even split between genders and a relatively small proportion of senior citizens (16.21%). Interestingly, there is almost an equal distribution of customers with and without partners, but a larger number do not have dependents (70.04% without dependents).

2) Service Subscription: A significant majority (90.31%) have phone services, yet the dataset indicates a diverse range of service subscriptions such as multiple lines, internet services, online security, backup, device protection, tech support, streaming TV, and movies. This diversity suggests varied customer preferences and needs regarding the telecom services offered.

3) Tenure, Charges, and Churn: Tenure among customers ranges from new subscribers (0 months) to long-term customers (up to 72 months), with a median tenure of 29 months. This variability indicates a mix of customer loyalty and potential market penetration opportunities. Monthly charges span from $18.25 to $118.75, reflecting the wide range of service plans customers subscribe to. Despite the breadth of services and tenure, the company faces a churn rate of 26.54%, highlighting the importance of targeted customer retention strategies.

4) Billing and Payments: Over half of the customers (59.22%) have adopted paperless billing, suggesting a notable trend towards digital service management. The variety in payment methods further characterizes the customer base, pointing to differing preferences in managing financial transactions with the telecom provider.

   
   <img width="915" alt="image" src="https://github.com/Omezzine-amir/Telco-customer-Churn/assets/165148422/455dde0c-8ce5-47db-90ca-6dc7a3d8c22c">
==> The visualization presents a jitter plot that illustrates the distribution of customer tenure across different contract types, with a separate plot for each category of Senior Citizen status (0 (Non Senior) or 1(Senior)), and points colored to represent churn status (Yes or No).

From the plot, we can deduce:

Tenure Distribution: There is a wide range of tenure lengths across all contract types. Month-to-month contracts appear to have a broader distribution of tenure, indicating a mix of new and long-term customers. In contrast, one-year and two-year contracts seem to attract customers who stay for longer periods, as indicated by the clustering of points toward the higher end of the tenure axis.

- Churn by Contract Type: Churn (marked in red) is visibly more prevalent in month-to-month contracts, particularly among non-senior citizens. This suggests that customers with shorter, more flexible contracts are more likely to churn than those with longer commitments.

- Impact of Senior Citizen Status: The top and bottom rows differentiate between non-senior citizens (0) and senior citizens (1). For both groups, month-to-month contracts show higher churn, but the effect is more pronounced for non-senior citizens. One-year and two-year contracts have lower churn rates, which holds true for both seniors and non-seniors.

- Senior Citizens: Senior citizens (1) have a visibly smaller sample size compared to non-senior citizens (0), as seen by the fewer points in the plots for senior citizens. The distribution of tenure for senior citizens appears more uniform across contract types when compared to non-senior citizens.

- Churn Color Representation: The red points, indicating churn, are interspersed throughout, but they are most noticeable in the month-to-month contract facet for non-senior citizens, suggesting that churn is a significant issue in this segment.
- 
![Chart 2](https://github.com/Omezzine-amir/Telco-customer-Churn/assets/165148422/afe0206f-20ae-4d27-a37f-780e2505835f)

