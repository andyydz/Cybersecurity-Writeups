# TryHackMe — Cyber Kill Chain

## Introduction

The **Cyber Kill Chain** is a framework developed by Lockheed Martin that breaks down the stages of a cyberattack from an adversary's perspective. It was originally adapted from a military targeting model and is used by defenders to understand, detect, and disrupt attacker behavior at each stage. The model consists of **seven objectives** that an attacker typically progresses through during an intrusion:

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command & Control (C2)
7. Actions on Objectives

Understanding each stage helps a defender map detections and controls to specific points in the attack lifecycle, rather than treating an intrusion as a single event.

---

## 1. Reconnaissance

The first stage where the attacker gathers information about the target before launching an attack.

- **Types of Reconnaissance:**
  - **Passive Recon** — gathering information without directly interacting with the target (e.g., public records, social media, WHOIS lookups).
  - **Active Recon** — directly probing the target's systems (e.g., port scanning, banner grabbing), which carries a higher risk of detection.

- **OSINT Framework** — a curated collection of free OSINT tools and resources organized by category (people search, domains, social media, etc.), used to streamline the information-gathering process.

- **Email Harvesting** — collecting employee email addresses (via search engines, LinkedIn, breach data, or tools like theHarvester) to build target lists for phishing campaigns.

---

## 2. Weaponization

The attacker couples an exploit with a deliverable payload to create a malicious deliverable (e.g., a weaponized document or executable).

- **Payloads** — the malicious code that executes the attacker's intended action once delivered.
- **Malware / Exploits** — malware is the malicious software itself; an exploit is the code that takes advantage of a specific vulnerability to deliver that malware.

---

## 3. Delivery

The stage where the weaponized payload is transmitted to the target.

- **Phishing** — sending fraudulent emails designed to trick a victim into clicking a link or opening an attachment.
- **Watering Hole Attack** — compromising a website that the target is known to frequent, so the victim is infected simply by visiting it.

---

## 4. Exploitation

The delivered payload is triggered, exploiting a vulnerability to gain code execution on the target system.

- **Zero-Day Exploits** — exploits for vulnerabilities that are unknown to the vendor and have no patch available.
- **Known CVEs** — publicly documented vulnerabilities with an assigned CVE ID that may still be exploitable if unpatched.
- **Malicious Macro Execution** — using embedded macros in documents (e.g., Word/Excel) to execute code when a victim enables content.

---

## 5. Installation

The attacker installs malware or a backdoor on the compromised system to maintain access.

- **Metasploit / Meterpreter** — a widely used exploitation framework and its post-exploitation payload, used for gaining and maintaining access to a target.
- **MITRE ATT&CK** — a knowledge base of adversary tactics and techniques used to map and classify attacker behavior at this (and every) stage.
- **Timestomping** — altering file timestamps to make malicious files blend in with legitimate system files and evade forensic detection.
- **Web Shells** — scripts placed on a compromised web server that give the attacker remote command execution via a browser or HTTP requests.

---

## 6. Command & Control (C2)

The attacker establishes a channel to remotely control the compromised system.

- **HTTP/HTTPS-based C2** — blending malicious traffic with normal web traffic to avoid detection.
- **DNS-based C2** — using DNS queries/responses as a covert channel.
- **DNS Tunneling** — encoding data within DNS queries to exfiltrate data or issue commands, often bypassing firewalls that allow DNS traffic by default.

---

## 7. Actions on Objectives

The final stage, where the attacker accomplishes their actual goal — this could be data exfiltration, data destruction, lateral movement, or establishing persistence for long-term access.

---

## Practical Analysis

Completed the hands-on section of the room by analyzing the provided scenario/artifacts and mapping the observed activity back to the corresponding Cyber Kill Chain stage. Used the concepts above to identify indicators at each phase and located the flag required to complete the room.

**Flag:** `THM{redacted}`

---

## Conclusion

The Cyber Kill Chain gives defenders a structured way to think about an intrusion as a sequence of stages rather than a single event. By mapping detections and controls to each of the seven stages — Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command & Control, and Actions on Objectives — a defender can break the chain at the earliest possible point, minimizing the impact of an attack. This room reinforced how frameworks like MITRE ATT&CK complement the kill chain by providing granular technique-level detail within each stage.
