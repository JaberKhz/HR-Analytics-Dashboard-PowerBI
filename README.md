# 📊 Apex HR Analytics: End-to-End Data Project

## 📝 Project Overview
This project is an end-to-end data analytics solution designed for "Apex HR", focusing on transforming raw, messy human resources data into actionable insights. The goal is to monitor workforce demographics, evaluate the impact of training on employee performance, and uncover the root causes of employee attrition and turnover.

## 🛠️ Tools & Technologies Used
* **Microsoft Excel / Power Query:** Data extraction, deep cleaning, and transformation.
* **Power BI:** Data modeling, DAX measure creation, and interactive dashboard design.

## 🧹 Data Cleaning & Transformation (The Data Log)
The initial dataset consisted of multiple disparate tables with significant quality issues. A rigorous data cleaning process was applied, documented in the `Data Cleaning Log`. 
Key transformations included fixing time parsing errors, handling missing values, and standardizing categorical data across the following tables:
* **Attendance:** Cleaned anomalies in check-in/out records.
* **Department & Roles:** Standardized naming conventions.
* **Leave & Recruitment:** Formatted dates and calculated durations.
* **Performance & Training:** Merged scores and mapped training hours.
*(View the `01-Raw_and_Cleaned_Data` folder for Before/After snapshots).*

## 🔗 Data Modeling & DAX
* Built a robust relational **Data Model** (Star Schema) connecting the 8 dimensional and fact tables.
* Created a centralized `CALENDAR` table for Time Intelligence analysis.
* Managed complex relationships, including resolving role-playing dimensions (e.g., handling both `Hire_Date` and `Termination_Date` using `USERELATIONSHIP`).
* Developed advanced **DAX Measures** for dynamic KPIs, including:
  * `Terminated Employees = CALCULATE(COUNTROWS('Employees'), 'Employees'[Employment_Status] = "Terminated")`
  * `Attrition Rate = DIVIDE([Terminated Employees], COUNTROWS('Employees'))`

---

## 📈 Interactive Dashboards

### 1. HR Overview
Provides a high-level snapshot of the workforce, including headcount, hiring trends, and active vs. on-leave statuses.
<img width="1358" height="754" alt="22 - Over View" src="https://github.com/user-attachments/assets/da727f91-3894-4745-80a3-10e5918329a3" />


### 2. Performance & Training
Analyzes the correlation between training investments and employee performance scores, utilizing scatter plots with dynamic trend lines.
<img width="1341" height="760" alt="23 - Performance   Ttraning" src="https://github.com/user-attachments/assets/671c0557-1d0d-4b39-ae86-019b9f72e187" />


### 3. Attrition & Turnover
Uncovers where and why the company is losing talent. Highlights the highest attrition by department (e.g., Sales & IT) and tracks the turnover trend over time.
<img width="1349" height="753" alt="24 - Turn Over" src="https://github.com/user-attachments/assets/8d398c1b-a99f-41fd-bbc3-7e0649c5e115" />


---

## 💡 Key Business Insights
1. **Attrition Hotspots:** The Sales and IT departments experience the highest employee turnover rates, requiring immediate retention strategies.
2. **Training ROI:** There is a clear positive correlation between total training hours and average performance scores, justifying continued investment in employee development programs.
3. **Turnover Trends:** Cohort analysis based on hire dates reveals critical drop-off points, allowing HR to proactively engage at-risk employees.

## 📂 Repository Structure
* `/01-Raw_and_Cleaned_Data`: Excel files and the comprehensive Data Cleaning Log.
* `/02-PowerBI_Dashboard`: The interactive `.pbix` file.
* `/03-Screenshots`: High-resolution dashboard snapshots.

---
*Created as part of a comprehensive Data Analytics portfolio.*
