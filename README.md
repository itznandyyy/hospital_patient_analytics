# 🏥 Hospital Operations & Patient Analytics

An end-to-end analysis of a multispecialty hospital's patient data using **SQL, Python, and Power BI** to identify operational challenges related to waiting times, readmissions, costs, patient satisfaction, and doctor workload.

The project focuses on analyzing hospital performance, identifying operational bottlenecks, and providing data-driven recommendations for improving efficiency and patient experience.

![Dashboard Preview](Dashboard.png)

## 🎯 Business Problem

The hospital has experienced an increase in patient visits over the past year. Management wants to understand where operations are strained and identify opportunities for improvement.

Key business questions:

- Are patients waiting too long, and does waiting time affect satisfaction?
- Which departments have the highest patient workload?
- Which departments have higher costs or readmission rates?
- What factors influence patient length of stay and revenue?
- How can hospital operations and patient experience be improved?

## 📊 Dataset

- **Source:** `hospitaldata.csv`
- **Dataset Type:** Synthetic practice data
- **Total Records:** 2,000 patient visits
- **Total Columns:** 25
- **Period:** January–December 2025
- **Departments:** 7
- **Cities:** 6
- **Doctors:** 8

### Dataset Features

| Category | Information |
|---|---|
| Patient Details | Age, gender, city, blood group, BMI |
| Visit Details | Department, doctor, diagnosis, severity, admission type |
| Operations | Waiting time, length of stay, discharge status, 30-day readmission |
| Billing | Treatment cost, medicine cost, lab cost, room cost, total bill |
| Payment | Payment mode, insurance |
| Patient Experience | Satisfaction score from 1 to 5 |

### Data Quality Checks

- Checked for missing values and duplicate records.
- Reviewed billing calculations and relationships between cost columns.
- Identified an issue with the `TotalBill` column.

**Important finding:** `TotalBill` is exactly 1.667 times `TreatmentCost` for every patient and does not equal the sum of the four cost columns.

## 🛠️ Tools & Technologies

| Area | Tools |
|---|---|
| Database | MySQL 8.0 |
| Data Analysis | Python, pandas |
| Visualization | matplotlib |
| Notebook | Jupyter Notebook |
| Dashboard | Power BI Desktop |
| Calculations | DAX |

## 💡 Recommendations

1. **Improve Readmission Management:** Audit discharge procedures and follow-up care, starting with Neurology and Oncology, and validate the unusually high readmission rate.
2. **Reduce Waiting Time:** Set a hospital-wide target of under 60 minutes and monitor waiting times monthly across departments.
3. **Enhance Patient Satisfaction:** Introduce patient feedback surveys and collect comments to better understand patient experience.
4. **Validate Billing Data:** Review the `TotalBill` calculation and verify cost components before making financial decisions.


## 🔍 Project Workflow

### 1. SQL Analysis

**File:** `Acte_Hospital_Data.sql`

Created and executed 22 SQL queries to analyze hospital operations and patient data.

1. Total number of patient visits.
2. Patient count by department.
3. Average waiting time by department.
4. Average treatment cost by department.
5. Total revenue by department.
6. Patient count by city.
7. Payment mode usage distribution.
8. Most frequently used payment mode.
9. Average patient satisfaction by department.
10. Top 10 patients with the highest total bills.
11. Departments with an average length of stay above 5 days.
12. Patients with total bills above the overall average.
13. Rank patients by total bill using `RANK()`.
14. Patients with treatment costs above their department average.
15. Departments with readmission rates above the hospital average.
16. Patient distribution by age group.
17. Relationship between waiting time and patient satisfaction.
18. Monthly revenue, month-over-month changes, and running totals.
19. Top 3 highest-billing patients in each department.
20. Identify priority departments based on waiting time and readmission rates.
21. Doctor workload and performance analysis.
22. Revenue concentration by department (Pareto analysis).

### 2. Python Data Analysis

**File:** `Acte_Hospital_Data.ipynb`

Used Python, pandas, and matplotlib to perform exploratory data analysis and visualization.

- Data quality and validation
- Patient visit volume
- Department-wise patient distribution
- Payment mode distribution
- Patient satisfaction analysis
- 30-day readmission analysis
- Age group analysis
- Waiting time versus satisfaction
- Length of stay by severity
- Monthly revenue trends
- Doctor workload analysis
- Department operational priorities

Each analysis includes visualizations and written conclusions.

### 3. Power BI Dashboard

**File:** `Acte_Hospital_Data.pbix`

Developed an interactive dashboard to monitor hospital operations and patient analytics.

**KPI Cards:**
- Total Patients
- Total Revenue
- Average Waiting Time
- Average Patient Age
- Patient Satisfaction Gauge

**Visualizations:**
- Patient visits by department
- Revenue by department
- Payment mode distribution
- Monthly patient visits
- Length of stay by severity
- Patient satisfaction by department

**Interactive Features:**
- Gender slicer
- Department slicer
- City slicer
- Reset Filters button using a bookmark

## 📈 Key Findings

### 1. Readmission Is the Biggest Concern

- Overall 30-day readmission rate: **49.75%**
- Department rates range from approximately **47.1% to 55.1%**
- Neurology has the highest rate at **55.1%**, with 265 patients.

### 2. Waiting Time Is a Hospital-Wide Issue

- Average waiting time: **93.6 minutes**
- Approximately **70% of patients wait one hour or more**
- Department averages range from **88.6 to 97.4 minutes**

### 3. Severity Is the Main Factor Associated With Length of Stay

| Severity | Average Length of Stay |
|---|---:|
| Low | 1.1 days |
| Medium | 3.5 days |
| High | 8.4 days |

### 4. Patient Volume and Doctor Workload Are Relatively Balanced

- Department patient volume ranges from **265 to 303 visits**.
- Doctor workload ranges from **236 to 262 patients**.
- UPI transactions: **512**
- Cash transactions: **509**

### 5. Revenue Follows Patient Volume

- Total reported revenue: **₹46.6 million**
- January revenue: **₹4.45 million**
- December revenue: **₹3.36 million**

Revenue declined between January and December. However, one year of data is insufficient to establish whether this pattern is seasonal.

## ⚠️ Limitations

- The dataset is synthetic practice data, not real hospital records.
- `TotalBill` is exactly 1.667 times `TreatmentCost`, limiting financial analysis.
- Satisfaction scores are evenly distributed, and the readmission rate is unusually high.
- The dataset covers only one year and 2,000 patient visits.
- Small differences between departments may not be statistically significant.

**This project demonstrates analytical methods and dashboard development. Its findings should not be used as evidence for real clinical or hospital management decisions.**

## 📂 Project Structure

## 📂 Project Structure

```text
hospital_patient_analytics/
│
├── README.md
├── hospitaldata.csv
├── Acte_Hospital_Data.sql
├── Acte_Hospital_Data.ipynb
├── Acte_Hospital_Data.pbix
└── Dashboard.png
```

## How to Run the Project

### SQL Analysis

**Requirements:** MySQL 8.0 or later and MySQL Workbench.

1. Create a database in MySQL.
2. Import `hospitaldata.csv` into a table named `hospitaldata`.
3. Open `Acte_Hospital_Data.sql`.
4. Execute the queries from top to bottom.
5. Run the initial `ALTER TABLE` statements only once.

### Python Analysis

Install the required libraries:

```bash
pip install pandas matplotlib numpy
```
Launch Jupyter Notebook:

```bash
jupyter notebook
```
Open `Acte_Hospital_Data.ipynb` from the repository root and run the cells from top to bottom.

Keep hospitaldata.csv in the same folder as the notebook.

### Power BI Dashboard
1. Open Acte_Hospital_Data.pbix in Power BI Desktop.
2. If prompted, configure the data source to `hospitaldata.csv`
3. Apply changes and refresh the dashboard.
   
