# SOC L1 Alert Triage — TryHackMe Writeup

**Path:** SOC Level 1
**Room:** SOC L1 Alert Triage
**Category:** SOC Fundamentals / Alert Handling
**Author:** Andrew Vinston D Souza (andyydz57)

---

## Introduction
An entry-level but essential room for SOC L1 analysts covering the full lifecycle of a security alert — from generation to correct resolution. Alert handling is a core SOC skill: correctly triaging alerts is what determines whether a real attack is caught early or missed entirely.

## Prerequisites
Access to the TryHackMe SOC dashboard, which is used for the majority of the hands-on tasks in this room.

## SOC Dashboard
The room provides access to a simulated SOC dashboard containing a live queue of alerts, used throughout the room to practice real triage decisions.

## Events and Alerts
Covers the distinction between a raw **event** (any recorded activity) and an **alert** (an event flagged as potentially suspicious by detection rules) — with a worked example showing how an event escalates into an alert.

## Alert Triage Rules
Introduces the systematic, repeatable approach analysts follow so that alerts are handled consistently rather than ad hoc.

## Alert Properties
Every alert carries a standard set of fields used to assess it:
- **Alert Time** — when the alert was generated
- **Alert Name** — short description of the detected activity
- **Alert Severity** — Low / Medium / High / Critical
- **Alert Status** — New/Unassigned, In Progress/Pending, Closed/Resolved
- **Alert Verdict** — True Positive / False Positive
- **Alert Assignee** — analyst currently owning the alert
- **Alert Description** — detailed explanation of what triggered it and why it may be suspicious
- **Alert Fields** — technical data tied to the activity (hostnames, IPs, users, command lines)

## Alert Prioritization
When multiple alerts are queued, analysts prioritize using:
- **Filtering** — only pick alerts that are new/unassigned, to avoid duplicating another analyst's work
- **Sort by Severity** — Critical first, then High, Medium, Low
- **Sort by Time** — older alerts first, since a longer dwell time can mean more damage

## Alert Triage Workflow
The room's core hands-on process, broken into three phases:

**Initial Action**
1. Prioritize the alert queue and select the first (highest-priority) alert
2. Assign the alert to yourself
3. Move the alert status to *In Progress*

**Investigation**
4. Read the alert name and description
5. Note key alert fields (host, IP, user)
6. Check if a workbook exists for this alert type:
   - If **yes** → follow the documented workbook steps
   - If **no** → investigate the activity directly in the SIEM

**Final Action**
7. Reach a final verdict on the alert (True Positive / False Positive)
8. Decide if escalation is needed:
   - If **yes** → escalate to L2
   - If **no** → add your triage comment and move the alert to *Closed*

## SOC Dashboard Notes
Reinforces that this workflow mirrors real-world SOC tooling — the dashboard's status/verdict/assignee fields exist specifically to support this triage process at scale, across a team.

## Conclusion
This room builds the fundamental L1 triage loop — prioritize, own, investigate, decide, close or escalate — that underpins virtually every alert an L1 analyst will handle on the job. It sets up directly for the next room, **SOC L1 Alert Reporting**, which covers what happens after an alert is escalated.
