# Lab 12: Activity – Filter with AND, OR, and NOT

> **Platform:** Qwiklabs  
> **Skill Area:** SQL, Databases, Security Analysis, Query Filtering  
> **Date Completed:** 24-09-2025  
> **Difficulty:** Introductory  

---
## Overview

In this lab, I’ll practice filtering SQL queries using `AND`, `OR`, and `NOT` operators to retrieve specific data from a database.  
This includes filtering login attempts, employees, and department records.

---

## Task 1: Retrieve after hours failed login attempts  
Use the `AND` operator to get failed login attempts after `18:00`.

sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
![Task 1 – Failed login attempts after 18:00](screenshots/01_failed_login_attempts.png)

### Task 2: Retrieve login attempts on specific dates
Use the OR operator to get login attempts on 2022-05-08 or 2022-05-09.

sql
SELECT * 
FROM log_in_attempts 
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
![Task 2 – Attempts made on 8th or 9th](screenshots/02_atempts_on_8_and_9.png)

### Task 3: Retrieve login attempts outside of Mexico
Use the NOT and LIKE operators to exclude logins from Mexico.

sql
SELECT * 
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
![Task 3 – Country not Mexico](screenshots/03_not_like_mex.png)

### Task 4: Retrieve employees in Marketing
Filter employees in the Marketing department located in the East building.

sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East-%';
![Task 4 – Department Marketing, offices in East building 170 and 320](screenshots/04_office_east_170_or_320.png)

### Task 5: Retrieve employees in Finance or Sales
Use the OR operator to return employees from Finance or Sales.

sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
![Task 5 – Employees in Finance and Sales departments](screenshots/05_department_finances_or_sales.png)

### Task 6: Retrieve all employees not in IT
Use the NOT operator to exclude employees in Information Technology.

sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
![Task 6 – Employees not in the IT department](screenshots/06_not_it_department.png)

✅ Conclusion
In this lab, I practiced using:

AND, OR, and NOT operators

LIKE for pattern matching

📜 Evidence
All screenshots are saved in the screenshots/ folder with names per task and subtask.

🔗 References
Qwiklabs Lab Link:
https://www.cloudskillsboost.google/focuses/44052295?parent=lti_session&parent=lti_session