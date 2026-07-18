# IDS (Intrusion Detection Systems)

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Category](https://img.shields.io/badge/Category-SOC%20%2F%20Network%20Detection-blue)

This folder contains my notes and write-up on **IDS Fundamentals**, covering how Intrusion Detection Systems monitor network traffic for malicious activity, using Snort as the primary example tool.

## Overview

An IDS passively monitors network traffic against a set of rules or signatures, generating alerts when suspicious patterns are detected — a core layer of defense that feeds directly into SOC alert triage and investigation workflows.

## Writeup

📄 `ids-fundamentals.md` — Covers IDS fundamentals including how detection rules work, the difference between IDS and IPS, and hands-on examples of writing and testing rules using Snort.

## SOC Analyst Relevance

IDS alerts are one of the most common alert sources a SOC analyst triages — understanding how Snort rules are built and what triggers them makes it far easier to interpret alert context and determine true positive vs. false positive.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
