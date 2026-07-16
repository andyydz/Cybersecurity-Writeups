# SOC L1 Alert Reporting — TryHackMe Writeup

**Path:** SOC Level 1
**Room:** SOC L1 Alert Reporting
**Category:** SOC Fundamentals / Alert Handling
**Author:** Andrew Vinston D Souza (andyydz57)

---

## Learning Objectives
- Understand the need for proper alert reporting and escalation
- Learn how to write alert comments and case reports properly
- Explore escalation methods and communication best practices
- Apply this knowledge by triaging alerts in a simulated environment
- Build confidence handling alerts during live SOC operations

## The Alert Funnel
Illustrates how volume narrows as alerts move up the chain:
`Hundreds of alerts → L1 triage → ~10 True Positives → L2 → 1 confirmed incident → DFIR`

The ultimate goal at every stage is the same: protect corporate data. This room focuses on the three pieces that keep that funnel working — **alert reporting**, **alert escalation**, and **communication**.

## Alert Reporting Guide

### Purpose of an Alert Report
A short, structured L1 report is more than paperwork — it's a force multiplier for the whole SOC:
- **Provides context for escalation** — saves L2 time by giving a clear snapshot of what happened
- **Preserves findings** — raw SIEM logs can expire, but a well-documented alert record lives on as evidence
- **Improves investigation skill** — writing a clear report forces the analyst to organize their own reasoning

### Report Format — The 5 W's
A good alert report answers:
- **Who** — the user/account involved
- **What** — the activity that triggered the alert
- **When** — timing of the event
- **Where** — source/destination (host, IP, domain)
- **Why** — reasoning behind the verdict

### Practice: Sensitive Document Case
Hands-on task investigating a case involving leaked sensitive information — determining whether the sender is suspicious and whether the activity is likely a phishing attempt, then documenting the findings using the 5 W's format.

## Escalation Guide

### Escalation Steps
When an alert is confirmed as a real threat requiring further action, it needs to be escalated to an L2 analyst with a properly documented handoff, rather than just being flagged and left.

### Requesting L2 Support
Covers how to properly request L2 involvement — clear subject/summary, current status, and what specifically is needed from L2.

## Communication Case Studies
The room works through realistic communication scenarios an L1 analyst may face:
- An alert is urgent/critical, but **L2 is unavailable** and doesn't respond within 30 minutes — how to escalate further or find backup coverage
- A **Slack/Teams account compromise** alert requires reaching out to validate a login directly with the affected user
- An **overwhelming volume of alerts** arrives in a short window; days later it's discovered that an alert was mishandled and a real attack was likely missed — how to communicate and document this transparently
- An investigation **can't be completed** because SIEM logs weren't parsed correctly and aren't searchable — how to communicate this blocker up the chain (e.g., to L2 or the SOC engineer) rather than letting the alert stall silently

## Conclusion
This room extends the triage workflow from **SOC L1 Alert Triage** into what happens next: turning a raw verdict into a clear, well-documented report, escalating it correctly when needed, and communicating honestly — including when something goes wrong (missed alerts, broken tooling, unresponsive L2). Together, these two rooms cover the complete L1 alert lifecycle from detection to resolution or handoff.
