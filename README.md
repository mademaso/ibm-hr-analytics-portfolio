# IBM HR Analytics and Attrition Study

<p align="center">
  <img src="assets/ibm-logo.png" alt="IBM Logo" width="150"/>
</p>

**Author:** [Matteo De Maso](https://www.linkedin.com/in/mademaso) | [Contact Email](mailto:mademaso@outlook.com)

An independent HR analytics project using the IBM HR Analytics Employee Attrition and Performance dataset from Kaggle. The project uses **Excel** to clean and organize employee data and **Tableau Public** to explore patterns in employee attrition.

**[View Executive Overview Dashboard](https://public.tableau.com/views/executive-overview_17907232274830/HREmployeeDataOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** | **[View Sales Representatives Deep-Dive](https://public.tableau.com/views/sales-representatives-deep-dive/SalesRepresentativesDeep-Dive?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## Project Overview

The goal of this project was to practice using workforce data to identify patterns in employee attrition and explore potential areas for further investigation.

The project included:

- Cleaning and organizing **1,470 employee records** in Excel
- Creating a data dictionary to make coded fields easier to understand
- Using Excel formulas such as `IF` and `XLOOKUP` to prepare the data
- Building two interactive dashboards in Tableau Public
- Exploring attrition by department, job role, monthly income, overtime, and tenure
- Developing potential retention recommendations based on the findings

---

## Tools

- **Microsoft Excel** — Data cleaning, organization, formulas, and data preparation
- **Tableau Public** — Data visualization and interactive dashboards
- **GitHub** — Project organization and documentation

---

## Key Findings

### Overall Workforce

- The dataset contains **1,470 employees**.
- Overall attrition is **16.12%**.
- Sales has the highest department-level attrition at **20.63%**.

### Sales Representatives

Sales Representatives had an attrition rate of **39.76%**, making the role a notable area for further investigation.

The analysis found several patterns:

- Sales Representatives with lower monthly income had higher attrition rates.
- Sales Representatives working overtime had substantially higher attrition.
- Attrition was highest among employees with shorter tenure.

For example, attrition among Sales Representatives was **57.14% for employees with less than one year at the company**, compared with **23.81% among employees with more than three years**.

These findings suggest areas that could be explored further, including compensation, workload, and early-career retention.

---

## Dashboards

### 1. Executive Overview

Provides a high-level view of the workforce, including:

- Total headcount
- Overall attrition rate
- Average monthly income
- Average years at the company
- Attrition by department
- Attrition by job role

### 2. Sales Representatives Deep-Dive

Focuses on the Sales Representative role and explores:

- Attrition by monthly income bracket
- Attrition by overtime status
- Attrition by tenure

---

## Project Structure

```text
├── assets/
│   └── ibm-logo.png
│
├── dashboards/
│   └── ibm-hr-attrition-dashboards.twbx
│
├── data/
│   ├── ibm-hr-attrition-raw.csv
│   └── ibm-hr-attrition-cleaned.xlsx
│
├── README.md
└── NOTES.md
