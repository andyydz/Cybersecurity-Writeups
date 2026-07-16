# Blue Team Fundamentals — TryHackMe Writeup

**Rooms covered in this writeup:**
1. Junior Security Analyst Intro
2. Meet the Blue Team
3. Human as Attack Vector
4. System as Attack Vector

**Path:** Introduction to Cyber Security / Blue Team
**Category:** SOC Fundamentals
**Author:** Andrew Vinston D Souza (andyydz57)

---

## 1. Junior Security Analyst Intro

### The Security Analyst Journey
An overview of how a security analyst grows from an entry-level (L1) role into more senior positions, building technical depth and situational judgment over time.

### Daily Duties of a Security Analyst
Core day-to-day responsibilities: monitoring alerts, triaging events, escalating confirmed threats, and documenting findings for the wider team.

### The SOC Team
A SOC is not a single role — it's a layered team:
- **Senior Analyst (L2/L3)** — handles escalated, more complex investigations
- **SOC Engineer** — builds and tunes the detection tooling (SIEM rules, log sources)
- **SOC Manager** — oversees team performance, process, and reporting
- **Incident Responder** — leads containment and remediation once an incident is confirmed

### A Day in the Life of a Security Analyst
Walks through a realistic shift: reviewing the queue, prioritizing by severity, investigating alerts, documenting verdicts, and handing off/escalating where needed — reinforcing that the job is equal parts technical analysis and clear communication.

**Key takeaway:** L1 is the entry point into a much larger team structure, and success depends as much on process discipline as on technical skill.

---

## 2. Meet the Blue Team

### Security Hierarchy
Typical organizational ladder in a security org:
`CEO → CISO → Associate Manager → Team Lead → Associate Analyst / Associate Engineer → GRC Specialist / Pen Tester`

### Meet the Blue Team
The SOC team is described as the organization's **first line of defense** — the group actively monitoring, detecting, and responding to threats in real time.

### CSIRT (Cyber Incident Response Team)
Referred to as the organization's "cyber firefighters" — the team mobilized specifically once an incident is confirmed, focused on containment, eradication, and recovery.

### Specialized Defense Roles
Beyond the core SOC, blue team–adjacent roles include:
- **DevSecOps** — embedding security into the software delivery pipeline
- **Penetration Tester** — proactively finds weaknesses before attackers do
- **GRC Auditor** — governance, risk, and compliance oversight
- **AppSec Engineer** — secures applications at the code/design level
- **Threat Analyst** — researches and tracks adversary TTPs
- **AI Researcher (Security)** — an emerging role applying AI/ML to detection and defense

### Advancing a SOC Career
Outlines a general SOC career path (L1 → L2 → L3 → specialization/leadership), and the choice between growing within a company's **internal SOC** versus an **MSSP (Managed Security Service Provider)**, which offers broader exposure across multiple client environments early in a career.

### Final Challenge
Room concludes with a practical flag-capture task tying together the roles and hierarchy covered.

**Key takeaway:** The "SOC" is one piece of a much wider blue team ecosystem — useful context for framing where an L1 role fits and where it can lead.

---

## 3. Human as Attack Vector

### Introduction
Humans are frequently the easiest entry point for attackers — no exploit needed if a person can simply be convinced to click, download, or hand over access.

### Attacks on Humans
- **Phishing** — deceptive emails/messages designed to steal credentials or deliver payloads
- **Malware downloads** — tricking users into installing malicious software
- **Deepfakes** — synthetic audio/video used for impersonation-based social engineering

### Defending Humans
- **Anti-phishing solutions** — email filtering and link/attachment inspection
- **Antivirus / EDR** — endpoint-level detection and response as a safety net
- **Trust but verify principle** — treating unexpected requests (even from known contacts) with healthy skepticism until confirmed
- **Security awareness training** — the primary long-term defense: teaching users to recognize and report attempts

### Practice: Risk Dashboard
Hands-on task using a dashboard to identify which employees are currently flagged as "at risk" based on behavior/training data.

### Security Policy
Reinforces that technical controls need to be backed by clear, enforced organizational policy to be effective.

**Key takeaway:** Human-layer defense is a mix of tooling (email/EDR filters) and culture (training + verification habits) — technology alone isn't enough.

---

## 4. System as Attack Vector

### Introduction
Defines a "system" broadly — any device, service, or piece of infrastructure that can be a target — and how a breach at the system level differs from a human-targeted attack.

### Attacks on Systems
- **Vulnerabilities** — unpatched flaws attackers can exploit directly
- **Supply chain vulnerabilities** — risk introduced via third-party software/vendors
- **Software vulnerabilities** — flaws in application code or dependencies
- **Responding to vulnerabilities** — the process of triage, patching, and verification once found

### Misconfigurations
- Covers common misconfiguration risks (open ports, default credentials, excessive permissions)
- **Responding to misconfigurations** — remediation workflow similar to vulnerability response, but focused on configuration hardening rather than patching

### Practice: Risk Dashboard
Hands-on task flagging systems currently at risk, based on dashboard data — mirrors the human-vector dashboard exercise but applied to infrastructure.

### Patch Management
The structured process of applying software updates in a timely, tested, and tracked way — a core control against known-vulnerability exploitation.

### Training & Protection
- IT/network protection training for staff managing infrastructure
- Antivirus protection as a baseline control on systems themselves

### Remediation Plan
Ties the room together: once systems-at-risk are identified, a clear remediation plan (patch, reconfigure, monitor, verify) closes the loop.

**Key takeaway:** System-level defense mirrors human-level defense in structure — identify risk, respond, and verify — but the controls are technical (patching, hardening) rather than behavioral.

---

## Overall Conclusion

Together, these four rooms build the foundational mental model for an SOC L1 role:
- **Who you work with** (Junior Security Analyst Intro, Meet the Blue Team) — the team structure and career path around the role
- **What you're defending** (Human as Attack Vector, System as Attack Vector) — the two broad categories of attack surface every SOC analyst monitors for

This foundation directly supports day-to-day L1 work covered in later rooms like **SOC L1 Alert Triage** and **SOC L1 Alert Reporting**, where these concepts get applied hands-on.
