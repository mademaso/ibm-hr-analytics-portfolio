# IBM HR Analytics and Attrition Study

<p align="center">
  <img src="assets/ibm-logo.png" alt="IBM Logo" width="150"/>
</p>

**Author:** [Matteo De Maso](https://www.linkedin.com/in/mademaso) | [Contact Email](mailto:mademaso@outlook.com)

An HR analytics project using the IBM HR Analytics Employee Attrition & Performance dataset from Kaggle. The project uses Excel to clean and organize the data and Tableau to present findings on employee attrition, with a closer look at the Sales Representative role.

**[View Executive Overview Dashboard](https://public.tableau.com/views/executive-overview_17907232274830/HREmployeeDataOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** | **[View Sales Representatives Deep-Dive Dashboard](https://public.tableau.com/views/sales-representatives-deep-dive/SalesRepresentativesDeep-Dive?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## Project Overview

The project follows a simple workflow:

1. Start with the IBM HR Analytics dataset from Kaggle.
2. Clean and organize the data in Excel.
3. Create calculated fields and a data dictionary to make the dataset easier to analyze.
4. Use Tableau to analyze and present employee attrition patterns.
5. Identify areas that may warrant further investigation.

---

## Tools Used

- **Microsoft Excel:** Data cleaning, organization, formulas, and data preparation.
- **Tableau Public:** Data visualization and dashboard creation.
- **GitHub:** Project files and documentation.

---

## Key Findings

- The overall attrition rate in the dataset is **16.12%** across 1,470 employees.
- The **Sales Representative** role has the highest attrition rate at **39.76%**.
- Sales Representatives have an average monthly income of **$2,626**, compared with **$6,503** across the full dataset.
- Among Sales Representatives, attrition is higher in lower monthly income brackets:
  - Under $2.5K: **48.72%**
  - $2.5K–$3.5K: **35.14%**
  - Over $3.5K: **14.29%**
- Sales Representatives who work overtime have a higher attrition rate (**66.70%**) than those who do not (**28.81%**).
- Attrition is also higher among Sales Representatives with shorter tenure:
  - Under 1 year: **57.14%**
  - 1–3 years: **43.64%**
  - Over 3 years: **23.81%**

These patterns suggest that compensation, overtime, and early tenure may be useful areas to investigate when considering Sales Representative retention.

---

## Dashboard 1: Executive Overview

The Executive Overview presents a high-level view of the dataset, including:

- Total headcount
- Overall attrition rate
- Average monthly income
- Average years at the company
- Attrition by department
- Attrition by job role

The dashboard highlights the Sales Representative role as an area for further investigation.

---

## Dashboard 2: Sales Representatives Deep-Dive

The Sales Representatives Deep-Dive focuses on the role with the highest attrition rate in the dataset.

It examines attrition by:

- Monthly income bracket
- Overtime status
- Tenure bracket

The dashboard provides a closer look at patterns that may help explain the high attrition rate among Sales Representatives.

---

## Business Recommendations

Based on the patterns identified in the analysis, several areas may warrant further investigation:

- Review compensation for Sales Representatives to better understand the relationship between pay and attrition.
- Examine workload and overtime among Sales Representatives.
- Investigate factors that may contribute to stronger retention after employees reach three years of tenure.

These recommendations are based on patterns in the dataset and would require additional information before drawing conclusions about the underlying causes of turnover.

---

## Repository Structure

- `assets/` — Contains the IBM logo used in the project.
- `dashboards/` — Contains the packaged Tableau workbook.
- `data/` — Contains the original dataset and cleaned Excel dataset.
- `NOTES.md` — Contains detailed project notes and methodology.
- `README.md` — Project overview and dashboard links.
