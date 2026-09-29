# IBM HR Analytics Project - Full Notes and Methodology

* **Dataset:** IBM HR Analytics Employee Attrition & Performance
* **Source:** [Kaggle - IBM HR Analytics Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
* **Project Overview:** Utilizing Excel and Tableau to clean a workforce dataset and discover underlying trends and drivers in employee attrition.

---

## Part 1: Excel Notes & Data Integrity

### Initial Setup & Data Hygiene
* Backed up the original raw CSV file, renamed to `ibm-hr-attrition-raw`.
* Saved a copy of the dataset as an XLSX file, renamed to `ibm-hr-attrition-cleaned`.
* Renamed the primary worksheet to `Employee Data` and formatted the data range as an official Excel table titled `tblEmployeeData`.
* Scanned the dataset using Excel filters to verify data integrity and confirm no structural corruption or missing values.
* Standardized each column into its correct data type.

### Data Dictionary & Metadata
* Created a dedicated reference sheet titled `Data Dictionary` to translate unintuitive numeric codes and serve as a user guide.
* Organized the reference sheet into an official table titled `tblDataDictionary`.

### Calculated Fields & Transformations (Highlighted Yellow Headers)
* **AttritionValue:** Translated text strings into binary indicators for numerical aggregation:
  * `=IF([@Attrition]="Yes",1,0)`
* **Categorical Mapping via XLOOKUP:** Leveraged the `Data Dictionary` reference sheet to decode standard categorical columns:
  * *EducationName:* `=XLOOKUP($I2,'Data Dictionary'!$A$2:$A$6,'Data Dictionary'!$B$2:$B$6)`
  * *EnvironmentSatisfactionName:* `=XLOOKUP($N2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$C$2:$C$5)`
  * *JobInvolvementName:* `=XLOOKUP($R2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$D$2:$D$5)`
  * *JobSatisfactionName:* `=XLOOKUP($V2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$E$2:$E$5)`
  * *PerformanceRatingName:* `=XLOOKUP($AF2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$F$2:$F$5)`
  * *RelationshipSatisfactionName:* `=XLOOKUP($AH2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$G$2:$G$5)`
  * *WorkLifeBalanceName:* `=XLOOKUP($AN2,'Data Dictionary'!$A$2:$A$5,'Data Dictionary'!$H$2:$H$5)`
* **SalaryHike:** Converted percentage points into true percentage data types using division:
  * `=[@PercentSalaryHike]/100`

### Scope Optimization
* Identified and documented columns containing zero variance to be excluded from visualization phases:
  * `EmployeeCount`
  * `Over18`
  * `StandardHours`

---

## Part 2: Tableau Preparation & Architecture

### Dataset Connection & Field Organization
* Connected Tableau directly to the `Employee Data` sheet from the cleaned workbook.
* Verified field titles and data types.
* Hid redundant coded fields, zero-variance columns, and unnecessary financial metrics while retaining `Monthly Income` as the primary financial measure.
* Saved the initial file format as a `.twb` file.

### Calculated Fields & Number Formatting
* Created key analytical calculated fields:
  * *Attrition Rate:* `AVG([Attrition Value])`
  * *Headcount:* `COUNT([Employee Number])`
  * *Monthly Income Brackets:* `IIF([Monthly Income]<2500,"Under $2.5K", IIF([Monthly Income]<=3500,"$2.5K - $3.5K","Over $3.5K"))`
  * *Tenure Brackets:* `IIF([Years At Company]<1,"Under 1 Year",IIF([Years At Company]<=3,"1 Year - 3 Years","Over 3 Years"))`
* Standardized number formatting across all fields:
  * Currency, counts, and discrete corporate levels: 0 decimal places
  * Time and distance metrics: 1 decimal place
  * Percentages: 2 decimal places

### Field References
* **Dimensions List:** Attrition, Business Travel, Department, Education Field, Education Name, Environment Satisfaction Name, Gender, Job Involvement Name, Job Level, Job Role, Job Satisfaction Name, Marital Status, Monthly Income Brackets, Over Time, Performance Rating Name, Relationship Satisfaction Name, Stock Option Level, Tenure Brackets, Work Life Balance Name.
* **Measures List:** Age, Attrition Rate, Distance From Home, Headcount, Monthly Income, Num Companies Worked, Salary Hike, Total Working Years, Training Times Last Year, Years At Company, Years In Current Role, Years Since Last Promotion, Years With Curr Manager, Employee Data (Count), Measure Values.

---

## Part 3: Dashboard Architecture & Findings

### Dashboard 1: Executive Overview (`HR Employee Data Overview`)
* Serves as a macro-level executive summary for company-wide workforce health.
* Features the corporate logo in the top left and is titled `HR Employee Data Overview`.
* **Executive KPIs (Horizontal Layout):**
  * Total Headcount: 1,470
  * Overall Attrition Rate: 16.12%
  * Average Monthly Income: $6,503
  * Average Years at Company: 7.0 years
* **Visualization 1 (Attrition by Department - Horizontal Bar):** Ranked in descending order of turnover:
  * Sales: 20.63%
  * Human Resources: 19.05%
  * Research & Development: 13.84%
* **Visualization 2 (Attrition by Job Role - Horizontal Bar):** Highlighting organizational turnover hotspots:
  * Sales Representative: 39.76%
  * Laboratory Technician: 23.94%
  * Human Resources: 23.08%
  * Sales Executive: 17.48%
  * Research Scientist: 16.10%
  * Manufacturing Director: 6.90%
  * Healthcare Representative: 6.87%
  * Manager: 4.90%
  * Research Director: 2.50%

### Dashboard 2: Targeted Deep-Dive (`Sales Representatives Deep-Dive`)
* Investigates the critical attrition drivers within the Sales Representative job role.
* Maintains visual consistency with Dashboard 1, including the top-left logo and title `Sales Representatives Deep-Dive`.
* **Sales-Specific KPIs (Horizontal Layout):**
  * Sales Rep Headcount: 83
  * Sales Rep Attrition Rate: 39.76%
  * Average Monthly Income: $2,626
  * Average Years at Company: 2.9 years
* **Visualization 3 (Monthly Income Effect - Line Chart):** Attrition breakdown by income tiers:
  * Under $2.5K: 48.72%
  * $2.5K - $3.5K: 35.14%
  * Over $3.5K: 14.29%
* **Visualization 4 (Over Time Effect - Vertical Bar):** 
  * Yes: 66.70%
  * No: 28.81%
* **Visualization 5 (Tenure Effect - Vertical Bar):** 
  * Under 1 Year: 57.14%
  * 1 Year - 3 Years: 43.64%
  * Over 3 Years: 23.81%

* **Finalization:** Saved as a packaged `.twbx` workbook and published to Tableau Public.

---

## Part 4: Key Findings & Strategic Recommendations

### Key Findings
* Attrition is notably concentrated within the Sales and Human Resources departments.
* The Sales Representative role displays an abnormally high attrition rate (39.76%), driving the need for targeted investigation:
  * Sales representatives earn significantly lower average monthly incomes compared to the broader company average, revealing an inverse correlation between lower pay bands and high turnover.
  * Sales representatives logging frequent overtime experience a substantially higher attrition rate (66.70%).
  * Sales representatives have shorter average tenures than the general workforce, with strong correlations between early tenure brackets and turnover.

### Strategic Recommendations
* **Targeted Compensation Review:** Conduct an immediate review of base pay structures for entry-to-mid level Sales Representatives. Adjusting compensation to market competitiveness may prove more cost-effective than continuous recruitment and onboarding churn.
* **Workload and Overtime Audit:** Implement managerial workload reviews within the sales division to prevent chronic burnout and structural fatigue caused by excessive overtime.
* **Retention and Onboarding Milestones:** Investigate why sales representatives who surpass the 3-year tenure mark anchor successfully within the organization, and build out proactive support systems for new hires during their first 1 to 2 years.
