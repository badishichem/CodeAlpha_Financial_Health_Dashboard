# CodeAlpha_Financial_Health_Dashboard

## Project Overview

This project delivers a fully interactive Financial Health Dashboard built in Power BI as part of the CodeAlpha Data Analytics internship. The dashboard analyzes key financial indicators, including income, expenses, savings, loans, credit score, and financial ratios to assess the economic stability of individuals. It visualizes income statements, loan structures, debt-to-income risk levels, savings capacity, and demographic patterns through dynamic charts and KPIs. The solution enables users to explore trends, evaluate financial performance, and derive actionable insights for budgeting, risk assessment, and financial planning.

## Dashboard Preview
### Page One
![Page1 Overview](https://github.com/badishichem/CodeAlpha_Financial_Health_Dashboard/blob/main/Page%201%20Overview.png)
### Page Two
![Page1 Overview](https://github.com/badishichem/CodeAlpha_Financial_Health_Dashboard/blob/main/Page%202%20Overview.png)

## Dataset Details
**Dataset Name :** synthetic personal finance dataset
**Source:** Kaggle 
**File Type:** CSV 

### 📊 Columns Overview

| Column | Description |
|--------|-------------|
| **user_id** | Unique identifier for each user/applicant |
| **age** | Age of the individual |
| **gender** | Gender identity (Male, Female, Non-binary, etc.) |
| **education_level** | Highest level of education completed |
| **employment_status** | Employment type (Employed, Self-employed, Unemployed, etc.) |
| **job_title** | Specific job or occupation of the individual |
| **monthly_income_usd** | Monthly income in USD |
| **monthly_expenses_usd** | Total monthly spending in USD |
| **savings_usd** | Current amount of savings in USD |
| **has_loan** | Indicates if the user currently has a loan (Yes/No) |
| **loan_type** | Type of loan (Education, Personal, Business, Home, etc.) |
| **loan_amount_usd** | Total loan amount borrowed |
| **loan_term_months** | Duration of the loan in months |
| **monthly_emi_usd** | Monthly loan installment (EMI) in USD |
| **loan_interest_rate_pct** | Interest rate applied to the loan |
| **debt_to_income_ratio** | Percentage of debt compared to monthly income |
| **credit_score** | Financial credit score indicating creditworthiness |
| **savings_to_income_ratio** | Ratio of savings to income |
| **region** | Geographic region of the user (North America, Africa, Asia, etc.) |
| **record_date** | Date the financial record was captured |

## ⚙️ Data Cleaning & Transformation
- Removed duplicates and inconsistent records.
- Standardized data types (numeric, date, text).
- Formatted `record_date` to Date type.
- Cleaned categorical fields (employment_status, gender, loan_type, region, etc.).
- Added calculated columns:
  - **Debt_Category** based on debt_to_income_ratio (Low / Medium / High)
  - **Age_Group** (18–24, 25–34, 35–44, 45–54, 55-64 ,65+)  
  - **Loan_Flag** = 1 if has_loan = "Yes", else 0  
- Built DAX measures for KPIs:
  - `Average Income = AVERAGE(synthetic_personal_finance_dataset[monthly_income_usd])`
  - `Avg Credit Score = AVERAGE(synthetic_personal_finance_dataset[credit_score])`
  - `Total Expenses = SUM(synthetic_personal_finance_dataset[monthly_expenses_usd])`
  - `Users with loan = CALCULATE(COUNT(synthetic_personal_finance_dataset[user_id]), synthetic_personal_finance_dataset[has_loan] = "YES")`
### **1️⃣ KPI Overview**
- **Total Income:** 130,60M
- **Total Expenses:** 78.45M  
- **Average Credit Score:** 575,26 
- **Users with Loan:** 13k
- **Total Saving:** 7.90bn

### 2️⃣ Demographics & Income Insights

Horizontal Bar Chart – Income by Age Group
Shows that age groups 25–54 dominate total income (≈25M each), while 65+ earns the least (12M).

Filters (Slicers):
Debt Category, Loan Type, Employment Status, Savings Category, Region, Education Level, Age Group.

These help explore how income changes by age, education, and employment.

### 3️⃣ Financial Insights

Column Chart – Loan Amount by Debt Category
Highest loans are taken by users with High Debt Category, followed by Low and Medium.

Line Chart – Average Income vs Expenses over Record Date
Shows financial patterns over time (2022–2025), highlighting periods of high income and controlled expenses.

### 4️⃣ Employment Analysis

Pie Chart – Employment Status Distribution
Breakdown of Employed, Self-employed, Student, and Unemployed users.
Majority of users are Employed (≈60%), followed by Self-employed and Students.

### 5️⃣ Interactive Filters

The dashboard allows dynamic exploration with the following slicers:

Debt Category

Loan Type

Employment Status

Savings Category

Region

Education Level

Age Group

These filters make the dashboard fully interactive and suitable for decision-making.

### 📈 Analytical Findings

High Debt Category users take the largest loan amounts.

Employment status strongly influences financial behavior: Employed users dominate the dataset.

Income steadily increases after 2023, while expenses remain relatively stable.

Age groups 25–54 contribute the highest total income.

Savings remain high, showing strong financial capacity.

### 💡 Insights

High-debt users rely heavily on loans → need targeted financial planning.

Income peaks in middle-age groups → strong earning years.

Employed individuals show better financial stability.

No-debt users have negligible loan amounts → low risk for lending institutions.

### 🧭 Recommendations

Focus on high-debt customers for financial counseling or risk assessment.

Develop age-specific financial products for 25–54 group (highest earners).

Promote savings programs for younger age groups (18–24).

Monitor expenses vs income trends to detect financial stress early.

Target unemployed and student groups with controlled loan plans.

### 🧰 Tools Used

Power BI Desktop

Power Query

DAX Measures

CSV Dataset

### 📢 Key Takeaway

This dashboard provides a 360° view of financial health, helping analysts and decision-makers identify loan behaviors, debt risks, and income patterns across demographics. It can support lending strategies, risk assessment models, and long-term financial planning.

### 👩‍💻 Created by:
**Badis Hichem**  
_Data Analyst | Power BI | SQL | ETL | Python

