![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Networking-blue)



>  **Key Finding:** A firewall's job comes down to one decision per packet — allow, deny, or forward — but *how* it makes that decision (stateless, stateful, proxy, or next-gen) determines how much context and protection it actually provides.

## Overview

Room: **Firewall Fundamentals**

This room covers firewall theory — types, rule components, and traffic directionality — followed by hands-on practice configuring Windows Defender Firewall and Linux firewall tools (iptables/UFW).

## What I Actually Found

| Area | Details |
|------|---------|
| Firewall Types | Stateless, Stateful, Proxy, Next-Gen Firewall (NGFW) |
| Rule Actions | Allow, Deny, Forward |
| Rule Directionality | Inbound rules, Outbound rules, Forward rules |
| Windows Tooling | Windows Defender Firewall — network profiles, custom rule creation |
| Linux Tooling | iptables, netfilter, UFW (Uncomplicated Firewall) |
| Core Concept | Distinguishing wanted vs. unwanted traffic based on defined rules |

## Hands-On Activities

**1. What is a Firewall?**
Reviewed the firewall's core function — filtering network traffic to separate **allowed traffic** from **unwanted traffic** based on a defined rule set.

**2. Types of Firewalls**
Covered the four main firewall categories:
- **Stateless** — filters packets individually with no awareness of connection state
- **Stateful** — tracks connection state, allowing return traffic for established sessions
- **Proxy** — intercepts and inspects traffic at the application layer before forwarding
- **Next-Gen Firewall (NGFW)** — combines traditional filtering with deeper inspection (application awareness, intrusion prevention, etc.)

**3. Firewall Rules & Components**
Learned the components that make up a firewall rule, including:
- **Actions** — Allow, Deny, Forward
- **Directionality** — Inbound rules (traffic coming in), Outbound rules (traffic leaving), Forward rules (traffic passing through, e.g. routed traffic)

**4. Windows Defender Firewall — Hands-On**
Worked in a Windows VM configuring **Windows Defender Firewall**:
- Reviewed **network profiles** (e.g. Domain, Private, Public) and how rules can differ per profile
- Created **custom rules** to allow/deny specific traffic based on port, program, or protocol

**5. Linux Firewall Tools — Hands-On**
Worked hands-on with Linux firewall tooling:
- **iptables** — direct rule configuration against the **netfilter** framework
- **netfilter** — the underlying kernel framework that iptables (and UFW) interacts with
- **UFW (Uncomplicated Firewall)** — simplified frontend for managing firewall rules without writing raw iptables syntax

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Stateless vs. stateful vs. NGFW concepts | Understanding what visibility/protection a given firewall log source actually provides |
| Rule actions (Allow/Deny/Forward) | Interpreting firewall logs to understand why traffic was permitted or blocked |
| Inbound/outbound/forward directionality | Correlating firewall logs with suspected lateral movement or exfiltration attempts |
| Windows Defender Firewall configuration | Recognizing legitimate vs. suspicious custom rule changes on endpoints |
| iptables/UFW on Linux | Reading and interpreting Linux firewall logs and rule sets during host investigation |

## Key Takeaways

- Knowing the difference between stateless and stateful firewalls is important for correctly interpreting what a firewall log can and can't tell you about a connection.
- Firewall rule directionality (inbound/outbound/forward) is often the first clue in spotting unusual traffic — e.g., unexpected outbound connections can indicate C2 or exfiltration.
- Hands-on practice with both Windows Defender Firewall and Linux iptables/UFW builds cross-platform comfort, since real environments almost always mix both OS types.
- Unauthorized changes to firewall rules (new allow rules, disabled profiles) are a meaningful indicator worth flagging during endpoint investigations.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
