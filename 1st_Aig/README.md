# A Detailed Guide to SQL Injection Attacks

This guide provides a comprehensive overview of SQL injection attacks.
---

## 1. What is SQL Injection?

**SQL Injection (SQLi)** is a code injection technique that exploits a vulnerability in a web application's software. By manipulating SQL queries, an attacker can trick the application into executing malicious commands, allowing them to retrieve, modify, or delete data from the underlying database.

---

## 2. Types of SQL Injection Attacks

The video categorizes SQL injection into three primary types:

### In-band SQLi
This type of attack is where the attacker can see the results of their malicious SQL query directly on the web page. This includes:
* **Union-based Attacks**: The attacker uses the `UNION SELECT` statement to combine a malicious query with a legitimate one, forcing the database to display its contents on the page.
* **Error-based Attacks**: The attacker triggers a database error that reveals information about the database structure in the error message.

### Inferential (Blind) SQLi
With this type of attack, no data is returned on the web page. Instead, the attacker infers information about the database by observing the application's behavior or response time. This includes:
* **Boolean-based Attacks**: The attacker sends queries that return a true or false result, and the application responds differently for each case, revealing information.
* **Time-based Attacks**: The attacker uses queries that cause a time delay in the server's response if a condition is met.

### Out-of-band SQLi
This is a more advanced type of attack where the attacker sends data to a different channel (e.g., DNS or HTTP) to retrieve the information. This method was not demonstrated in the video.

---

## 3. Practical Demonstration: Exploiting SQLi Vulnerabilities

The video includes practical demonstrations of several SQL injection techniques on a vulnerable web application, starting with a setup in Kali Linux.

### A. Union-based SQLi
* **Goal**: To force the database to display its name on the web page.
* **Payload**: `1' UNION SELECT null, database()-- -`
* **Result**: The database name is displayed on the screen, confirming the vulnerability.

### B. Always True Condition
* **Goal**: To bypass the login form and gain administrative access to the website without a password.
* **Payload**: `' OR '1'='1`
* **Result**: The `OR '1'='1'` part of the payload evaluates to true, causing the SQL query to always succeed and grant the attacker access as an administrator.

### C. Time-based Blind SQLi
* **Goal**: To confirm that the database is vulnerable by causing a noticeable delay in the page's response.
* **Payload**: `' AND IF(1=1, SLEEP(5), 0)-- -`
* **Result**: The `SLEEP(5)` command causes a 5-second delay, which confirms that the database is vulnerable to time-based attacks.

The video also briefly touches on passive information gathering by demonstrating how to use a tool to create and send phishing links that can capture a target's location, camera, and microphone access. It also shows how a broken access control vulnerability could allow an attacker to view internal files by changing URL paths.

---
