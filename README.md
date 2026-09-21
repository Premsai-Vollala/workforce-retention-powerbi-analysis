# Enterprise Workforce Demographics & Retention Analytics

## 📌 Executive Dashboard Overview
![Workforce Retention Dashboard](dashboard_overview.png)

This project analyzes enterprise workforce turnover patterns across 5,000 employee records using **Power BI**, **Power Query**, and **DAX**. It evaluates turnover hotspots across departments, salary bands, and tenure brackets to deliver structured retention recommendations.

---

## 🛠️ Tech Stack & Methodology
* **Business Intelligence:** Microsoft Power BI Desktop
* **Data Transformation:** Power Query (Column profiling, schema shaping, star-schema modeling)
* **Analytical Modeling:** DAX (Data Analysis Expressions)
* **Architecture:** Fact & Dimension Relational Star Schema

---

## 📐 Key DAX Measures
* **Attrition Rate:**
  ```dax
  Attrition Rate = 
  DIVIDE(
      CALCULATE(COUNTROWS('employee_workforce_retention_5000'), 'employee_workforce_retention_5000'[Attrition] = "Yes"),
      COUNTROWS('employee_workforce_retention_5000'),
      0
  )
----
2. Overtime Turnover %:

   Overtime Attrition % = 
DIVIDE(
    CALCULATE(COUNTROWS('employee_workforce_retention_5000'), 'employee_workforce_retention_5000'[Attrition] = "Yes", 'employee_workforce_retention_5000'[Overtime] = "Yes"),
    CALCULATE(COUNTROWS('employee_workforce_retention_5000'), 'employee_workforce_retention_5000'[Overtime] = "Yes"),
    0
)

3. Median Tenure:

   Median Tenure = MEDIAN('employee_workforce_retention_5000'[Years_At_Company])

🔍 Key Findings & Business Insights:

  * Early-Tenure Turnover: Employees with less than 1 year of tenure exhibited the highest voluntary departure rate (28.1%).

  * Impact of Overtime: Turnover among employees working consistent overtime reached 25.4%, compared to 17.7% for standard working hours.

  * Compensation Hotspots: Lowest turnover occurred in senior tiers, while the entry salary band (<50K) experienced an attrition rate of 22.2%.

📂 Repository Contents:

  ├── employee_workforce_retention_5000.csv   # 5,000-record enterprise HR dataset
├── date_table.csv                          # Date dimension table for time-intelligence DAX
├── dashboard_overview.png                  # Executive report preview
└── README.md                               # Project documentation
