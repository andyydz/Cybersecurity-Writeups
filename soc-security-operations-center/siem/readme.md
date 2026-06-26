#  SIEM - Introduction to SIEM

This folder contains my writeup and screenshots from the **Introduction to SIEM** room on TryHackMe — part of my SOC Level 1 learning path.

---

##  Folder Structure

```
siem/
├── screenshots/
│   ├── 01-siem-dashboard-overview.png
│   ├── 02-alert-investigation.png
│   └── 03-suspicious-activity-analysis.png
└── intro-to-siem.md
```

---

##  What This Room Covers

- What SIEM is and why it exists
- Host-centric vs network-centric log sources
- Challenges of working with isolated logs
- SIEM core features — centralisation, normalisation, correlation, alerting
- How detection rules are created and triggered
- Hands-on alert investigation inside a SIEM dashboard

---

##  Tools Used

- Splunk (SIEM dashboard)
- TryHackMe AttackBox
- Windows Event Viewer (log source context)

---

##  Key Takeaways

- SIEM is the central nervous system of a SOC
- Logs in isolation provide limited value — correlation is everything
- Detection rules define when alerts fire — understanding them is core to SOC L1
- True positive vs false positive triage is the primary SOC analyst responsibility
- A compromised device must be isolated quickly to prevent lateral movement

---

##  Back to SOC Folder

[SOC - Security Operations Center](../readme.md)
