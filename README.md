# Customer Churn & Retention Analytics

An end-to-end data analytics project using **Python, Pandas, and Power BI** to analyze customer churn, identify key churn drivers, build a customer risk scoring framework, and develop actionable retention strategies.

---

## Project Overview

Customer churn is a major challenge for subscription-based businesses. Understanding why customers leave and identifying customers who are most likely to churn can help businesses take proactive steps to improve customer retention.

This project analyzes a telecom customer dataset containing **7,043 customers** and **21 features** to uncover patterns associated with customer churn.

The project follows an end-to-end analytics workflow:

**Data Cleaning → Exploratory Data Analysis → Churn Analysis → Risk Scoring → Customer Segmentation → Power BI Dashboard → Business Recommendations**

The analysis was performed using **Python and Pandas**, while **Power BI** was used to create an interactive business dashboard for exploring churn patterns and high-risk customer segments.

---

## Project Objectives

The main objectives of this project were to:

- Understand the overall customer churn rate
- Identify key factors associated with customer churn
- Analyze churn across different customer segments
- Compare churn rates by contract type and customer tenure
- Investigate the relationship between services and churn
- Identify high-risk customer characteristics
- Develop a rule-based customer risk scoring framework
- Segment customers into Low, Medium, and High Risk categories
- Build an interactive Power BI dashboard
- Generate actionable recommendations to improve customer retention

---

## Tools & Technologies

- **Python** — Data analysis and exploratory analysis
- **Pandas** — Data cleaning and manipulation
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Jupyter Notebook** — Python analysis environment
- **Power BI** — Interactive dashboard and business visualization
- **GitHub** — Project documentation and version control

---

## Dataset

The dataset contains information about **7,043 telecom customers** across **21 columns**.

### Key Features

| Category | Features |
|---|---|
| Customer Information | Customer ID, Gender, Senior Citizen, Partner, Dependents |
| Customer Relationship | Tenure, Contract |
| Services | Phone Service, Multiple Lines, Internet Service |
| Additional Services | Online Security, Online Backup, Device Protection, Tech Support |
| Entertainment | Streaming TV, Streaming Movies |
| Billing | Paperless Billing, Payment Method |
| Financial | Monthly Charges, Total Charges |
| Target Variable | Churn |

The target variable, **Churn**, indicates whether a customer has left the company.

---

## Data Cleaning & Preparation

The dataset was inspected and prepared using Python and Pandas.

### Key data preparation steps included:

- Loaded the dataset into a Pandas DataFrame
- Inspected the first few records
- Checked the dataset shape and column names
- Examined data types using DataFrame information
- Checked for missing values
- Identified blank values in the `TotalCharges` column
- Converted `TotalCharges` from string to numeric format
- Handled missing `TotalCharges` values
- Checked for duplicate records
- Verified the final dataset structure
- Created customer tenure groups for analysis

The final dataset contained **7,043 customer records**.

---

# Python Analysis

Exploratory data analysis was performed using Python, Pandas, NumPy, and Matplotlib.

The analysis focused on identifying customer segments and characteristics associated with higher churn risk.

---

## 1. Churn Rate by Contract Type

Contract type was found to be one of the strongest churn indicators.

| Contract Type | Churn Rate |
|---|---:|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

Customers on month-to-month contracts showed significantly higher churn compared with customers on longer-term contracts.

![Churn Rate by Contract](screenshots/tenure_churn.png)

---

## 2. Churn Rate by Customer Tenure

Newer customers were more likely to churn than long-term customers.

| Tenure Group | Churn Rate |
|---|---:|
| 0–12 Months | 47.44% |
| 13–24 Months | 28.71% |
| 25–48 Months | 20.39% |
| 49–72 Months | 9.51% |

The highest churn occurred among customers in their first year.

![Churn Rate by Tenure](screenshots/tenure_churn.png)

---

## 3. Average Monthly Charges by Churn Status

Customers who churned had higher average monthly charges than customers who stayed.

| Churn Status | Average Monthly Charges |
|---|---:|
| No | $61.27 |
| Yes | $74.44 |

This suggests that higher monthly charges may be associated with increased churn risk.

![Average Monthly Charges by Churn](screenshots/monthly_charges_churn.png)

---

## 4. Churn Rate by Internet Service

Internet service type showed differences in churn behavior.

| Internet Service | Churn Rate |
|---|---:|
| DSL | 18.96% |
| Fiber optic | 41.89% |
| No internet service | 7.40% |

Fiber optic customers showed a significantly higher churn rate than DSL customers.

![Churn Rate by Internet Service](screenshots/internet_service_churn.png)

---

## 5. Churn Rate by Payment Method

Electronic check users had the highest churn rate among payment methods.

| Payment Method | Churn Rate |
|---|---:|
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |
| Electronic check | 45.29% |
| Mailed check | 19.11% |

![Churn Rate by Payment Method](screenshots/payment_method_churn.png)

---

## 6. Churn Rate by Tech Support

Customers without Tech Support showed substantially higher churn.

| Tech Support | Churn Rate |
|---|---:|
| No | 41.64% |
| No internet service | 7.40% |
| Yes | 15.17% |

![Churn Rate by Tech Support](screenshots/tech_support_churn.png)

---

## 7. Churn Rate by Online Security

Customers without Online Security also showed significantly higher churn.

| Online Security | Churn Rate |
|---|---:|
| No | 41.77% |
| No internet service | 7.40% |
| Yes | 14.61% |

![Churn Rate by Online Security](screenshots/online_security_churn.png)

---

# Customer Risk Scoring

To identify customers who may require proactive retention efforts, a rule-based risk scoring framework was developed.

Customers received risk points based on characteristics associated with higher churn rates.

### Risk Factors

- Month-to-month contract
- Fiber optic internet service
- Electronic check payment method
- No Tech Support
- No Online Security
- New customer / short tenure

Each applicable risk factor contributed to the customer's overall **Risk Score**.

Customers were then grouped into three risk categories:

- 🟢 **Low Risk**
- 🟡 **Medium Risk**
- 🔴 **High Risk**

---

## Risk Score and Churn

A strong relationship was observed between Risk Score and churn.

| Risk Score | Churn Rate |
|---:|---:|
| 0 | 1.92% |
| 1 | 6.28% |
| 2 | 15.05% |
| 3 | 23.00% |
| 4 | 40.02% |
| 5 | 58.13% |
| 6 | 74.45% |

As the number of risk factors increased, the likelihood of customer churn increased substantially.

![Churn Rate by Risk Score](screenshots/risk_score_churn.png)

---

## Customer Risk Categories

The customer base was segmented into three risk categories.

| Risk Category | Customers | Monthly Charges | Churn Rate |
|---|---:|---:|---:|
| High Risk | 2,567 | $197,757.70 | 53.95% |
| Medium Risk | 2,135 | $141,408.65 | 18.55% |
| Low Risk | 2,341 | $116,950.25 | 3.76% |

High-risk customers represented the most critical segment for proactive retention efforts.

![Churn Rate by Risk Category](screenshots/risk_category_churn.png)

---

# Power BI Dashboard

An interactive Power BI dashboard was created to provide a consolidated view of customer churn and retention patterns.

The dashboard allows users to explore customer churn using interactive filters for:

- **Contract Type**
- **Internet Service**
- **Risk Category**

### Dashboard KPIs

The dashboard includes:

- **Total Customers:** 7,043
- **Churned Customers:** 1,869
- **Overall Churn Rate:** 26.54%

### Dashboard Visualizations

The dashboard includes:

- Churn Rate by Contract
- Churn Rate by Tenure
- Churn Rate by Internet Service
- Churn Rate by Payment Method
- Churn Rate by Risk Score
- Churn Rate by Risk Category
- Monthly Charges by Customer Risk Category

### Dashboard Preview

![Customer Churn & Retention Power BI Dashboard](screenshots/Customer_Churn_Retention_dashboard.png)

---

# Key Findings

The analysis identified several important churn patterns:

### 1. Overall Churn

The overall customer churn rate was **26.54%**, with **1,869 out of 7,043 customers** having churned.

### 2. Contract Type

Month-to-month customers had a churn rate of **42.71%**, significantly higher than customers on one-year or two-year contracts.

### 3. Customer Tenure

Customers with **0–12 months of tenure** had the highest churn rate at **47.44%**.

### 4. Internet Service

Fiber optic customers had a churn rate of **41.89%**, considerably higher than DSL customers at **18.96%**.

### 5. Payment Method

Electronic check users had the highest churn rate among payment methods at **45.29%**.

### 6. Additional Services

Customers without Tech Support or Online Security showed significantly higher churn rates than customers who subscribed to these services.

### 7. Risk Score

Churn increased sharply as Risk Score increased.

Customers with a Risk Score of **6** had a churn rate of approximately **74.45%**, compared with only **1.92%** for customers with a Risk Score of 0.

### 8. Risk Category

High-risk customers had a churn rate of **53.95%**, compared with only **3.76%** for low-risk customers.

---

# Business Recommendations

Based on the analysis, the following strategies could help reduce customer churn:

### 1. Target Month-to-Month Customers

Develop personalized retention campaigns and incentives to encourage month-to-month customers to move to longer-term contracts.

### 2. Strengthen New Customer Onboarding

Focus on the first 12 months of the customer lifecycle, when churn risk is highest.

### 3. Investigate Fiber Optic Customer Churn

Analyze potential pricing, service quality, and customer satisfaction issues among fiber optic customers.

### 4. Encourage Long-Term Contracts

Offer incentives or loyalty benefits to customers who switch from month-to-month contracts to one-year or two-year plans.

### 5. Promote Value-Added Services

Encourage customers to adopt Tech Support and Online Security services, which are associated with lower churn rates.

### 6. Prioritize High-Risk Customers

Use the risk scoring framework to identify customers who are most likely to churn and prioritize them for proactive retention campaigns.

### 7. Implement Risk-Based Retention

Instead of applying the same retention strategy to every customer, use risk categories to allocate retention resources more efficiently.

---

# Project Outcome

This project demonstrates an end-to-end data analytics workflow:

**Data Collection & Loading**  
↓  
**Data Cleaning & Preparation**  
↓  
**Exploratory Data Analysis**  
↓  
**Customer Churn Analysis**  
↓  
**Risk Factor Identification**  
↓  
**Customer Risk Scoring**  
↓  
**Customer Segmentation**  
↓  
**Interactive Power BI Dashboard**  
↓  
**Business Insights & Recommendations**

The project combines technical data analysis with business-focused problem solving to identify customers at risk of churn and recommend data-driven retention strategies.

---

# Project Structure

```text
Customer-Churn-Retention-Analytics/
│
├── data/
│   └── customer_churn.csv
│
├── python/
│   └── customer_churn_analysis.ipynb
│
├── powerbi/
│   └── Customer_Churn_Retention_Analytics.pbix
│
├── screenshots/
│   ├── Customer_Churn_Retention_dashboard.png
│   ├── churn_distribution.png
│   ├── contract_churn.png
│   ├── tenure_churn.png
│   ├── monthly_charges_churn.png
│   ├── internet_service_churn.png
│   ├── payment_method_churn.png
│   ├── contract_internet_churn.png
│   ├── tech_support_churn.png
│   ├── online_security_churn.png
│   ├── risk_score_churn.png
│   └── risk_category_churn.png
│
└── README.md
```

---

# Author

**indupalli jayasri **
---
