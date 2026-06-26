![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Security%20Fundamentals-blue?style=for-the-badge)



> **Key Finding:** Security is not one-size-fits-all — the right protection mechanism depends entirely on what you are protecting, who you are protecting it from, and what level of risk is acceptable.

## Overview
This room covers the foundational principles of security — from the CIA triad and extended security models to defence in depth, ISO/IEC architectural principles, and the distinction between vulnerability, threat, and risk. Includes hands-on questions and flag capture based on applying these concepts.



---

## What I Actually Found

| Topic | Finding |
|---|---|
| CIA Triad | Confidentiality, Integrity, Availability — the three core pillars of security |
| Beyond CIA | Authenticity and Non-Repudiation extend the triad for stronger assurance |
| Parkerian Hexad | Six elements: Availability, Utility, Integrity, Authenticity, Confidentiality, Possession |
| DAD Triad | Disclosure, Alteration, Destruction/Denial — the attacker's mirror of CIA |
| Zero Trust | Never trust, always verify — no implicit trust based on network location |
| Trust but Verify | Traditional model — some implicit trust with periodic verification |
| Key terms | Vulnerability (weakness), Threat (potential harm), Risk (likelihood × impact) |

---

## Hands-On Activities

### CIA Triad
The three core pillars every security decision is built on:
- **Confidentiality** — ensuring data is accessible only to authorised parties
- **Integrity** — ensuring data is accurate and has not been tampered with
- **Availability** — ensuring systems and data are accessible when needed

### Beyond CIA — Authenticity and Non-Repudiation
- **Authenticity** — verifying that data or identity is genuine
- **Non-Repudiation** — ensuring an action cannot be denied after the fact (e.g. digital signatures)

### Parkerian Hexad
Extends CIA with three additional elements:

| Element | Description |
|---|---|
| Availability | System is accessible when needed |
| Utility | Data is in a usable format |
| Integrity | Data has not been altered |
| Authenticity | Data or identity is genuine |
| Confidentiality | Data is accessible only to authorised parties |
| Possession | Control of data is maintained |

### DAD Triad
The attacker's perspective — mirror of CIA:
- **Disclosure** — confidentiality breach
- **Alteration** — integrity breach
- **Destruction / Denial** — availability breach

### Security Models

#### Bell-LaPadula Model (Confidentiality focused)
- **Simple Security Property** — no read up (cannot read data at a higher classification)
- **Star Security Property** — no write down (cannot write data to a lower classification)
- **Discretionary Security Property** — access controlled via access matrix

#### Biba Model (Integrity focused)
- Opposite of Bell-LaPadula — focuses on preventing unauthorised data modification

#### Clark-Wilson Model (Integrity focused)
| Component | Description |
|---|---|
| Constrained Data Items (CDI) | Data that must be protected |
| Unconstrained Data Items (UDI) | Input data not yet validated |
| Transformation Procedures (TP) | Authorised operations on CDIs |
| Integrity Verification Procedures (IVP) | Checks that CDIs are in a valid state |

### Defence in Depth
Layered security approach — multiple controls across different levels so that if one fails, others remain. No single point of failure.

### ISO/IEC 19249 — Five Architectural Principles

| Principle | Description |
|---|---|
| Domain Separation | Different components operate in separate domains |
| Layering | Security applied at multiple layers |
| Encapsulation | Internal details hidden from external access |
| Redundancy | Duplicate systems to prevent single points of failure |
| Virtualisation | Isolated environments to contain threats |

### ISO/IEC 19249 — Five Design Principles

| Principle | Description |
|---|---|
| Least Privilege | Grant only the minimum access needed |
| Attack Surface Minimisation | Reduce the number of exploitable entry points |
| Centralised Parameter Validation | Validate all input through one trusted mechanism |
| Centralised General Security Services | Centralise authentication and security functions |
| Preparation for Error and Exception Handling | Systems should fail safely without leaking information |

### Vulnerability vs Threat vs Risk

| Term | Definition |
|---|---|
| Vulnerability | A weakness in a system that can be exploited |
| Threat | A potential event or actor that could exploit a vulnerability |
| Risk | The likelihood and impact of a threat exploiting a vulnerability |

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| CIA Triad application | Classifying incidents by which pillar was violated |
| DAD Triad awareness | Understanding attacker objectives during threat analysis |
| Security model knowledge | Recognising which controls apply to confidentiality vs integrity incidents |
| Defence in depth | Understanding layered security architecture in enterprise environments |
| Least privilege principle | Identifying over-privileged accounts during investigations |
| Vulnerability vs risk distinction | Accurate risk communication during incident reporting |

---

## Key Takeaways

- Security is context-dependent — the right protection depends on what you are defending and from whom
- CIA Triad is the foundation — Confidentiality, Integrity, and Availability underpin every security decision
- DAD is the attacker's mirror — every attack targets Disclosure, Alteration, or Destruction
- Non-Repudiation and Authenticity extend CIA for stronger assurance in critical systems
- Bell-LaPadula protects confidentiality; Biba and Clark-Wilson protect integrity
- Defence in depth ensures no single failure compromises the entire system
- Least privilege and attack surface minimisation are the two most practically impactful design principles
- Vulnerability is a weakness, threat is a potential actor or event, risk is the combination of both

---

*Part of my [TryHackMe Writeups](https://github.com/andyydz/TryHackMe-Writeups) portfolio — documenting my SOC analyst journey.*
