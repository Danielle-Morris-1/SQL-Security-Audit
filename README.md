# SQL Security Audit

## Scope

In this project, I conducted a security audit for a fictional organization's internal systems by querying and analyzing authentication and device data. My responsibilities included securing systems against unauthorized access, investigating suspicious login activity, and auditing employee devices for compliance. I leveraged SQL queries with filtering techniques to examine the `log_in_attempts` and `employees` tables, identifying after-hours anomalies, and supporting endpoint patch management initiatives.

The `log_in_attempts` table had the following columns:

![image](https://github.com/user-attachments/assets/19083bfb-bee1-40b3-b092-cb60381965d2)

The `employees` table had the following columns:

![image](https://github.com/user-attachments/assets/ba17a9e5-fdfb-435b-930a-e396dd982c65)

---

## 📑 Table of Contents
- [Technology Utilized](#technology-utilized)
- [Objectives](#objectives)
- [Key Actions & Investigation Process](#key-actions--investigation-process)
- [Skills Demonstrated](#skills-demonstrated)
- [Final Reflection 🧠](#final-reflection-)

---
## Technology Utilized 

- **SQL Server** — For querying and analyzing authentication data.
- **Cybersecurity Principles** — To interpret suspicious behaviors and data patterns.

---

## Objectives

- Identify unauthorized or suspicious login attempts within SQL Server databases.
- Apply filters to isolate specific user behaviors or anomalies.
- Support internal investigations related to potential insider threats.
- Provide actionable insights to the IT security team regarding system vulnerabilities and access patterns.

---

## Key Actions & Investigation Process

### 🔐 After-Hours Failed Login Attempts
- Investigated suspicious activity that occurred after the organization’s business hours.
- Retrieved all failed login attempts **after business hours** (after 18:00).
- SQL filters used:  
  ```sql
  WHERE login_time > '18:00' AND success = FALSE**

<details>
<summary>SQL Query Results</summary>
  
![image](https://github.com/user-attachments/assets/cee3c49f-a444-4bfe-ba89-3dc2bfbcd038)
</details>

### 🗓️ Suspicious Login Attempts by Date
- Investigated all login activity on May 8th and 9th, 2022 related to a potential breach.
- SQL filters used:
  ```sql
  WHERE login_date = '2022-05-08' OR login_date = '2022-05-09'

<details>
<summary>SQL Query Results</summary>
  
![image](https://github.com/user-attachments/assets/4e8ea17b-63b7-4ca9-845f-80639df77570)
</details>

### 🌎 Login Attempts Outside of Mexico
- Investigated suspicious activity with login attempts, and it was determined that this activity happened outside of Mexico.
- Filtered all login attempts originating outside Mexico to isolate suspicious geographic activity.
- SQL filters used:
  ```sql
  WHERE country NOT LIKE 'MEX%'

<details>
<summary>SQL Query Results</summary>
  
![image](https://github.com/user-attachments/assets/0cde470b-045e-48ac-83c3-8421b77999a5)
</details>

### 🏢 Device Audit: Marketing Department
- Gathered employee device data from the Marketing department specifically in the East office.
- SQL filters used:
  ```sql
  WHERE department = 'Marketing' AND office_location LIKE 'East%'

<details>
<summary>SQL Query Results</summary>
  
![image](https://github.com/user-attachments/assets/f360186c-8935-418c-9cd5-d79b41ffb4cf)
</details>

### 💼 Device Audit: Finance and Sales Departments
- Retrieved device data for employees in Finance and Sales to support department-wide security updates.
- SQL filters used:
  ```sql
  WHERE department = 'Finance' OR department = 'Sales'

<details>
<summary>SQL Query Results</summary>
  
![image](https://github.com/user-attachments/assets/0fe68a1f-6b38-4992-b2bd-34d496a51b91)
</details>

### 🚫 Excluding IT Department
- Identified employee devices outside of the IT department for broader security patching.
- SQL filters used:
  ```sql
  WHERE department NOT LIKE 'Information Technology'

<details>
<summary>SQL Query Results</summary>

  ![image](https://github.com/user-attachments/assets/ec65a945-158b-4b33-b5c7-8b645eb5ce96)

</details>

---

## Skills Demonstrated

- SQL Query and Filtering
- Data Analysis for Cybersecurity Investigations
- Critical Thinking for Threat Detection

---

## Final Reflection 🧠

This project strengthened my ability to extract actionable security insights from large datasets using SQL.  
It also emphasized the importance of cross-team communication in cybersecurity — bridging technical analysis with clear, non-technical reporting that enables faster remediation and risk reduction across the organization.

---

## 🚀 Project Status

![Status](https://img.shields.io/badge/Status-Completed-2ea44f)
![SQL](https://img.shields.io/badge/Skill-SQL-blue)
![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-blueviolet)
![Investigation](https://img.shields.io/badge/Skill-Data%20Analysis-brightgreen)

---

> 🔐 *"Security isn't a destination — it's a continuous journey."*

