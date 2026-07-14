![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Networking-blue)



> **Key Finding:** An IDS is only as good as its rules — Snort's rule syntax (action, protocol, source/destination IP:port, options/metadata) is the actual language that turns raw traffic into a meaningful alert.

## Overview

Room: **IDS Fundamentals**


This room covers Intrusion Detection System (IDS) theory — types, detection models, and deployment methods — followed by hands-on Snort rule writing, testing against a PCAP file, and a practical lab identifying an attacker's activity via custom rules.

## What I Actually Found

| Area | Details |
|------|---------|
| IDS Meaning | Intrusion Detection System |
| Deployment Types | NIDS (Network Intrusion Detection System), HIDS (Host Intrusion Detection System) |
| Detection Models | Signature-based, Anomaly-based, Hybrid |
| Tool Used | Snort — rule-based IDS/packet analysis engine |
| Rule Components | Action, Protocol, Source IP, Source Port, Destination IP, Destination Port, Options/Metadata |
| Practical Task | Identify attacker IP via SSH activity, write custom Snort rules, test against a PCAP |

## Hands-On Activities

**1. Introduction to IDS**
Covered what an IDS is and its role in detecting (not blocking) suspicious or malicious network activity, distinguishing it from a firewall's prevent-based approach.

**2. Types of IDS — Deployment Methods**
Learned the two primary deployment models:
- **NIDS (Network IDS)** — monitors traffic across the network, not tied to a single machine
- **HIDS (Host IDS)** — monitors activity on an individual host/endpoint

**3. Detection Models**
Reviewed the three core detection approaches:
- **Signature-based** — matches traffic against known attack patterns/signatures
- **Anomaly-based** — flags deviations from an established baseline of "normal" behavior
- **Hybrid** — combines both signature and anomaly-based detection for broader coverage

**4. Introduction to Snort**
Covered Snort's role as a widely-used, rule-driven IDS engine capable of real-time traffic analysis as well as offline analysis of captured traffic (PCAP files).

**5. Snort Rule Format**
Broke down the structure of a Snort rule:
- **Action** — what Snort does when the rule matches (e.g. alert, log, pass)
- **Protocol** — which protocol the rule applies to (TCP, UDP, ICMP, etc.)
- **Source IP / Source Port** — where the traffic originates
- **Destination IP / Destination Port** — where the traffic is headed
- **Rule options/metadata** — additional match conditions and rule identification info

**6. Custom Rule Creation & Testing**
Wrote custom Snort rules targeting specific traffic patterns, then tested them by running Snort against a provided **PCAP file** to confirm the rules triggered correctly against the recorded traffic.

**7. Practical Lab**
Applied everything hands-on:
- Analyzed traffic to identify the **attacker's IP address** based on SSH-related activity
- Reviewed and applied the custom rules created earlier
- Confirmed detection by running Snort against the lab traffic and validating the alerts generated

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| NIDS vs. HIDS deployment models | Knowing which detection layer generated a given alert, and its blind spots |
| Signature vs. anomaly vs. hybrid detection | Understanding why some attacks are missed by signature-only tools, guiding tuning decisions |
| Snort rule syntax | Reading, writing, and tuning custom detection rules — a core Tier 1/2 SOC skill |
| PCAP analysis with Snort | Validating whether a rule would have caught a given piece of traffic during retrospective investigation |
| SSH-based attacker identification | Recognizing brute-force/suspicious SSH connection patterns in logs |

## Key Takeaways

- Understanding Snort's rule syntax directly transfers to real SOC work — most commercial/open-source IDS platforms use similar action/protocol/IP/port logic.
- Signature-based detection is fast and precise but blind to novel attacks — anomaly and hybrid models fill that gap, which matters when tuning detection coverage.
- Testing custom rules against a PCAP before deploying them live is a good habit — it validates the rule actually fires before it's trusted in production.
- NIDS and HIDS give different visibility — a full detection strategy usually needs both, not one or the other.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
