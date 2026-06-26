![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Log%20Analysis-blue?style=for-the-badge)



> **Key Finding:** Even the most careful attackers leave traces — logs are the digital footprints that let SOC analysts reconstruct exactly what happened, when, and sometimes who was behind it.

## Overview
This room covers the fundamentals of log analysis — what logs are, why they matter, and how to use them for security investigation. Includes hands-on tasks analysing Windows Event Logs via Event Viewer and web server access logs using `cat` and `grep` on a virtual machine.



---

## What I Actually Found

| Topic | Finding |
|---|---|
| Why logs matter | Even skilled attackers leave small traces — logs help reconstruct the full attack story |
| Use cases | Security monitoring, incident investigation, forensics, troubleshooting, performance monitoring, auditing, compliance |
| Types of logs | System, Audit, Security, Network, Access, Application |
| Windows log locations | Application, System, Security — viewed via Event Viewer → Windows Logs |
| Critical Event IDs | 4624, 4625, 4634, 4720, 4722, 4724, 4725, 4726 |
| Web log analysis tools | `cat` and `grep` used to filter and investigate access log entries |
| Web log fields | IP address, timestamp, request method, URL, status code |

---

## Hands-On Activities

### Windows Event Log Analysis
Connected to the lab virtual machine and opened **Event Viewer → Windows Logs → Security** to investigate security events.

#### Key Event IDs Reference

| Event ID | Description |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon attempt |
| 4634 | Account logoff |
| 4720 | User account created |
| 4722 | User account enabled |
| 4724 | Password reset attempted |
| 4725 | User account disabled |
| 4726 | User account deleted |

#### Investigation Tasks
Using Event Viewer, investigated the following:
- Identified what the system had based on logged security events
- Found which account was created by the target account (Event ID 4720)
- Determined the exact date the user account was enabled (Event ID 4722)
- Confirmed whether the account underwent a password reset (Event ID 4724)

### Web Service Access Log Analysis
Downloaded and analysed a web server access log file using terminal commands on the virtual machine.

Used `cat` to read the full log and `grep` to filter specific entries:

```bash
cat access.log
grep "POST" access.log
```

#### Investigation Tasks
- Identified the URL targeted by POST requests
- Found the IP address making suspicious requests
- Determined when the last POST request was made based on the timestamp field

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Windows Event Log analysis | Core skill for investigating authentication events and account changes in SOC |
| Critical Event ID knowledge | Instantly recognising suspicious events like failed logins and account creation |
| Web access log analysis | Identifying malicious web requests, scanning activity, and data exfiltration attempts |
| grep for log filtering | Efficient log triage — filtering thousands of entries to find relevant events fast |
| Forensic log investigation | Reconstructing attacker activity from log evidence during incident response |
| Audit and compliance logs | Understanding log types used to meet regulatory requirements |

---

## Key Takeaways

- Logs are the most reliable source of truth during a security investigation — they capture what actually happened
- Even sophisticated attackers leave traces — log analysis is how SOC analysts find those footprints
- Different log types serve different purposes — security logs for auth events, network logs for traffic, application logs for service behaviour
- Windows Event IDs 4624, 4625, and 4720 are among the most critical for SOC monitoring
- `cat` and `grep` are essential command-line tools for fast log triage in Linux environments
- Web access logs reveal IP addresses, timestamps, HTTP methods, and URLs — enough to reconstruct an attack
- Log analysis is the foundation of both incident response and digital forensics

---

*Part of my [TryHackMe Writeups](https://github.com/andyydz/TryHackMe-Writeups) portfolio — documenting my SOC analyst journey.*
