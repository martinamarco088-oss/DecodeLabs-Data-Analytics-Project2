# 📊 DecodeLabs-Data-Analytics-Project2
## Week 2 - Project 2: Exploratory Data Analysis (EDA) & Data Auditing

## 📝 Project Overview
This repository contains the deliverables for **Project 2 (Week 2)** of the DecodeLabs Data Analytics track. The primary objective of this phase is to build upon the cleaned transaction dataset by executing a rigorous **Exploratory Data Analysis (EDA)**. This involves calculating descriptive statistical measures using live Excel formulas, identifying distribution skewness, uncovering high-value transactional outliers, and auditing advanced business KPIs to isolate gross vs. net financial metrics.

---

## 🛠️ Data Processing & Analysis Documentation

| Step | Scope / Column | Description of Analysis | Action Taken & Excel Formula | Impact & Business Logic | Status |
| :---: | :--- | :--- | :--- | :--- | :---: |
| **1** | **Descriptive Statistics** <br>`Quantity`, `UnitPrice`, `TotalPrice` | Profiling central tendency and dataset boundaries to understand overall distribution shape. | Implemented live dynamic functions:<br>`=AVERAGE()`<br>`=MEDIAN()`<br>`=MODE.SNGL()`<br>`=MIN()`<br>`=MAX()` | Found that **Mean (\$1,053.97)** > **Median (\$823.62)** for `TotalPrice`, mathematically proving that the distribution is **positively skewed (right-skewed)**. | **Resolved** |
| **2** | **Outlier Detection** <br>`TotalPrice` | Investigating extreme maximum observations that significantly deviate from the core median. | Filtered and audited transaction clusters exceeding **\$3,500**. | Proved that upper-bound outliers are legitimate high-volume wholesale orders where `Quantity = 5` and `UnitPrice > $699`, not systemic data entry errors. | **Resolved** |
| **3** | **Core Business KPIs** <br>Enterprise Performance | Isolating baseline sales figures, aggregate items sold, and individual transaction weights. | Created summarized global aggregation blocks via metrics:<br>- **Total Gross Revenue:** `=SUM()` <br>- **Total Units Sold:** `=SUM()` <br>- **AOV:** `=AVERAGE()` | Defined the company's baseline: <br>Gross Revenue: **\$1,257,384.18** <br>Units Sold: **3,514 Units** <br>Average Order Value (AOV): **\$1,053.97**. | **Resolved** |
| **4** | **Advanced Audit** <br>`Net-TotalProfit` | Building conditional criteria to bridge gross receipts with net strategic yields based on marketing campaigns. | Developed a nested logical audit script using the **`IFS`** function:<br>`=IFS(L2="SAVE10", N2*0.90, L2="WINTER15", N2*0.85, TRUE, N2)` | Isolated raw promotional impacts from base sales performance by dynamically applying 10% and 15% discount deductions for active coupons. | **Resolved** |

---

## 📊 Final Descriptive Statistics Matrix

| Statistical Metric | Quantity | UnitPrice | TotalPrice |
| :--- | :---: | :---: | :---: |
| **Mean** | 2.95 | \$356.41 | \$1,053.97 |
| **Median** | 3.00 | \$364.21 | \$823.62 |
| **Mode** | 1.00 | \$127.18 | \$635.90 |
| **Minimum Value** | 1.00 | \$11.39 | \$11.39 |
| **Maximum Value** | 5.00 | \$699.93 | \$3,456.40 |

---

## 📂 Repository Deliverables

The following files have been finalized and committed to this repository for evaluation:
1. **`Dataset_Data_Analytics_Cleaned.xlsx`** 
   - *Sheet 1 (`Sheet1 (2)`):* The clean transaction matrix containing the newly engineered `Net-TotalProfit` formula.
   - *Sheet 2 (`EDA Summary`):* The executive dashboard containing live mathematical formulas linked directly to the records.
2. **`EDA_Summary_Report.pdf`**
   - The formal executive summary document formatted for management review, detailing data skewness, outlier rationalization, and detailed KPI definitions.

---
*Submitted as part of the DecodeLabs Industrial Training Portfolio - June 2026.*
