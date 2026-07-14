![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-SIEM-blue)



>  **Key Finding:** Without a SIEM, logs exist "everywhere but nowhere" — scattered across hosts, network devices, and servers with no correlation — SIEM solves this by centralizing, normalizing, and correlating logs into alerts that map directly to real (or false-positive) incidents.

## Overview

Room: **Introduction to SIEM**

This room covers SIEM fundamentals — what SIEM stands for, the different log source types (host-centric vs. network-centric), core SIEM features, and a hands-on investigation identifying whether a triggered alert was a true or false positive.

## What I Actually Found

| Area | Details |
|------|---------|
| SIEM Meaning | Security Information and Event Management |
| Core Problem SIEM Solves | Logs exist across every device/network segment but aren't usable in isolation — "logs everywhere, visibility nowhere" |
| Log Source Types | Host-centric (Windows, Linux, web server logs) and network-centric (routers, network devices, internet-facing traffic) |
| Core SIEM Features | Centralized log collection, log normalization, log correlation, real-time alerting, dashboards & reporting |
| Alert Workflow | Detection rule triggers → use case matched → analyst investigates → determine true/false positive |
| Lab Objective | Investigate a suspicious process execution alert and determine analyst response |

## Hands-On Activities

**1. Introduction & Learning Objectives**
Reviewed the room's goals: understanding different log source types, recognizing the limitations of working with isolated/unconnected logs, and understanding why SIEM tools are essential for meaningful investigation.

**2. The Problem — Logs Everywhere, Visibility Nowhere**
Covered how a typical network generates massive volumes of logs across many devices — hosts, servers, routers — that communicate with each other and the internet, but without a SIEM, these logs sit isolated with no way to correlate related events across sources.

**3. Log Source Categories**
Broke down log sources into two categories:
- **Host-centric log sources** — Windows machines, Linux machines, individual server logs
- **Network-centric log sources** — routers, network devices, traffic passing through internet-facing infrastructure

**4. What is a SIEM?**
Defined SIEM (Security Information and Event Management) and its role in aggregating and making sense of log data from across the environment.

**5. Core SIEM Features**
Reviewed the primary capabilities a SIEM provides:
- **Centralized log collection** — pulling logs from all sources into one platform
- **Normalization** — standardizing log formats from different sources into a consistent structure
- **Correlation** — linking related events across different logs to reveal patterns
- **Real-time alerting** — triggering alerts as matching conditions occur
- **Dashboards & reporting** — visualizing data for faster analysis and stakeholder reporting

**6. Log Sources Station**
Reviewed practical examples of log sources feeding into a SIEM — Windows machine logs, Linux machine logs, and web server logs — and how each contributes different visibility into system/network activity.

**7. Alerting Process & Analysis**
Covered how detection rules generate alerts, using example use cases to understand the logic behind why a specific alert fires and what conditions had to be met.

**8. Lab — Alert Investigation**
Investigated a triggered alert involving a suspicious process:
- Identified the **suspicious process execution** flagged by the SIEM
- Traced the **user responsible** for triggering the process
- Identified the **affected hostname**
- Examined how/why the process was flagged as suspicious
- Determined whether the alert was a **true positive** — confirmed as true positive after analysis
- Took the appropriate follow-up action and retrieved the flag for correctly classifying and responding to the alert

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Host vs. network-centric log sources | Knowing where to look first depending on the type of alert |
| Log normalization & correlation concepts | Understanding how a SIEM turns raw noise into an actionable alert |
| Detection rule / use case logic | Understanding why an alert fired — critical for accurate triage |
| True/false positive determination | Core daily SOC skill — avoiding alert fatigue by correctly classifying findings |
| Process execution investigation | Practicing the exact workflow used in real endpoint/process-based alerts |

## Key Takeaways

- A SIEM's real value isn't just collecting logs — it's normalization and correlation that turn scattered, isolated data into something an analyst can actually act on.
- Understanding host-centric vs. network-centric log sources helps prioritize where to pivot first during an investigation.
- Correctly distinguishing true positives from false positives is one of the most important day-to-day SOC skills — misclassifying either wastes time or misses real threats.
- Tracing an alert back to the responsible user, host, and process is the exact workflow used in real-world endpoint detection investigations.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
