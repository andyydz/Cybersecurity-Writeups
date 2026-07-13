![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Room](https://img.shields.io/badge/Room-OWASP%20Top%2010%3A%20Secure%20Data%20and%20Links-blue)
![Category](https://img.shields.io/badge/Category-Web%20Security-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)



> **Key Finding:** Cryptographic failures, injection, and software/data integrity failures all boil down to the same broken assumption — trusting something that was never verified, whether that's an algorithm's strength, user input, or the integrity of a software update.

## Overview

**Room:** OWASP Top 10 2025: Secure Data and Links


This room covers three OWASP Top 10 categories centered on trust boundaries: A04 Cryptographic Failures, A05 Injection, and A08 Software and Data Integrity Failures. Each section defines the vulnerability, covers prevention strategies, and includes a hands-on practical with a flag to capture.

## What I Actually Found

| Category | What It Is | How to Prevent It |
|---|---|---|
| **A04: Cryptographic Failures** | Sensitive data exposed due to weak, missing, or misapplied cryptography (in transit or at rest) | Use strong, modern algorithms; enforce TLS everywhere; never roll custom crypto; proper key management and rotation |
| **A05: Injection** | Untrusted input is interpreted as code/commands by an interpreter — covers SQL injection, command injection, AI prompt injection, and server-side template injection (SSTI) | Treat all user input as untrusted by default; use parameterized queries/prepared statements; input validation and output encoding; sandbox/limit interpreter privileges |
| **A08: Software and Data Integrity Failures** | Code or data trusted without verifying its integrity — e.g., unsigned updates, insecure deserialization, unverified CI/CD pipeline artifacts | Use digital signatures/checksums to verify software and updates; secure CI/CD pipelines against tampering; avoid insecure deserialization of untrusted data |

## Hands-On Activities

- **A04 Cryptographic Failures:** Reviewed what qualifies as a cryptographic failure and why weak or misapplied crypto undermines confidentiality even when other controls hold. Completed the hands-on practical exploiting a cryptographic weakness and captured the flag.
- **A05 Injection:** Covered the injection family broadly — SQL injection, command injection, AI prompt injection, and server-side template injection (SSTI) — and reinforced the core prevention principle that *all user input must be treated as untrusted by default*. Worked through the practical exploiting an injection point and captured the flag.
- **A08 Software and Data Integrity Failures:** Defined what counts as an integrity failure (trusting unverified code, updates, or data), reviewed prevention methods (signing, checksums, secured pipelines), and completed the practical demonstrating an integrity-failure exploit, capturing the flag.
- Used TryHackMe's own room content as the reference/practice environment for all three sections.

## SOC Analyst Relevance

| Category | SOC Use Case |
|---|---|
| A04: Cryptographic Failures | Guides investigation of data-exposure incidents — was the "encrypted" data actually protected, or using a broken/legacy algorithm? |
| A05: Injection | The single most common web attack class in SOC alert queues — SQLi/command injection detection rules are core to most SIEM use cases |
| A05: AI Prompt Injection | An emerging category SOCs increasingly need to monitor as orgs deploy LLM-integrated features |
| A08: Software/Data Integrity Failures | Directly relevant to supply-chain and insider-threat investigations — unsigned/unverified updates are a common persistence and initial-access vector |
| "Untrusted by default" principle | The single mental model that generalizes across nearly all A05 detection and prevention work |

## Key Takeaways

- Injection remains dangerous specifically because it's a *category*, not a single bug — SQLi, command injection, SSTI, and AI prompt injection are all the same root failure applied to different interpreters.
- The rule "treat all user input as untrusted" is simple to state but the actual discipline of consistently applying it (validation, parameterization, encoding) is where most real-world injection vulnerabilities slip through.
- Cryptographic failures are easy to miss because "we use encryption" isn't the same as "we use encryption correctly" — algorithm choice and key management matter as much as the presence of encryption itself.
- Software/data integrity failures extend trust issues beyond user input to the software supply chain itself — verifying *what* runs is just as important as validating *what's sent*.
- Completing practicals for A04, A05, and A08 reinforced that these three categories, while conceptually different, are all exploitable through the same underlying gap: trust without verification.

---
