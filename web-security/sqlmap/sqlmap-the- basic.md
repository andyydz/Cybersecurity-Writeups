![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Web%20Application%20Basics-blue)



>  **Key Finding:** SQLMap automates what a manual SQL injection payload (like `' OR 1=1--`) does by hand — detecting injectable parameters, then enumerating databases, tables, and credentials without writing a single query yourself.

## Overview

Room: **SQLMap: The Basics**
Room Link: [TryHackMe - SQLMap: The Basics](https://tryhackme.com/room/sqlmapthebasics)

This room covers how web applications interact with backend database servers, how SQL injection vulnerabilities arise, and how to use SQLMap to automate detection and exploitation of SQLi instead of crafting payloads manually.

## What I Actually Found

| Area | Details |
|------|---------|
| Architecture | Web server ↔ database server — user input from web forms gets passed into backend SQL queries |
| Vulnerability Class | SQL Injection (SQLi) — unsanitized input alters the intended SQL query logic |
| Manual Injection Example | Login bypass using logic like `' OR 1=1--` to make the WHERE clause always evaluate true |
| Underlying Query Logic | Queries structured like `SELECT * FROM users WHERE username='<input>' AND password='<input>'` |
| Tool | SQLMap — automated SQL injection detection & exploitation tool |
| Tool Modes | Manual command-line usage and SQLMap Wizard (guided/simplified mode) |
| Objective | Enumerate number of databases in the target application and extract a password |

## Hands-On Activities

**1. Introduction — Web & Database Servers**
Reviewed how a typical web application works — the web server handles requests and hands off user input (like login form fields) to a backend database server, which runs SQL queries to validate or retrieve data.

**2. Understanding SQL Injection**
Learned how SQLi vulnerabilities occur when user input is inserted directly into a SQL query without sanitization. Walked through the classic authentication bypass logic:
- Query structured as: `SELECT * FROM users WHERE username='<input>' AND password='<input>'`
- Injecting `' OR 1=1--` into the username field breaks out of the intended string and appends a condition that is always true, bypassing the password check entirely and returning valid credentials/access.

**3. Manual vs. Automated SQL Injection**
Understood why manual SQLi (crafting payloads by hand) doesn't scale well against complex applications, setting up the case for using an automated tool like SQLMap.

**4. Introduction to SQLMap**
Covered SQLMap's role as an automated SQL injection detection and exploitation tool — capable of identifying injectable parameters, fingerprinting the database type, and extracting data (databases, tables, columns, credentials) without manual query crafting.

**5. SQLMap Wizard**
Used SQLMap's **Wizard** mode — a simplified, guided interface for running SQLMap against a target URL without needing to remember every command-line flag manually.

**6. Practical Exercise**
Ran SQLMap against the target web application to:
- Enumerate the **number of databases** present on the backend
- Drill down into a specific database to extract table data
- Retrieved a **user password** from the compromised database

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| SQLi logic (`OR 1=1`-style payloads) | Recognizing classic SQLi signatures in WAF/web server logs |
| Web-to-database query flow | Understanding where injection risk lives in an application's architecture |
| SQLMap automated scanning | Identifying SQLMap's distinctive request patterns (rapid, sequential, parameter-fuzzing requests) as a scanning indicator |
| Database/credential enumeration | Knowing what a successful SQLi compromise looks like from the data-exfiltration side |
| Wizard vs. manual tool use | Recognizing that even low-skill attackers can achieve serious impact via automated tooling |

## Key Takeaways

- SQL injection remains one of the most impactful and common vulnerability classes — a single unsanitized input field can expose an entire database.
- SQLMap's automation means even unsophisticated attackers can escalate a simple injectable parameter into full database compromise quickly — this raises the urgency of detecting SQLi attempts early.
- The distinctive volume and pattern of SQLMap's requests (many rapid variations against the same parameter) is a strong log-level indicator worth alerting on.
- Input validation and parameterized queries on the application side remain the most effective root-cause fix — detection is a safety net, not a substitute for secure coding.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups
