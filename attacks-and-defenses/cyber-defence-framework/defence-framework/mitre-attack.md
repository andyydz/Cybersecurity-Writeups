# TryHackMe — MITRE

## Introduction

**MITRE ATT&CK** (Adversarial Tactics, Techniques, and Common Knowledge) is a globally accessible knowledge base of adversary tactics and techniques based on real-world observations. Everything an attacker might do — from initial reconnaissance to final impact — is catalogued and documented in this framework, making it one of the most widely adopted references in the cybersecurity industry.

### Learning Objectives

- Understand the **purpose and structure** of the MITRE ATT&CK framework.
- Explore how security professionals apply ATT&CK to their work.
- Understand the uses of ATT&CK for **Cyber Threat Intelligence (CTI)**.
- Use the ATT&CK Matrix to profile threats.
- Discover other MITRE frameworks, including **CAR** and **D3FEND**.

---

## The ATT&CK Framework

ATT&CK documents adversary behavior across several structured layers:

- **Tactics** — the *why* of an attack technique; the attacker's tactical goal or objective (e.g., gaining Initial Access, achieving Persistence).
- **Techniques** — the *how*; the specific method used to achieve a tactic's goal.
- **Sub-techniques** — a more granular breakdown of a technique.
- **Procedures** — the specific real-world implementation an adversary (or malware/tool) uses to carry out a technique — documented from actual observed incidents.

### ATT&CK Evolution & the Matrix

The ATT&CK Matrix organizes tactics and techniques into columns and rows, letting analysts trace an attack path from left to right (e.g., Reconnaissance → Active Scanning → Initial Access → …).

---

## Why ATT&CK Matters

ATT&CK matters because it gives security professionals and organizations a **standard, consistent language** for describing adversary behavior. In the cybersecurity field, the same action or technique is often referred to by several different names across vendors and teams. By providing standardized terminology and a unique ID for each tactic/technique, ATT&CK makes it far easier to compare data, correlate incidents, and communicate effectively across the security community.

---

## Who Uses ATT&CK

| Role | Goal | How They Use ATT&CK |
|------|------|----------------------|
| **Cyber Threat Intelligence (CTI)** | Collect and analyze threat information to improve an organization's security posture | Map observed attacker behavior to ATT&CK to build actionable threat profiles shared across the industry |
| **SOC Analysts** | Investigate and triage security alerts | Link alert activity to specific tactics/techniques, adding context for prioritization |
| **Detection Engineers** | Design and improve detection and response systems | Build detections mapped directly to ATT&CK techniques |
| **Incident Responders** | Respond to and investigate security incidents | Use ATT&CK to identify what stage an incident is at and what to expect next |
| **Red & Purple Teams** | Emulate adversary behavior to test defenses | Map planned actions to ATT&CK techniques for realistic, threat-informed engagements |

---

## Mapping to ATT&CK — CTI Scenario

Worked through mapping a threat intelligence scenario's observed attacker actions to their corresponding ATT&CK tactics and techniques, building a technique-level profile of the activity.

---

## Other MITRE Projects

- **CAR (Cyber Analytics Repository)** — a repository of analytics built on the ATT&CK framework, used to implement and test detections for specific adversary techniques.
- **D3FEND** — Detection, Denial, and Disruption framework empowering network defenders; a structured framework that maps defensive techniques and establishes a common language for describing how security controls work (the defensive counterpart to ATT&CK's offensive focus).
- **Emerging/adjacent MITRE frameworks** — including **MITRE Engage** (adversary engagement/deception planning) and **MITRE ATLAS** (adversarial threats to AI/ML systems).

---

## Conclusion

MITRE ATT&CK provides a shared, standardized language for describing adversary tactics, techniques, and procedures — bridging the gap between offense and defense. Whether used by CTI analysts building threat profiles, SOC analysts triaging alerts, detection engineers building rules, or red teams emulating adversaries, ATT&CK gives every role in the security community a common reference point. Paired with complementary frameworks like CAR and D3FEND, it forms a foundational part of a mature cybersecurity posture.
