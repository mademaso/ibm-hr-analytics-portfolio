# IBM HR Analytics and Attrition Study

<p align="center">
  <img src="assets/ibm-logo.png" alt="IBM Logo" width="150"/>
</p>

An end-to-end HR analytics project investigating workforce attrition drivers using the IBM HR dataset. This project covers data cleaning and transformation in Excel, followed by a multi-page interactive Tableau dashboard suite tracking macro-level executive health and micro-level departmental deep-dives.

---

## Tableau Dashboards
You can explore the live, interactive dashboards on Tableau Public:
* **[Executive Overview Dashboard](https://public.tableau.com/views/executive-overview_17907030976820/HREmployeeDataOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** - Macro-level view of company-wide workforce health and turnover distribution across departments and roles.
* **[Sales Representatives Deep-Dive Dashboard](https://public.tableau.com/views/sales-representatives-deep-dive/SalesRepresentativesDeep-Dive?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** - Targeted investigation into the critical 39.8% turnover rate among Sales Reps, analyzing income, overtime, and tenure.

---

## Repository Structure

ibm-hr-analytics-portfolio/
│
├── assets/
│   └── ibm-logo.png                            # Project logo / branding element
│
├── dashboards/
│   └── employee_data_cleaned.twbx              # Packaged Tableau workbook containing both dashboards
│
├── data/
│   ├── ibm-hr-attrition-raw.csv                # Original, raw dataset
│   └── ibm-hr-attrition-cleaned.xlsx           # Cleaned Excel dataset (XLOOKUPs & data dictionary)
│
├── NOTES.md                                    # Detailed project notes, formulas, and deep-dive methodology
└── README.md

---

## Project Workflow and Methodology

1. **Data Preparation and Cleaning (Excel):**
   * Processed the raw IBM HR dataset to ensure data integrity, established an official Excel table, and standardized data types.
   * Utilized formulas like `XLOOKUP` and custom binary translations (`AttritionValue`) to structure records.
   * Established a comprehensive data dictionary for clear field definitions.

2. **Visual Analytics and Reporting (Tableau):**
   * **Dashboard 1 (Executive Overview):** Designed to give stakeholders a high-level pulse check on turnover hotspots across various job roles and departments.
   * **Dashboard 2 (Sales Reps Deep-Dive):** Explored behavioral and financial metrics (overtime, monthly income, stock options, and tenure) to uncover root causes behind high sales attrition.

*For a complete breakdown of data transformations, Excel formulas, and structural methodology, review the full [Project Notes and Methodology](NOTES.md).*

---

## Key Insights and Business Recommendations

* **Address Sales Representative Attrition:** With turnover hitting near 39.8% in this role, leadership should review compensation competitiveness, base-to-commission structures, and frequent overtime patterns.
* **Proactive Engagement for High-Risk Tenures:** Data shows employees within their first 1 to 2 years are most vulnerable; implementing a structured 90-day and 1-year mentorship or check-in program could drastically improve retention.
* **Workload Balancing:** High overtime strongly correlates with departures. Managers should audit workloads across departments to prevent burnout before it leads to resignation.

---
