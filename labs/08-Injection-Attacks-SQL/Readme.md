# Lab 08 – Injection Attacks (SQL Injection)

## Objective

Understand how SQL Injection attacks exploit vulnerable web applications by interacting with the DVWA (Damn Vulnerable Web Application), extracting database information, and researching common SQL Injection mitigation techniques. :contentReference[oaicite:0]{index=0}

---

## Environment

- Operating System: Kali Linux
- Platform: Cisco Ethical Hacker Virtual Lab
- Target Application: DVWA (Damn Vulnerable Web Application)
- Attack Type: SQL Injection

---

## Activities Performed

- Configured DVWA security level to **Low**.
- Accessed the SQL Injection module.
- Tested SQL Injection payloads to bypass normal input validation.
- Enumerated database records using SQL queries.
- Identified the number of available columns.
- Retrieved the database version.
- Retrieved the active database name.
- Enumerated available tables from the target database.
- Reviewed SQL Injection mitigation techniques.

---

## Tools Overview

| Tool | Purpose |
|------|---------|
| DVWA | Practice environment for web application vulnerabilities |
| Web Browser | Interacting with the vulnerable application |
| SQL Injection Payloads | Extracting information from the backend database |

---

## Key Observations

- The application accepted unsanitized user input, making SQL Injection possible.
- SQL queries successfully returned multiple database records.
- UNION-based SQL Injection was used to retrieve database version information.
- Database enumeration revealed the active database and available tables.
- The lab demonstrated how improper input validation can expose sensitive backend information.

---

## Skills Practiced

- SQL Injection
- UNION-Based Injection
- Database Enumeration
- Web Application Security Testing
- Vulnerability Assessment
- Secure Coding Awareness

---

## Key Learnings

- SQL Injection occurs when user input is directly incorporated into SQL queries.
- Improper input validation allows attackers to manipulate backend database queries.
- Attackers can enumerate databases, tables, and application information through crafted SQL payloads.
- Parameterized queries and prepared statements significantly reduce SQL Injection risks.
- Proper input validation and least-privilege database permissions improve application security.

---

## Personal Reflection

This lab provided hands-on experience with SQL Injection in a controlled environment. I learned how attackers enumerate database information using SQL payloads and gained a better understanding of why secure coding practices, input validation, and parameterized queries are essential for protecting web applications.

---

## Disclaimer

This lab was completed in an authorized training environment for educational purposes only. All SQL Injection activities were performed against intentionally vulnerable systems within the lab environment and not against real-world targets.
