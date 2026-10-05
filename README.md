# IBM HR Analytics & Attrition Study

<p align="center">
  <img src="assets/ibm-logo.png" alt="IBM Logo" width="150"/>
</p>

**Author:** [Matteo De Maso](https://www.linkedin.com/in/mademaso) | [Contact Email](mailto:mademaso@outlook.com)

An independent HR analytics project using the IBM HR Analytics Employee Attrition & Performance dataset from Kaggle. The project uses **Excel** to prepare and organize the data and **Tableau Public** to explore patterns in employee attrition.

**[View Executive Overview Dashboard](https://public.tableau.com/views/executive-overview_17907232274830/HREmployeeDataOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** | **[View Sales Representatives Dashboard](https://public.tableau.com/views/sales-representatives-deep-dive/SalesRepresentativesDeep-Dive?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## Project Overview

The project examines **1,470 employee records** and focuses on where employee attrition is highest and what patterns appear among employees who leave.

The analysis includes:

- Preparing and organizing the dataset in Excel
- Creating a data dictionary for coded fields
- Using Excel formulas such as `IF` and `XLOOKUP`
- Building interactive Tableau dashboards
- Comparing attrition across departments and job roles
- Exploring income, overtime, and tenure patterns among Sales Representatives

---

## Tools Used

- **Microsoft Excel** — data preparation, formulas, data organization, and data dictionary
- **Tableau Public** — interactive dashboards and data visualization

---

## Key Findings

- Overall attrition in the dataset is **16.12%**.
- Sales Representatives have the highest attrition rate among the job roles shown, at **39.76%**.
- Sales Representatives have an average monthly income of **$2,626**, compared with **$6,503** across the full dataset.
- Among Sales Representatives, attrition is higher in the lower monthly income groups.
- Sales Representatives working overtime have a higher attrition rate (**66.7%**) than those who do not (**28.81%**).
- Sales Representatives also show higher attrition among employees with shorter tenure.

These findings show patterns in the dataset that may warrant further investigation. They should not be interpreted as proof that income, overtime, or tenure directly causes attrition.

---

## Dashboards

### Executive Overview

Provides a high-level view of the dataset, including:

- Total headcount
- Overall attrition rate
- Average monthly income
- Average years at the company
- Attrition by department
- Attrition by job role

### Sales Representatives Deep-Dive

Focuses on the job role with the highest attrition rate in the dataset.

The dashboard examines Sales Representative attrition by:

- Monthly income
- Overtime
- Tenure

---

## Repository Contents

- `dashboards/` — Tableau packaged workbook (`.twbx`)
- `data/` — original dataset and cleaned Excel workbook
- `NOTES.md` — project methodology, formulas, dashboard details, and findings

---

## Data Source

IBM HR Analytics Employee Attrition & Performance dataset from Kaggle:

**[Kaggle Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)**
