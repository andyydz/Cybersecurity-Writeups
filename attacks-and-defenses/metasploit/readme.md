# Exploitation Basics

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Category](https://img.shields.io/badge/Category-Exploitation%20Basics-blue)

> **Key finding:** exploitation doesn't always mean writing exploit code from scratch — sometimes it's a single malicious link (Moniker Link) triggering a known CVE, and sometimes it's just knowing the difference between a bind shell, a reverse shell, and a web shell well enough to catch one on the wire.

---

## Overview

This folder covers the foundational offensive concepts behind gaining and using access on a target — starting with a real-world CVE and then stepping back to the core shell types that underpin almost every post-exploitation scenario.

---

## Writeups in This Folder

| File | Topic |
|---|---|
| `moniker-link (CVE-2024-21413).md` | Outlook Moniker Link vulnerability (CVE-2024-21413) — how a crafted hyperlink bypasses Protected View and leads to NTLM credential leakage/RCE |
| `shells-overview.md` | Overview of shell types — reverse shells, bind shells, web shells — and how each is established and used |

---

## What I Actually Found

| Concept | Key Insight |
|---|---|
| CVE-2024-21413 (Moniker Link) | A specially crafted Outlook hyperlink can bypass Protected View, forcing the app to auto-open the linked file and leak NTLM hashes or trigger code execution |
| Reverse shell | Target initiates the connection back to the attacker — useful for bypassing inbound firewall restrictions |
| Bind shell | Target opens a listening port and waits for the attacker to connect — simpler, but often blocked by firewalls |
| Web shell | A malicious script dropped on a compromised web server, giving persistent command execution through HTTP requests |

---

## SOC Analyst Relevance

- Moniker Link–style vulnerabilities are a reminder that email remains a primary initial access vector — SOC monitoring should flag unusual outbound SMB/NTLM authentication attempts triggered by a user simply opening an email.
- Recognizing the traffic signature of a reverse shell (unexpected outbound connection from an internal host to an external IP on an odd port) is one of the most common indicators analyzed during triage.
- Web shells are frequently missed by traditional AV since they can be small, obfuscated scripts — file integrity monitoring on web server directories is a key detection control.

---

## Key Takeaways

- Not every exploitation technique requires custom exploit development — some of the most damaging vulnerabilities (like Moniker Link) rely on abusing legitimate application behavior.
- Understanding the mechanics of reverse, bind, and web shells makes it much easier to recognize their traffic patterns during log and network analysis.
- Patching and Protected View settings matter — CVE-2024-21413 is a strong example of why keeping mail clients updated is a real, not theoretical, security control.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
