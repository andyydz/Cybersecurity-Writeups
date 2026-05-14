# Database & SQL Basics - TryHackMe Write-up

## Overview
This room introduced the fundamentals of databases and SQL (Structured Query Language) and provided hands-on experience interacting with database systems through practical exercises in a virtual machine environment.

The module focused on understanding how databases store information using tables, rows, and columns, along with learning how SQL queries are used to retrieve and manage data.

Databases are widely used across enterprise systems, web applications, cloud platforms, and cybersecurity environments, making SQL knowledge valuable for both IT and security professionals.

---

# Topics Covered
- Introduction to Databases & SQL
- Understanding Tables, Rows, and Columns
- Writing the First SQL Query
- Database Structure Fundamentals
- Querying Data Using SQL
- Virtual Machine Practical Exercises
- Data Management Concepts
- Conclusion and Key Takeaways

---

# What I Learned
Through this room, I gained foundational knowledge of relational databases and learned how SQL is used to interact with stored data.

Some of the major concepts learned include:
- Understanding database structures
- Learning how tables organize data
- Understanding rows and columns
- Writing basic SQL queries
- Retrieving information from databases
- Understanding how databases support modern applications

The room also improved my understanding of how databases are used in enterprise environments and cybersecurity operations.

---

# Hands-on Experience

During the practical exercises, I interacted with a virtual machine environment and practiced running basic SQL queries against database tables.

## Practical Activities
- Exploring database tables
- Viewing rows and columns
- Writing beginner SQL queries
- Retrieving stored data
- Understanding structured data storage
- Interacting with database environments

This hands-on experience improved my familiarity with database systems and SQL query fundamentals.

---

# SQL Concepts Explored

## Tables, Rows & Columns

Databases organize information into tables.

- **Tables** store related information
- **Rows** represent individual records
- **Columns** represent categories or attributes of data

### Example

| ID | Name   | Role          |
|----|--------|---------------|
| 1  | Andrew | SOC Analyst   |
| 2  | John   | Administrator |

---

## Basic SQL Query

SQL queries are used to retrieve and interact with stored information.

### Example

```sql
SELECT * FROM users;
```

This query retrieves all records from the `users` table.

---

# Access Services & Database Interaction

This room helped build an understanding of how systems interact with databases and how users retrieve stored information securely.

## Access Services Involved
- Database access through SQL queries
- Data retrieval mechanisms
- User interaction with database systems
- Structured data management
- Query-based information access

Understanding these services is important because many enterprise applications and security systems rely heavily on databases.

---

# SOC & Cybersecurity Applications

Database and SQL knowledge is valuable in cybersecurity because security analysts often investigate logs, alerts, and stored data inside database systems.

## SOC Analyst Applications
SQL skills are useful for:
- Searching security-related data
- Reviewing stored logs
- Investigating suspicious activity
- Querying alert databases
- Retrieving incident-related information

### Example
A SOC Analyst may use SQL to:
- Search login records
- Investigate failed authentication attempts
- Retrieve suspicious user activity
- Analyze stored security events
- Query SIEM-related databases

---

# Threat Investigation Applications

SQL knowledge supports incident response and threat investigations involving stored data.

## Threat Investigation Tasks
Security professionals may:
- Search for suspicious records
- Investigate unusual database activity
- Analyze login patterns
- Review compromised account activity
- Examine application logs stored in databases

### Example

```sql
SELECT username, login_time
FROM logins
WHERE status = 'failed';
```

This query could help analysts identify failed login attempts during investigations.

---

# System & Enterprise Applications

Databases are widely used across enterprise systems and applications.

## Real-world Applications
- Web applications
- Banking systems
- Enterprise software
- Cloud platforms
- Security monitoring systems
- SIEM platforms

SQL helps organizations efficiently store, manage, and retrieve large amounts of information.

---

# Job-Oriented Skills Gained

This room helped strengthen foundational skills relevant to:
- SOC Analyst
- Cybersecurity Analyst
- Database Administration
- IT Support
- Security Operations
- Backend & Data Fundamentals

## Technical Skills Developed
- Database fundamentals
- SQL query basics
- Structured data understanding
- Data retrieval concepts
- Basic analytical thinking
- Virtual machine interaction

---

# Key Takeaways
- Databases organize and manage structured information
- SQL is widely used for querying and retrieving data
- Database knowledge supports cybersecurity investigations
- SQL helps analyze logs and security-related records
- Understanding databases improves technical problem-solving skills

---

# Platform
TryHackMe

# Room
Database & SQL Basics

# Status
Completed Successfully
