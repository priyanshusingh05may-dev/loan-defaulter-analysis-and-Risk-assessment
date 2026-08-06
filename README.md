#  Loan Defaulter Analysis 

A comprehensive exploratory data analysis (EDA) and analytical case study conducted on a financial dataset to evaluate loan application risks,
identify default indicators, and optimize approval strategies for financial institutions.

This repository features complete end-to-end solutions built using **Python** (Pandas, Seaborn, Matplotlib) and **Excel**.

---

##  Table of Contents
- [Background & Problem Statement](#-background--problem-statement)
- [Dataset Architecture](#-dataset-architecture)
- [Key Business Insights & Findings](#-key-business-insights--findings)
- [Repository Structure](#-repository-structure)
- [Solutions & Analysis Walkthrough](#-solutions--analysis-walkthrough)
  - [Basic Analysis](#1-basic-level-questions)
  - [Medium-Level Insights](#2-medium-level-questions)
  - [Advanced Anomaly & Risk Detection](#3-advanced-level-questions)
- [Getting Started](#-getting-started)

---

##  Background & Problem Statement

### **What is the problem?**
Financial institutions need to evaluate borrower risk dynamically. Understanding the key factors affecting loan approval statuses and potential defaults
helps underwriters create smarter, data-driven approval framework.

### **Why solve it?**
- **Risk Mitigation:** Lower non-performing asset (NPA) rates by spotlighting high-risk applicant profiles.
- **Profit Optimization:** Tailor interest rates, terms, and collateral constraints accurately.
- **Efficiency:** Streamline manual approval processes using automated risk factors.

---

##  Dataset Architecture

* **Source:** [Kaggle - Deloitte Hackathon: Predict the Loan Defaulter](https://www.kaggle.com/datasets/manishtripathi86/deloitte-hackathon-predict-the-loan-defaulter?select=train.csv)
* **Dataset Size:** 67464 records × 35 features

### **Data Dictionary**

| Feature | Description |
| :--- | :--- |
| `ID` | Unique representative ID |
| `Loan Amount` | Loan amount requested |
| `Funded Amount` | Loan amount funded |
| `Funded Amount Investor` | Amount approved by investors |
| `Term` | Loan duration (in months) |
| `Interest Rate` | Annual interest rate (%) |
| `Grade` / `Sub Grade` | Internal credit risk tiers assigned by bank |
| `Employment Duration` | Employment status/length (e.g., MORTGAGE, RENT, OWN) |
| `Home Ownership` | Property ownership status |
| `Verification Status` | Income verification status |
| `Debit to Income` | Monthly debt repayment divided by monthly income (DTI) |
| `Delinquency - two years` | 30+ days overdue occurrences in past 2 years |
| `Public Record` | Number of derogatory public records |
| `Revolving Balance` | Total credit revolving balance |
| `Revolving Utilities` | Ratio of credit used vs. revolving limit |
| `Total Revolving Credit Limit`| Total revolving credit limit |
| `Loan Status` | **Target variable** (`1` = Defaulter, `0` = Non-Defaulter) |

---

##  Key Business Insights & Findings

1. **Defaulter Rate Baseline:** ~9.25% of total applicants defaulted (`Loan Status = 1`).
2. **Investor Disconnect:** `Funded Amount Investor` shows low linear correlation ($r \approx 0.003$) with `Loan Amount`. Investor allocations are driven
3. more heavily by holistic risk profiles rather than base applicant request size.
4. **Over-Funding Behavior:** The mean funding ratio (`Funded Amount / Loan Amount`) is $\sim136.47\%$ for
5. non-defaulters vs. $\sim140.39\%$ for defaulters, indicating that loans funded beyond original applicant requests correlate slightly higher with default behavior.
6. **Interest Rate Integrity:** Statistical outlier detection ($\vert{}Z\vert{} > 3$) flagged **321
7. anomalous interest rate records**, where high-tier grades (Grade A/B) were assigned unexpectedly high interest rates ($>23\%$).

---

##  Repository Structure

```text
├── loan defaulter analysis.xlsx   # Full analytical model, pivot tables, formulas & charts
├── loan_defaulter_analysis.ipynb  # Interactive Python notebook with statistical analysis
└── README.md                       # Documentation & Case Study Brief
