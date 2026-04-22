# Task 3: SQL Injection (DVWA Low Security)

## Objective
Demonstrate an SQL Injection vulnerability on a low-security web application.

## Execution
* **Target:** DVWA (`192.168.56.101`)
* **Payload Used:** `' OR '1'='1`

## Vulnerability Explanation
The application fails to sanitize user input before passing it to the database query. By injecting `' OR '1'='1`, the backend query logic is forced to evaluate to TRUE, causing the database to execute the query and dump all hidden user records.
