# IBM HR Analytics Project - Notes & Methodology

**Dataset:** IBM HR Analytics Employee Attrition & Performance  
**Source:** [Kaggle - IBM HR Analytics Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

## Project Overview

This project uses Excel and Tableau to clean, organize, and analyze an employee workforce dataset. The goal was to identify patterns in employee attrition and investigate areas with notably high turnover.

---

## Part 1: Excel Data Preparation

### Initial Setup

- Backed up the original CSV dataset.
- Saved a copy as an Excel workbook for cleaning and analysis.
- Renamed the primary worksheet to `Employee Data`.
- Created an Excel table named `tblEmployeeData`.
- Used Excel filters to review the dataset for missing values or obvious data issues.
- Checked and adjusted column data types where needed.

### Data Dictionary

Created a separate `Data Dictionary` worksheet to make several coded fields easier to understand and use in analysis.

Created an Excel table named `tblDataDictionary`.

The dictionary was used to translate coded values for:

- Education
- Environment Satisfaction
- Job Involvement
- Job Satisfaction
- Performance Rating
- Relationship Satisfaction
- Work Life Balance

### Calculated Fields

Created an `AttritionValue` column to convert the text values in the `Attrition` field into numbers that could be used for calculating attrition rates.

Formula: `=IF([@Attrition]="Yes",1,0)`

Used `XLOOKUP` formulas with the Data Dictionary to create readable versions of several coded fields.

Examples:

- `EducationName`: `=XLOOKUP($I2,'Data Dictionary'!$A$2:$A$6,'Data Dictionary'!$B$2:$B$6)`
- `EnvironmentSatisfactionName`: `=XLOOKUP($N2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$C$2:$C$5)`
- `JobInvolvementName`: `=XLOOKUP($R2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$D$2:$D$5)`
- `JobSatisfactionName`: `=XLOOKUP($V2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$E$2:$E$5)`
- `PerformanceRatingName`: `=XLOOKUP($AF2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$F$2:$F$5)`
- `RelationshipSatisfactionName`: `=XLOOKUP($AH2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$G$2:$G$5)`
- `WorkLifeBalanceName`: `=XLOOKUP($AN2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$H$2:$H$5)`

Created a `SalaryHike` field by converting the `PercentSalaryHike` values into percentage format.

Formula: `=[@PercentSalaryHike]/100`

### Dataset Review

Identified several columns with no variation across the dataset:

- `EmployeeCount`
- `Over18`
- `StandardHours`

These fields were not useful for the analysis and were excluded from the Tableau visualizations.

---

## Part 2: Tableau Preparation

The cleaned Excel workbook was connected to Tableau using the `Employee Data` worksheet as the data source.

### Field Preparation

- Reviewed field names and data types.
- Organized fields as dimensions or measures where appropriate.
- Hid coded fields after creating readable versions.
- Hid fields with no variation.
- Hid financial fields that were not needed for the dashboards.
- Kept `Monthly Income` as the primary financial measure.
- Hid other fields that were not used in the final visualizations.

### Calculated Fields

Created several calculated fields in Tableau for the dashboards.

**Attrition Rate:** `AVG([Attrition Value])`

**Headcount:** `COUNT([Employee Number])`

**Monthly Income Brackets:** `IIF([Monthly Income]<2500,"Under $2.5K", IIF([Monthly Income]<=3500,"$2.5K - $3.5K","Over $3.5K"))`

**Tenure Brackets:** `IIF([Years At Company]<1,"Under 1 Year",IIF([Years At Company]<=3,"1 Year - 3 Years","Over 3 Years"))`

### Number Formatting

Formatted fields according to the type of information being displayed:

- Currency and counts: 0 decimal places
- Time and distance measures: 1 decimal place
- Percentages: 2 decimal places

---

## Part 3: Dashboards

### Dashboard 1: Executive Overview

**Title:** `HR Employee Data Overview`

The first dashboard provides an overview of workforce size, overall attrition, income, tenure, and attrition by department and job role.

**Key Metrics**

- Total headcount: 1,470
- Overall attrition rate: 16.12%
- Average monthly income: $6,503
- Average years at company: 7.0

**Attrition by Department**

- Sales: 20.63%
- Human Resources: 19.05%
- Research & Development: 13.84%

**Attrition by Job Role**

- Sales Representative: 39.76%
- Laboratory Technician: 23.94%
- Human Resources: 23.08%
- Sales Executive: 17.48%
- Research Scientist: 16.10%
- Manufacturing Director: 6.90%
- Healthcare Representative: 6.87%
- Manager: 4.90%
- Research Director: 2.50%

### Dashboard 2: Sales Representatives Deep-Dive

**Title:** `Sales Representatives Deep-Dive`

The second dashboard focuses on the Sales Representative role because it had the highest attrition rate in the dataset.

**Key Metrics**

- Sales Representative headcount: 83
- Sales Representative attrition rate: 39.76%
- Average monthly income: $2,626
- Average years at company: 2.9

**Attrition by Monthly Income**

- Under $2.5K: 48.72%
- $2.5K - $3.5K: 35.14%
- Over $3.5K: 14.29%

**Attrition by Overtime**

- Overtime: Yes — 66.70%
- Overtime: No — 28.81%

**Attrition by Tenure**

- Under 1 Year: 57.14%
- 1 Year - 3 Years: 43.64%
- Over 3 Years: 23.81%

The dashboards were saved as a packaged Tableau workbook (`.twbx`) and published to Tableau Public.

---

## Part 4: Key Findings

### Sales Representative Attrition

Sales Representatives had the highest attrition rate among the job roles shown in the analysis at 39.76%, compared with an overall company attrition rate of 16.12%.

### Monthly Income

Sales Representatives had an average monthly income of $2,626 compared with $6,503 across the full dataset.

Within the Sales Representative group, attrition was higher among employees in the lower monthly income brackets:

- Under $2.5K: 48.72%
- $2.5K - $3.5K: 35.14%
- Over $3.5K: 14.29%

This shows an association between lower monthly income and higher attrition in this group.

### Overtime

Sales Representatives who reported working overtime had a 66.70% attrition rate, compared with 28.81% for those who did not.

This indicates that overtime is another area worth investigating when considering Sales Representative turnover.

### Tenure

Sales Representatives had an average tenure of 2.9 years.

Attrition was highest among employees with shorter tenure:

- Under 1 year: 57.14%
- 1-3 years: 43.64%
- Over 3 years: 23.81%

The lower attrition rate among employees with more than three years at the company suggests that the early stages of employment may be an important period to examine.

---

## Part 5: Business Recommendations

Based on the patterns identified in the analysis, several areas may warrant further investigation.

### Compensation

Review compensation for Sales Representatives to determine whether lower pay may be associated with turnover and whether adjustments could improve retention.

### Workload and Overtime

Review workload and overtime expectations for Sales Representatives to better understand whether extended working hours may be associated with turnover.

### Early Tenure

Investigate the experiences of Sales Representatives during their first several years with the organization and identify factors that may help employees remain with the company beyond the three-year mark.

These recommendations are based on patterns in the dataset and are intended as areas for further investigation rather than definitive explanations for employee turnover.
