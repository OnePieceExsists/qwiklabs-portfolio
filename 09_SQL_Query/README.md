# Lab 09: Perform a SQL Query

> **Platform:** Qwiklabs  
> **Skill Area:** SQL, Databases, Security Analysis  
> **Date Completed:** 23-09-2025  
> **Difficulty:** Introductory  

---

## 📝 Overview
In this lab, I practiced using **SQL queries** to retrieve, filter, and order information from relational database tables.  
As a security analyst, querying databases helps identify vulnerable systems, investigate login activities, and detect suspicious behavior.  

---

## 🎯 Objectives
- Use `SELECT` and `FROM` to retrieve data from tables.  
- Retrieve specific columns from a database table.  
- Use the `*` wildcard to select all data from a table.  
- Apply `ORDER BY` to sort query results by date and time.  
- Analyze login attempts for unusual or suspicious activity.  

---

## 🚀 What I Did

### Task 1: Retrieve Employee Device Data
* I retrieved all device records from the `machines` table:

![Task 1.1 – Select all](screenshots/01_1_all.png)

SELECT * 
FROM machines;
I selected specific columns (device_id and email_client) to focus on email client usage:

SELECT device_id, email_client 
FROM machines;

![Task 1.2 – Device ID and Email Client](screenshots/01_2_Device_ID_and_Email_Client.png)

I selected operating system details and patch dates:

SELECT device_id, operating_system, OS_patch_date 
FROM machines;

![Task 1.3 – OS and Patch Date](screenshots/01_3_OS_and_Patch_Date.png)

### Task 2: Investigate Login Activity
I investigated login locations:


SELECT event_id, country 
FROM log_in_attempts;

![Task 2.1 – Login Locations](screenshots/02_1_Login_Locations.png)

I checked login attempts outside normal hours by selecting usernames, dates, and times:


SELECT username, login_date, login_time 
FROM log_in_attempts;

![Task 2.2 – Username, Date, and Time](screenshots/02_2_Username_Date_and_Time.png)

Finally, I displayed all login attempt data:


SELECT * 
FROM log_in_attempts;

![Task 2.3 – Select all columns](screenshots/02_3_select_all_columns.png)

### Task 3: Order Login Attempts Data
I sorted login attempts by date:

SELECT * 
FROM log_in_attempts
ORDER BY login_date;

![Task 3.1 – Ordered by Date](screenshots/03_1_ Ordered_by_Date.png)

I further ordered the results by login time:

SELECT * 
FROM log_in_attempts
ORDER BY login_date, login_time;

![Task 3.2 – Ordered by Date and Time](screenshots/03_2_Ordered_by_Date_and_Time.png)


✅ Results

Successfully queried all device and login attempt records.

Retrieved targeted data using SELECT with specific columns.

Verified unusual login activity outside expected regions.

Ordered results by both date and time for accurate analysis.

💡 Lessons Learned

SELECT * retrieves all data, while specifying columns improves focus.

ORDER BY helps organize large datasets for investigation.

SQL queries are essential for identifying system vulnerabilities and security incidents.

📜 Evidence
Screenshots for each task are stored in the screenshots/ folder.

🔗 References
Qwiklabs Lab Link:
https://www.cloudskillsboost.google/focuses/44042687?parent=lti_session&parent=lti_session
