# students_performance_analytics





# 📊 Student Performance Data Analysis

This project explores how different factors affect student academic performance using **Excel**, **Power BI**, and **SQL**.  
It focuses on analyzing scores, demographics, and study habits to uncover meaningful patterns and insights.

---

## 🔧 Tools Used

- **Excel** – Data cleaning 
- **Power BI** – Interactive dashboards and slicers  
- **SQL** – Data querying and aggregation for deeper insights  

---

## 📁 Dataset Summary

Includes:
- **Demographic Fields**: Gender, Parental Education, Lunch Type  
- **Academic Fields**: Math Score, Reading Score, Writing Score  
- **Other Fields**: Study Hours, Test Preparation Course  

New columns created:
- `Total Score`
- `Average Score`
- `Pass/Fail` (Average Score ≥ 70)

---

## 📊 Excel Highlights

- Created calculated columns using formulas:
  - `Total Score = SUM(math_score, reading_score, writing_score)`
  - `Average Score = AVERAGE(math_score, reading_score, writing_score)`
  - `Pass/Fail = IF(Average Score ≥ 70, "Pass", "Fail")`
  
- Pivot Tables:
  - **Average Score by Gender**
  - **Pass Rate by Parental Education**
  - **Study Hours vs Final Result**
  - **Lunch Type and Performance**

- Charts used:
  - Column chart, pie chart, bar chart, line chart  
  - Conditional formatting for score levels and pass/fail icons  

---

## 📈 Power BI Features

- Pages created:
  - Overview
  - Gender & Education Breakdown
  - Study Time Analysis

- Used:
  - Slicers (Gender, Lunch Type, Test Prep)
  - Interactive bar/line/pie charts
  - Dynamic tooltips and filters

---

## 🧮 SQL Analysis

Sample queries included:

```sql
-- Average score by gender
SELECT gender, ROUND(AVG((math_score + reading_score + writing_score)/3), 2) AS avg_score
FROM students
GROUP BY gender;

-- Pass rate by parental education
SELECT parent_education,
       COUNT(CASE WHEN average_score >= 70 THEN 1 END) AS pass_count,
       COUNT(*) AS total,
       ROUND(COUNT(CASE WHEN average_score >= 70 THEN 1 END)*100.0/COUNT(*), 2) AS pass_rate
FROM students
GROUP BY parent_education;
