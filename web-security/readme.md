# Web Security

This folder contains my notes and write-ups from web security rooms completed on TryHackMe — covering common web vulnerabilities, offensive tooling used to discover and exploit them, and the OWASP Top 10 as a framework for understanding application risk.

---

## Folder Structure

| Folder | Focus |
|---|---|
| `burp-suite` | Using Burp Suite to intercept, inspect, and manipulate web traffic |
| `gobuster` | Directory and file enumeration on web servers |
| `sqlmap` | Automated SQL injection detection and exploitation |

---

## OWASP Top 10 Write-ups

| File | Topic |
|---|---|
| `owasp-top10-application-design-flaws.md` | Vulnerabilities rooted in insecure application design |
| `owasp-top10-iaaa.md` | Identification, Authentication, Authorization, and Accountability (IAAA) failures |
| `owasp-top10-secure-data-and-links.md` | Secure handling of data and links — covering issues like cryptographic failures and insecure references |

---

## Why This Matters

Web applications remain one of the most common attack surfaces, and understanding the OWASP Top 10 alongside the tools attackers actually use — Burp Suite for traffic manipulation, Gobuster for enumeration, SQLMap for injection — builds the practical skill needed to both find these issues offensively and recognize them defensively during SOC investigation.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
