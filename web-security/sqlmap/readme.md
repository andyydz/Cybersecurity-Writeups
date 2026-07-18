# SQLMap

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Category](https://img.shields.io/badge/Category-Web%20Security-blue)

This folder contains my notes and write-up on **SQLMap**, an automated tool for detecting and exploiting SQL injection vulnerabilities in web applications.

## Overview

SQLMap takes a target URL or request and automates the process of testing injection points, identifying the underlying database, and extracting data — turning what would be manual, tedious SQL injection testing into a fast, repeatable process.

## Writeup

 `sqlmap-the-basic.md` — Covers the fundamentals of running SQLMap against a target, identifying injectable parameters, and using it to enumerate databases, tables, and data.

## SOC Analyst Relevance

SQLMap traffic has a recognizable pattern — a high volume of rapid, sequential requests containing SQL syntax and payload variations against the same endpoint — making it an important signature to recognize when triaging web application attack alerts.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
