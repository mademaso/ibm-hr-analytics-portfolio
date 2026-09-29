# IBM HR Analytics and Attrition Study

<p align="center">
  <img src="assets/ibm-logo.png" alt="IBM Logo" width="150"/>
</p>

**Author:** [Matteo De Maso](www.linkedin.com/in/mademaso) | [Contact Email](mailto:mademaso@outlook.com)

An end-to-end HR analytics project investigating workforce attrition drivers using the IBM HR Analytics Employee Attrition and Performance dataset from Kaggle. This project uncovers critical turnover hotspots and provides actionable retention strategies through a multi-page interactive Tableau dashboard suite built on a cleaned Microsoft Excel data model.

**[Explore Executive Overview Dashboard](https://public.tableau.com/views/executive-overview_17907030976820/HREmployeeDataOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** | **[Explore Sales Reps Deep-Dive Dashboard](https://public.tableau.com/views/sales-representatives-deep-dive/SalesRepresentativesDeep-Dive?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## Tech Stack and Skills Demonstrated

* **Data Engineering and Cleaning (Excel):** Built `tblEmployeeData` and a reference `tblDataDictionary` sheet. Utilized `IF` functions for binary aggregation flags (`AttritionValue = 1/0`), `XLOOKUP` formulas to map categorical codes into readable text names (such as job satisfaction and education levels), and converted percentage salary hikes. Cleaned scope by dropping zero-variance columns (`EmployeeCount`, `Over18`, `StandardHours`).
* **Data Visualization and Business Intelligence (Tableau Public):** Developed a packaged workbook (`.twbx`) featuring calculated fields for `Attrition Rate` (`AVG([Attrition Value])`), `Headcount`, income brackets, and tenure brackets, alongside tailored decimal formatting.
* **Domain Expertise:** HR Analytics, Workforce Planning, Root-Cause Attrition Analysis.

---

## Key Findings and Business Recommendations

* **The Sales Representative Crisis (39.76% Turnover):** While overall company attrition sits at 16.12% (across 1,470 records), Sales Representatives suffer from an abnormally high turnover rate of 39.76% compared to other roles like Laboratory Technicians (23.94%) and HR staff (23.08%).
* **Income and Overtime Pressures:** Sales reps average a lower monthly income ($2,626 vs. $6,503 company average), and analysis reveals a direct income bracket correlation (48.72% attrition under $2.5K vs. 14.29% over $3.5K). Furthermore, mandatory overtime pushes sales rep attrition up to 66.7%.
* **Critical Tenure Window:** Sales reps average only 2.9 years at the company, with severe drop-offs occurring early (57.14% attrition under 1 year; 43.64% between 1 and 3 years). Those who pass the 3-year mark stabilize significantly (23.81%).
* **Strategic Recommendations:** Leadership should review compensation bands for sales representatives to determine if increasing base pay is more cost-effective than continuous recruitment turnover, audit workloads to prevent burnout from excessive overtime, and investigate retention factors for employees who stay past three years.

---

## Dashboard Preview and Architecture

### 1. Executive Overview Dashboard
Designed for executive leadership to monitor macro-level workforce health. Features KPIs for total headcount (1,470), overall attrition rate (16.12%), average monthly income ($6,503), and average years at company (7.0), alongside department and job role breakdown charts.

### 2. Sales Representatives Deep-Dive Dashboard
A targeted investigation into sales rep dynamics. Features specialized KPIs (83 headcount, 39.76% attrition, $2,626 avg. income, 2.9 avg. tenure) supported by visual analytics on monthly income effects, overtime impact, and tenure brackets.

For a complete breakdown of data transformations, Excel formulas, and analytical methodology, check out the full [Project Notes](NOTES.md).

---

## Repository Structure

* `dashboards/` - Packaged Tableau workbook (`employee_data_cleaned.twbx`)
* `data/` - Original raw CSV dataset and finished cleaned Excel dataset (`ibm-hr-attrition-cleaned.xlsx`)
* `NOTES.md` - Technical methodology, formulas, and data preparation documentation
