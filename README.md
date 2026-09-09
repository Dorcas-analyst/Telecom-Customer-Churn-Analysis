# Telecom-Customer-Churn-Analysis
The project demonstrates an end-to-end analytics workflow that converts raw customer data into a decision-ready BI solution. It also highlights the importance of validating dashboard calculations and relationships rather than assuming that technically successful transformations automatically produce accurate analytical results.
**An End-to-End ETL & Business Intelligence Project Using PostgreSQL and Power BI**

### 📌 Project Overview
This project analyzes telecom customer churn through an end-to-end PostgreSQL ETL and Power BI Business Intelligence workflow. The raw customer dataset was loaded into PostgreSQL, audited for data-quality issues, cleaned and transformed into production and reporting views, and then connected to Power BI for interactive analysis.

### 🎯 Objectives
* Analyze customer churn patterns.
* Identify high-risk customer segments.
* Perform SQL-based data-quality auditing.
* Clean and transform raw customer data.
* Build reporting views in PostgreSQL.
* Create DAX measures and KPIs.
* Develop an interactive Power BI dashboard.
* Generate data-driven customer retention recommendations.

### 🛠️ Tools & Technologies

* PostgreSQL
* SQL
* Microsoft Power BI
* Power Query
* DAX

### 🔄 ETL Workflow

```text
Raw CSV
   ↓
PostgreSQL Staging Table
   ↓
Data Quality & NULL Audit
   ↓
Data Cleaning with COALESCE
   ↓
Production Table
   ↓
Reporting Views
   ↓
Power Query Transformations
   ↓
DAX Measures
   ↓
Power BI Dashboard
   ↓
Business Insights
```

### 📈 Core DAX Measures

```DAX
Total Customers =
COUNT(prod_Churn[Customer_ID])

New Joiners =
CALCULATE(
    COUNT(prod_Churn[Customer_ID]),
    prod_Churn[Customer_Status] = "Joined"
)

Total Churn =
SUM(prod_Churn[Churn Status])

Churn Rate =
[Total Churn] / [Total Customers]
```

### 🔎 Key Results
| KPI             | Result |
| --------------- | -----: |
| Total Customers |  6,418 |
| New Joiners     |    411 |
| Total Churn     |  1,732 |
| Churn Rate      |  27.0% |

### 💡 Key Insights
* Month-to-Month customers recorded **46.5% churn**, compared with **2.7%** for Two-Year contracts.
* Mailed Check customers recorded **37.8% churn**, compared with **14.8%** for Credit Card customers.
* Fiber Optic customers recorded **41.1% churn**.
* Jammu & Kashmir recorded the highest state-level churn rate at **57.2%**.
* Competitor-related churn represented approximately **44%** of all churn.
* Attitude and Dissatisfaction together represented approximately **35%** of churn.

### 📊 Dashboard Analysis
The Power BI dashboard analyzes churn across:
* Demographics
* Account information
* Geography
* Contract type
* Payment method
* Service usage
* Churn categories
* Churn reasons

### 🧪 Data Validation
An important part of this project was validating the dashboard after implementation. The report identified issues with the Age Group, Tenure Group, and Services visuals. The Age and Tenure charts were not correctly slicing the underlying data, while the Services matrix required correction to its percentage calculation.

These issues reinforced an important analytics principle:
> **Successful code execution does not necessarily mean correct analytical output.**

### 📌 Business Recommendations
Based on the analysis:
1. Encourage longer-term contract adoption.
2. Investigate high churn among non-credit-card payment users.
3. Prioritize Fiber Optic customer retention.
4. Investigate unusually high churn in specific geographic regions.
5. Conduct competitive pricing and plan analysis.
6. Strengthen customer-service and complaint-resolution processes.

### ⚠️ Project Scope
This implementation covers the **SQL/ETL and Power BI portions** of the original project. The Machine Learning/churn-prediction component was intentionally not implemented.

### 🙏 Original Project Credit
The project design, dataset structure, dashboard specification, and analytical methodology were adapted from **PivotalStats'** YouTube tutorial:
**“PowerBI End to End Churn Analysis Portfolio Project | Power BI + SQL + Machine Learning | 2024.”**

This repository represents an independent implementation that:
* Uses **PostgreSQL instead of Microsoft SQL Server**.
* Covers the **SQL/ETL and Power BI components**.
* Does **not** implement the original tutorial's Machine Learning phase.

Full credit is given to PivotalStats for the original project design and analytical approach.
