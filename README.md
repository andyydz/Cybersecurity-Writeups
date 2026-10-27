# Cybersecurity Write-ups

**Aspiring SOC Analyst | Blue Team | Threat Detection & Incident Response**

<p align="center">
  <img src="asset/andyy-banner.jpg"
       alt="ANDYYDZ57 — Cybersecurity Write-Ups"
       width="100%">
</p>

<p align="center">
  <a href="https://tryhackme.com/p/andyydz57">
    <img src="https://tryhackme-badges.s3.amazonaws.com/andyydz57.png"
         alt="TryHackMe profile badge">
  </a>
  <br>
  <a href="https://tryhackme.com/p/andyydz57">View my TryHackMe profile</a>
</p>

---
I am a final-year BCA student building practical defensive-security skills through lab write-ups and projects. This repository is my technical documentation record, written with attention to how each topic applies in a Security Operations Center.

[GitHub](https://github.com/andyydz) · [TryHackMe profile](https://tryhackme.com/p/andyydz57) · [LinkedIn](https://www.linkedin.com/in/andrew-vinston-d-souza-41699330a/)

TryHackMe longest streak: 78 days (historical personal best, not my current streak).

## Current Focus

- TryHackMe SOC Level 1 learning (in progress)
- SIEM and log analysis
- Alert triage and reporting
- Hands-on detection work in my [Sentinel SOC Lab](#projects)

## Selected Technical Write-ups

| Topic | Write-up |
|-------|----------|
| SOC fundamentals | [SOC Fundamentals](soc-security-operations-center/soc-fundamentals.md) |
| SIEM | [Introduction to SIEM](soc-security-operations-center/siem/introduction-to-siem.md) |
| Log search with Splunk | [Splunk basics](soc-security-operations-center/splunk/splunk-the-basic.md) |
| Alert triage | [SOC Level 1: alert triage](soc-security-operations-center/soc-level-1/soc-l1-alert-triage.md) |
| Alert reporting | [SOC Level 1: alert reporting](soc-security-operations-center/soc-level-1/soc-l1-alert-reporting.md) |
| Phishing analysis | [Phishing analysis fundamentals](soc-security-operations-center/phishing-analysis/phishing-analysis-fundamentals.md) |
| Digital forensics | [Digital forensics fundamentals](soc-security-operations-center/digital-forensics/digital-forensics-fundamentals.md) |
| Threat intelligence | [Pyramid of Pain](soc-security-operations-center/threat-intelligence/pyramid-of-pain.md) |
| Network traffic analysis | [Wireshark](soc-security-operations-center/wireshark/readme.md) |
| Malware analysis | [CAPA: the basics](malware-analysis/capa-the-basics.md) |

## Repository Navigation

| Directory | Contents |
|-----------|----------|
| [soc-security-operations-center/](soc-security-operations-center/) | SOC fundamentals, SIEM, Splunk, EDR, IDS, SOC Level 1 alert triage and reporting, digital forensics, threat intelligence, phishing analysis, Nmap, Wireshark |
| [network-concepts/](network-concepts/) | Networking concepts, including the OSI model and DNS |
| [windows/](windows/) | Windows basics and Active Directory |
| [linux/](linux/) | Linux fundamentals and command line basics |
| [malware-analysis/](malware-analysis/) | Malware analysis tooling, including CAPA |
| [web-security/](web-security/) | Web security, including Burp Suite |
| [attacks-and-defenses/](attacks-and-defenses/) | Attack and defense topics, including cryptography and hashing |
| [cybersecurity/](cybersecurity/) | Security fundamentals |
| [google-cybersecurity-professional-cert/](google-cybersecurity-professional-cert/) | Coursework notes for the Google Cybersecurity Professional Certificate, such as Foundations of Cybersecurity |
| [os-basics/](os-basics/) | Operating system fundamentals |
| [computer-fundamentals/](computer-fundamentals/) | Computer fundamentals |
| [software-basics/](software-basics/) | Programming fundamentals |

## Projects

### Sentinel SOC Lab

[Sentinel SOC Lab](https://github.com/andyydz/sentinel-soc-lab) is a personal learning lab built in VirtualBox with Wazuh, Kali Linux, and an Ubuntu endpoint. It follows this lifecycle:

`SIMULATE → DETECT → INVESTIGATE → RESPOND → MEASURE → IMPROVE → RETEST`

Status: v0.2 detection engineering and v0.3 investigation are in progress. Controlled modification tests have triggered my custom Wazuh rule 100002; creation and deletion have not yet been validated for that rule. It is not a finished SOC platform, and I have not measured detection rates. Sentinel is my own project and is unrelated to Microsoft Sentinel.

### Bank Secure Network

[Bank Secure Network](https://github.com/andyydz/bank-secure-network) is a simulated networking project built in Cisco Packet Tracer. It covers VLAN segmentation, router-on-a-stick, DHCP, DNS, internal web services, and ACL-based security. It is a lab simulation, not a real banking deployment.

## Tools and Learning Areas

| Area | Guided labs (TryHackMe) | My own projects |
|------|-------------------------|-----------------|
| SIEM and log analysis | Splunk | Wazuh (Sentinel SOC Lab) |
| Network analysis | Wireshark, Nmap | Cisco Packet Tracer (Bank Secure Network) |
| Malware analysis | CAPA | None yet |
| Web security | Burp Suite | None yet |
| Lab environment | TryHackMe virtual machines | VirtualBox, Kali Linux, Ubuntu (Sentinel SOC Lab) |

Concepts studied: SOC operations, SIEM, EDR, IDS, alert triage and reporting, phishing analysis, digital forensics, and threat intelligence.

## Disclaimer

These write-ups are for educational use. All activities were performed in legal, controlled lab environments, and no real systems were targeted.
