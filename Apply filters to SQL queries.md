# Apply Filters to SQL Queries

## Project Description

My organization is working to improve system security. It is my responsibility to ensure the system is secure, investigate potential security incidents, and update employee computers when necessary. Below are examples of how I used SQL queries with filters to accomplish security-related tasks.

---

## Retrieve After-Hours Failed Login Attempts

A potential security incident occurred after business hours (after **18:00**). All failed login attempts during this period need to be investigated.

### SQL Query:
```sql
SELECT * 
FROM log_in_attempts 
WHERE login_time > '18:00' 
AND success = FALSE;

Explanation:
login_time > '18:00' filters login attempts that occurred after 6 PM.
success = FALSE ensures only failed login attempts are retrieved.

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

SELECT * 
FROM log_in_attempts 
WHERE login_date = '2022-05-09' 
OR login_date = '2022-05-08';

Explanation:
login_date = '2022-05-09' retrieves logins on May 9, 2022.
OR login_date = '2022-05-08' ensures logins on May 8, 2022 are also included.

## Retrieve login attempts outside of Mexico

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

SELECT * 
FROM log_in_attempts 
WHERE country NOT LIKE 'MEX%';

Explanation:
NOT LIKE 'MEX%' filters login attempts from countries other than Mexico.
Since Mexico is represented as MEX or MEXICO in the database, MEX% covers both variations.

## Retrieve employees in Marketing

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

SELECT * 
FROM employees 
WHERE department = 'Marketing' 
AND office LIKE 'East%';

Explanation:
department = 'Marketing' filters employees in the Marketing department.
AND office LIKE 'East%' ensures only employees in the East building are included.

## Retrieve employees in Finance or Sales

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

SELECT * 
FROM employees 
WHERE department = 'Finance' 
OR department = 'Sales';

Explanation:
department = 'Finance' retrieves employees from Finance.
OR department = 'Sales' retrieves employees from Sales.


## Retrieve all employees not in IT

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the Information Technology department.

SELECT * 
FROM employees 
WHERE department <> 'IT';

department <> 'IT' ensures employees outside of IT are included. <<Can also use 'department != 'IT';' or 'NOT department = 'IT;'>>

## Summary

Throughout this project, I applied SQL filters to extract specific information from two key tables:

log_in_attempts (to investigate login activity)
employees (to identify computers that require updates)
I utilized AND, OR, and NOT operators to refine the results. Additionally, I used the LIKE operator with wildcard (%) patterns to account for variations in naming conventions.

This project highlights my ability to analyze security data with SQL and retrieve relevant insights to enhance system security.
