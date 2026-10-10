# Insurance Customer Analytics Dashboard

## Project Overview

This project analyzes insurance policy, premium, coverage, claim, and customer-feedback data to provide a consolidated view of insurance business performance and customer experience.

The project combines **Microsoft SQL Server, Power BI, and Excel** to explore policy-level data, claim status, premium and coverage amounts, customer demographics, policy types, and customer feedback sentiment.

The Power BI report contains an executive-style dashboard, detailed policy-level records, and a separate customer-feedback analysis page.

---

## Business Problem

Insurance companies need to understand how their policies and claims are performing while also tracking customer experience.

This project focuses on questions such as:

- How much premium and coverage value is represented in the portfolio?
- How are claims distributed across different claim statuses?
- Which policy types contribute the most premium and coverage?
- How does claim value vary across customer age groups?
- What is the distribution of active and inactive policies?
- What patterns can be identified from customer feedback?
- Which areas of the customer experience appear positive and which may require improvement?

---

## Project Objectives

- Analyze insurance policy and customer-level information.
- Track total premium, coverage, and claim amounts.
- Understand claim-status distribution.
- Compare performance across insurance policy types.
- Analyze customer demographics such as gender and age groups.
- Monitor active/inactive policy distribution.
- Analyze customer feedback and sentiment scores.
- Build an interactive Power BI dashboard for business reporting.

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Source data and customer feedback data |
| **Microsoft SQL Server** | Database creation, data loading, inspection, and SQL analysis |
| **Power BI Desktop** | Dashboard development and interactive analysis |
| **DAX / Power BI calculations** | Aggregations and calculated fields used in the report |
| **Power BI Custom Visuals** | Customer-feedback word cloud |

---

## Dataset

### Insurance Policy Dataset

The main dataset contains **10,004 records and 13 columns**.

Key fields include:

- `PolicyNumber`
- `CustomerID`
- `Gender`
- `Age`
- `PolicyType`
- `PolicyStartDate`
- `PolicyEndDate`
- `PremiumAmount`
- `CoverageAmount`
- `ClaimNumber`
- `ClaimDate`
- `ClaimAmount`
- `ClaimStatus`

The dataset contains five policy types:

- Travel
- Health
- Auto
- Life
- Home

Claim statuses include:

- Settled
- Pending
- Rejected

### Customer Feedback Dataset

The customer-feedback workbook contains **97 feedback records** with:

- Customer Name
- Feedback
- Score sentiment

The Power BI feedback analysis also includes a **Good/Improvement** categorization and visual analysis of customer comments.

---

## Project Workflow

```text
Excel / CSV Data
       ↓
Microsoft SQL Server
       ↓
Data Inspection & SQL Analysis
       ↓
Power BI Desktop
       ↓
Dashboard & Interactive Visualizations
       ↓
Customer Feedback & Sentiment Analysis
```

---

# SQL Server Analysis

A SQL Server database named `Insurancedb` was created for the insurance dataset.

The SQL script includes database setup and basic data inspection, including:

```sql
CREATE DATABASE Insurancedb;
USE Insurancedb;

SELECT *
FROM [dbo].[InsuranceData];

SELECT COUNT(PolicyNumber)
FROM [dbo].[InsuranceData];
```

SQL was used to work with the insurance data before connecting it to the Power BI reporting layer.

---

# Power BI Dashboard

The main Power BI dashboard provides a high-level overview of the insurance portfolio.
<img width="1442" height="797" alt="Image" src="https://github.com/user-attachments/assets/0b8599ac-42c8-4068-a910-7d90b0d5b026" />

### KPI Cards

The dashboard tracks:

- **Total Premium Amount**
- **Total Coverage Amount**
- **Total Claim Amount**

### Main Visualizations

The report includes:

- Gender-wise customer/policy distribution
- Claim Status distribution
- Premium Amount by Policy Type
- Claim Amount by Age Group
- Active vs Inactive policies
- Coverage Amount by Policy Type and Claim Status
- Detailed policy-level table

### Interactive Filters

The dashboard includes slicers for:

- Policy Number
- Customer ID
- Claim Number

This allows users to move from portfolio-level analysis to individual policy or claim records.

---

# Customer Feedback Analysis

A separate Power BI page analyzes customer feedback using the feedback dataset.

The page includes:

- **Word Cloud** of customer comments
- **Good/Improvement** feedback categorization
- Customer-level feedback table
- Sentiment score for each feedback record

This section helps connect quantitative insurance performance with qualitative customer experience.

---

# Key Findings

Based on the uploaded insurance dataset:

### Portfolio Overview

- The dataset contains **10,004 insurance records**.
- Total premium represented in the dataset is approximately **5.98 million**.
- Total coverage represented is approximately **600.55 million**.
- Total claim amount is approximately **16.91 million**.

### Policy Type

- **Travel** is the largest policy category with **4,148 records**, followed by Health with 2,000 records.
- Travel policies also contribute the highest total premium and coverage among the five policy types in the dataset.

### Claim Status

- **Rejected:** 4,355 records (~43.5%)
- **Settled:** 3,386 records (~33.8%)
- **Pending:** 2,263 records (~22.6%)

The claim-status distribution provides a useful view of the current state of claims across the portfolio.

### Claim Amount

- **5,649 records** have a claim amount greater than zero, while 4,355 records have a claim amount of zero.
- Settled claims account for approximately **10.11 million** in claim amount.
- Pending claims account for approximately **6.81 million** in claim amount.
- Rejected records have zero claim amount in the supplied dataset.

### Customer Feedback

- The feedback dataset contains **97 customer comments**.
- The average sentiment score is approximately **0.693**.
- **75 of 97** feedback records have sentiment scores above 0.5.
- Feedback comments include positive experiences around service, coverage, claims, and digital channels, while improvement-oriented comments mention areas such as response time, claim processing, policy clarity, and customer support.

> **Note:** These findings are descriptive observations from the supplied dataset. They should not be interpreted as causal relationships or predictions about future insurance performance.

---

# Conclusion

The analysis provides an integrated view of insurance portfolio value, claims, policy types, customer demographics, and customer feedback. The dataset shows Travel as the largest policy category, while claim-status analysis highlights a substantial volume of rejected and pending claims. Customer feedback is generally positive based on the supplied sentiment scores, but recurring comments point to opportunities around claim processing, response time, policy clarity, and customer support. Overall, the project demonstrates how SQL and Power BI can be combined to turn insurance data into business-focused insights.

---


#  How to Use

### 1. Download the project files

Clone or download this repository.

### 2. Set up SQL Server

Run `Insurance.sql` in Microsoft SQL Server Management Studio to create the database and inspect the insurance table.

### 3. Open the Power BI file

Open:

```text
powerbi/Insurance.pbix
```

### 4. Review the dashboard

Use the available slicers and visuals to explore policy, premium, coverage, claim, demographic, and feedback information.

---

# Data & Privacy Note

The project uses a dataset prepared for analytics and portfolio purposes. No real customer credentials, passwords, or sensitive authentication information are included in the project files.

---

---

## Author

**Harsh Negi**  
Aspiring Data Analyst


