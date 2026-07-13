![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Room](https://img.shields.io/badge/Room-OWASP%20Top%2010%3A%20IAAA-blue)
![Category](https://img.shields.io/badge/Category-Web%20Security-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)



> **Key Finding:** Most of OWASP's highest-impact categories trace back to a breakdown somewhere in IAAA — Identity, Authentication, Authorization, or Accountability — proving that access control and logging failures aren't edge cases, they're the backbone of the Top 10.

## Overview

**Room:** OWASP Top 10 2025: IAAA Failures


This room frames three OWASP Top 10 categories through the lens of the IAAA model (Identity, Authentication, Authorization, Accountability): A01 Broken Access Control, A07 Identification and Authentication Failures, and A09 Security Logging and Alerting Failures. Each section pairs the theory with a hands-on exploitation task, requiring a captured flag as proof of exploitation.

## What I Actually Found

| Area | Details |
|---|---|
| Core Model | IAAA — Identity, Authentication, Authorization, Accountability |
| A01: Broken Access Control | Exploited an authorization flaw to access resources/functionality outside intended permissions; flag captured |
| A07: Identification & Authentication Failures | Exploited weaknesses in login/session handling to bypass or subvert the authentication process |
| A09: Security Logging & Alerting Failures | Identified gaps in logging/alerting that allowed malicious activity to go undetected |
| IAAA Mapping | Identity → who you claim to be; Authentication → proving it; Authorization → what you're allowed to do; Accountability → tying actions back to an identity via logs |

## Hands-On Activities

- Reviewed the IAAA model and mapped each of the four components (Identity, Authentication, Authorization, Accountability) to a corresponding real-world control (login credentials, MFA, access control lists, audit logs).
- Worked the **A01: Broken Access Control** challenge — identified an authorization weakness (e.g., missing server-side permission check) and exploited it to reach unauthorized data or functionality, capturing the required flag.
- Worked the **A07: Identification and Authentication Failures** challenge — targeted weak authentication logic (session/credential handling) to bypass the login mechanism.
- Worked the **A09: Security Logging and Alerting Failures** challenge — demonstrated how insufficient logging/alerting let an attack proceed without triggering detection.
- Connected each vulnerability class back to which IAAA pillar had actually failed, rather than treating them as unrelated OWASP categories.

## SOC Analyst Relevance

| OWASP Category | SOC Use Case |
|---|---|
| A01: Broken Access Control | Directly informs what to look for in access logs — requests to resources outside a user's normal permission scope |
| A07: Authentication Failures | Ties into monitoring for brute-force attempts, session token reuse, and anomalous login patterns |
| A09: Logging & Alerting Failures | Core to the SOC's own function — if this control fails, the SOC loses visibility into everything else on this list |
| IAAA framework | Gives analysts a consistent way to classify *why* an incident happened, not just *what* happened |
| Accountability pillar | Justifies why complete, tamper-resistant audit logging is a non-negotiable control, not a nice-to-have |

## Key Takeaways

- IAAA is a useful lens because it explains *root cause*: A01, A07, and A09 aren't three unrelated bugs — they're failures of Authorization, Authentication, and Accountability respectively.
- A09 (logging/alerting failure) is arguably the most dangerous of the three in practice, since it's what turns a contained incident into an undetected breach.
- Capturing flags for A01 and A07 reinforced that access control and authentication bugs are often simple logic flaws (missing checks, weak session handling) rather than exotic exploits.
- Thinking in terms of IAAA during an investigation makes it faster to ask the right question: was this an identity problem, an authentication bypass, an authorization gap, or a failure to log/alert on the activity at all?

---
📁 More writeups: [my writeups repo — add your link here]
