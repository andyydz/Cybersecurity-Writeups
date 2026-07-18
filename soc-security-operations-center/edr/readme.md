# EDR (Endpoint Detection and Response)

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Category](https://img.shields.io/badge/Category-SOC%20%2F%20Endpoint%20Security-blue)

This folder contains my notes and write-up on **Introduction to EDR**, covering how Endpoint Detection and Response solutions work, how they differ from traditional antivirus, and how analysts use them to detect and respond to threats on endpoints.

## Overview

EDR goes beyond signature-based antivirus by continuously monitoring endpoint behavior — process execution, network connections, command-line activity, and file/registry changes — giving analysts the visibility and response tools needed to catch threats that traditional antivirus would miss.

## Writeup

📄 `introduction-to-edr.md` — Covers EDR architecture (agent and console), the telemetry it collects, detection techniques (behavioral analysis, IOC matching, MITRE ATT&CK mapping, machine learning), response capabilities (host isolation, process termination, quarantine), and a walkthrough of investigating a realistic EDR alert.

## SOC Analyst Relevance

EDR is one of the primary tools a SOC analyst works in day-to-day — understanding its telemetry and alert structure is directly applicable to triaging endpoint-based alerts in a real SOC environment.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
