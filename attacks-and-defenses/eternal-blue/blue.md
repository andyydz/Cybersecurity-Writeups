![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Exploitation%20Basics-blue)

> **Key Finding:** "Blue" walks through the classic EternalBlue (MS17-010) SMB exploitation chain end-to-end — from initial port recon to gaining a shell, dumping and cracking password hashes with John the Ripper, and capturing flags across the compromised host.

## Overview

Room: **Blue**

This room is a full offensive lifecycle exercise — reconnaissance, exploitation via the EternalBlue SMB vulnerability, credential harvesting, privilege escalation, and offline password cracking — capped off with flag hunting across the target.

## What I Actually Found

| Area | Details |
|------|---------|
| Target | Windows machine vulnerable to MS17-010 (EternalBlue) |
| Recon | Port scan revealed open SMB-related ports on the target |
| Initial Access | Exploited SMB vulnerability to gain a session |
| Credential Access | Harvested password hashes from the compromised system |
| Privilege Escalation | Escalated privileges within the active session |
| Cracking Tool | John the Ripper used to crack harvested hashes offline |
| Objective | Locate and submit flags placed across the filesystem |

## Hands-On Activities

**1. Reconnaissance**
Started the target VM and ran a port scan to enumerate open ports and services, identifying SMB as the exposed and vulnerable service to target — a step used to answer "how many ports are open" before moving to exploitation.

**2. Gaining Access**
Used the identified SMB vulnerability (EternalBlue/MS17-010) to exploit the target and establish an initial Meterpreter session on the host.

**3. Harvesting Credentials**
From the active session, dumped the local password hashes stored on the compromised machine for offline cracking.

**4. Privilege Escalation**
Worked within the session to escalate privileges, moving from the initial foothold to a higher-privilege context on the target.

**5. Cracking Hashes with John the Ripper**
Took the harvested hashes offline and ran John the Ripper against them, successfully cracking the password(s) needed to fully compromise the account(s).

**6. Flag Hunting**
Searched the compromised filesystem for flags planted throughout the challenge, submitting each one to complete the room.

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| SMB port/service recon | Recognizing SMB scanning as a precursor to EternalBlue-style attacks |
| MS17-010 exploitation awareness | Understanding a historically critical, still-relevant vulnerability class (WannaCry/NotPetya lineage) |
| Credential harvesting via session | Knowing what a compromised host's hash dump looks like in logs/EDR alerts |
| Privilege escalation in a live session | Spotting privilege escalation attempts in Windows event logs |
| John the Ripper offline cracking | Understanding attacker capability once hashes are exfiltrated — reinforces why hash exposure is a critical finding |

## Key Takeaways

- EternalBlue (MS17-010) remains one of the most important vulnerabilities to understand — it powered WannaCry and NotPetya, and unpatched SMB is still found in the wild today.
- The full attack chain — recon → exploit → harvest → escalate → crack — mirrors exactly what a SOC needs to reconstruct during incident response, making this a great end-to-end mental model.
- Offline cracking with John the Ripper reinforces why hash dumps must be treated as a critical severity event, not just a "credentials exposed" footnote.
- SMB hardening (patching, disabling SMBv1) is a simple, high-impact control directly tied to this entire attack class.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
