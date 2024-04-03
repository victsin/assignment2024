use employees;
show tables;
select * from emp_attrition;
SELECT 
    JobRole,
    Gender,
    EducationField,
    AVG(MonthlyIncome) AS Average_MonthlyIncome,
    MAX(MonthlyIncome) AS Max_MonthlyIncome,
    MIN(MonthlyIncome) AS Min_MonthlyIncome,
    AVG(YearsAtCompany) AS Average_YearsAtCompany,
    COUNT(*) AS Employee_Count
FROM 
    emp_attrition
WHERE 
    JobSatisfaction <= 3
GROUP BY 
    JobRole, 
    Gender, 
    EducationField
HAVING 
    COUNT(*) > 5;
