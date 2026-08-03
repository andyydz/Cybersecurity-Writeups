# TryHackMe — Unified Kill Chain

## Introduction

The **Unified Kill Chain (UKC)** is a framework developed by Paul Pols that expands on Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK. Where the original Cyber Kill Chain models an attack as a single linear sequence, the UKC recognizes that real intrusions are rarely linear — attackers loop back through phases, pivot across systems, and repeat stages multiple times before achieving their objective. The UKC was built to address the gaps of a purely linear model and to complement other frameworks such as MITRE ATT&CK, providing a more complete picture of attacker behavior end-to-end.

### Learning Objectives

- Understand why frameworks like the UKC are important for establishing a strong cybersecurity posture.
- Understand an attacker's **motivation, methodology, and tactics**.
- Understand the various **phases** of the Unified Kill Chain.
- Learn how the UKC complements other frameworks such as MITRE ATT&CK.

### What is a Kill Chain?

Originating from a military targeting concept, a "kill chain" is a term used to describe the sequential stages of an attack — how each stage connects to the next in a chain. Key related concepts covered:

- **Threat Modeling** — the process of identifying, analyzing, and prioritizing potential threats to a system or organization.
- **Asset** — anything of value to an organization (data, systems, credentials, infrastructure) that could be targeted by an attacker.

---

## The Unified Kill Chain — 18 Phases

The UKC consists of **18 phases**, organized into three overarching stages that reflect the attacker's progression: **In** (gaining a foothold), **Through** (expanding access across the network), and **Out** (achieving the objective).

### Stage 1 — In (Initial Foothold)

| # | Phase | Related MITRE ATT&CK Tactic |
|---|-------|------------------------------|
| 1 | Reconnaissance | TA0043 – Reconnaissance |
| 2 | Weaponization | TA0042 – Resource Development |
| 3 | Delivery | TA0001 – Initial Access |
| 4 | Social Engineering | TA0001 – Initial Access |
| 5 | Exploitation | TA0002 – Execution |
| 6 | Persistence | TA0003 – Persistence |
| 7 | Defense Evasion | TA0005 – Defense Evasion |
| 8 | Command & Control | TA0011 – Command and Control |

### Stage 2 — Through (Network Propagation)

| # | Phase | Related MITRE ATT&CK Tactic |
|---|-------|------------------------------|
| 9 | Pivoting | TA0008 – Lateral Movement |
| 10 | Discovery | TA0007 – Discovery |
| 11 | Privilege Escalation | TA0004 – Privilege Escalation |
| 12 | Execution | TA0002 – Execution |
| 13 | Credential Access | TA0006 – Credential Access |
| 14 | Lateral Movement | TA0008 – Lateral Movement |

### Stage 3 — Out (Action on Objectives)

| # | Phase | Related MITRE ATT&CK Tactic |
|---|-------|------------------------------|
| 15 | Collection | TA0009 – Collection |
| 16 | Exfiltration | TA0010 – Exfiltration |
| 17 | Impact | TA0040 – Impact |
| 18 | Objectives | — (attacker's end goal, not a technical tactic) |

> **Note:** Unlike the linear Cyber Kill Chain, an attacker can move back and forth between "Through" phases (Pivoting, Discovery, Privilege Escalation, Execution, Credential Access, Lateral Movement) multiple times as they expand their foothold across a network, before ever reaching the "Out" stage.

---

## How the Phases Interconnect

The UKC's real strength is showing that an intrusion isn't a straight line — an attacker may gain initial access (**In**), then loop through discovery → privilege escalation → credential access → lateral movement (**Through**) repeatedly across multiple hosts, before finally collecting and exfiltrating data or causing impact (**Out**). Mapping each phase to its corresponding MITRE ATT&CK tactic ID allows defenders to cross-reference specific techniques and sub-techniques for detection and mitigation at every stage.

---

## Practical Analysis

Completed the hands-on scenarios in the room by identifying which UKC phase(s) a given set of attacker actions belonged to, and mapping the overall attack path across the **In → Through → Out** stages for each scenario provided.

---

## Conclusion

The Unified Kill Chain builds on the strengths of the original Cyber Kill Chain and MITRE ATT&CK while addressing their limitations — namely the assumption of a strictly linear attack path. By organizing 18 phases into In, Through, and Out stages, and mapping each to MITRE ATT&CK tactics, the UKC gives defenders a more realistic, end-to-end model of how modern intrusions actually unfold, which in turn supports better threat modeling and more targeted detection strategies across an organization's assets.
