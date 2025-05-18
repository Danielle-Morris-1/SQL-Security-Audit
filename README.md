
# SQL Threat Hunting for Unauthorized Access

## Scope

In this project, I performed threat hunting activities on a fictional organization's internal systems by querying and analyzing authentication and device data using SQL. My focus was on identifying potential unauthorized access attempts and suspicious login activity. I leveraged SQL queries with filtering techniques on the `log_in_attempts` and `employees` tables to investigate after-hours anomalies. While not a full security audit, this initiative aimed to proactively identify and flag potentially malicious behavior.

The `log_in_attempts` table:

![image](https://github.com/user-attachments/assets/19083bfb-bee1-40b3-b092-cb60381965d2)

The `employees` table:

![image](https://github.com/user-attachments/assets/ba17a9e5-fdfb-435b-930a-e396dd982c65)

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

Query Input 🔽
 
  ```sql
  WHERE login_time > '18:00' AND success = FALSE**
  ```

SQL Output ⏬
  
![image](https://github.com/user-attachments/assets/cee3c49f-a444-4bfe-ba89-3dc2bfbcd038)

---

### 🗓️ Suspicious Login Attempts by Date
- Investigated all login activity on May 8th and 9th, 2022 related to a potential breach.

Query Input 🔽
 
  ```sql
  WHERE login_date = '2022-05-08' OR login_date = '2022-05-09'
  ```

SQL Output ⏬

![image](https://github.com/user-attachments/assets/4e8ea17b-63b7-4ca9-845f-80639df77570)

---

### 🌎 Login Attempts Outside of Mexico
- Investigated suspicious activity with login attempts, and it was determined that this activity happened outside of Mexico.
- Filtered all login attempts originating outside Mexico to isolate suspicious geographic activity.

Query Input 🔽
  
  ```sql
  WHERE country NOT LIKE 'MEX%'
  ```

SQL Output ⏬
  
![image](https://github.com/user-attachments/assets/0cde470b-045e-48ac-83c3-8421b77999a5)


---

### 🏢 Device Audit: Marketing Department
- Gathered employee device data from the Marketing department specifically in the East office.

Query Input 🔽
 
  ```sql
  WHERE department = 'Marketing' AND office_location LIKE 'East%'
  ```

SQL Output ⏬
  
![image](https://github.com/user-attachments/assets/f360186c-8935-418c-9cd5-d79b41ffb4cf)

---

### 💼 Device Audit: Finance and Sales Departments
- Retrieved device data for employees in Finance and Sales to support department-wide security updates.

Query Input 🔽
 
  ```sql
  WHERE department = 'Finance' OR department = 'Sales'
  ```

SQL Output ⏬
  
![image](https://github.com/user-attachments/assets/0fe68a1f-6b38-4992-b2bd-34d496a51b91)


---

### 🚫 Excluding IT Department
- Identified employee devices outside of the IT department for broader security patching.

Query Input 🔽
 
  ```sql
  WHERE department NOT LIKE 'Information Technology'
  ```

SQL Output ⏬

  ![image](https://github.com/user-attachments/assets/ec65a945-158b-4b33-b5c7-8b645eb5ce96)

---

## Suggested Remediations

* **Implement stronger password policies:** Enforce complexity requirements and regular password changes to mitigate brute-force attacks.
* **Enable Multi-Factor Authentication (MFA):** For all user accounts to add an extra layer of security and prevent unauthorized access even if passwords are compromised.
* **Implement geographical access controls:** Restrict login attempts to specific countries or regions based on legitimate user locations.
* **Monitor for unusual login activity:** Implement alerts in SIEM or monitoring tools for failed logins outside of business hours or from unexpected locations.
* **Regularly audit user accounts and permissions:** Ensure that users only have the necessary access privileges.
* **Investigate any anomalies promptly:** Establish clear procedures for investigating and responding to suspicious login attempts.
* **Enhance endpoint security:** Ensure all devices have up-to-date antivirus and EDR solutions to prevent compromise.

---

## Lessons Learned 🧠

This project reinforced the value of SQL in proactive threat hunting and security investigations. Key takeaways include:

* **SQL's power in data analysis:** Its efficiency in filtering and extracting specific information from large datasets is crucial for identifying anomalies.
* **The importance of context:** While SQL queries can highlight suspicious activity, understanding the organizational context (e.g., normal business hours, employee locations) is vital for accurate interpretation.
* **Actionable insights for security improvements:** The findings from threat hunting exercises can directly inform the implementation of stronger security controls and policies.
* **Collaboration is key:** Sharing these findings with the IT security team enables timely remediation and strengthens the overall security posture.
  
---

## 🚀 Project Status

![Status](https://img.shields.io/badge/Status-Completed-2ea44f)
![SQL](https://img.shields.io/badge/Skill-SQL-blue)
![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-blueviolet)
![Investigation](https://img.shields.io/badge/Skill-Data%20Analysis-brightgreen)

---

> 🔐 *"Security isn't a destination — it's a continuous journey."*

