# Power BI + SQL - Top 3 Employee Salary by Department

## 📌 Objective
To extract Top 3 highest salary employees per department using SQL Window functions, export to Power BI and visualize insights.

🔗 **Live Dashboard:**  
https://app.powerbi.com/reportEmbed?reportId=4b34d3ca-c786-4a32-b504-0ef5cbba886a&autoAuth=true&ctid=68fa027e-d599-4724-8870-99bdcaded2f9&actionBarEnabled=true

## ✅ Steps Performed
1. Queried SQL Server using ROW_NUMBER() & RANK() window functions.
2. Filtered Top 3 salary employees per department.
3. Exported results to Power BI and built interactive visual.

## 🧠 SQL Query
```sql
SELECT *
FROM (
    SELECT 
        e.Name,
        d.DepartmentName,
        e.Salary,
        RANK() OVER(PARTITION BY d.DepartmentName ORDER BY e.Salary DESC) AS SalaryRank
    FROM Employees e
    INNER JOIN Departments d
        ON e.DepartmentID = d.DepartmentID
) ranking
WHERE SalaryRank <= 3;

## 🔧 Tools Used
Power BI, SQL Server (SSMS), SQL Window Functions, Data Modeling

## 📁 Files Included
- Top 3 salary dashboard.pbix
- Screenshots
- Top3_Salary_SQL_Query.txt
- README.md


Publish using:
**File → Publish → Power BI Service**


