# SOC Workbook and Lookup — TryHackMe Writeup

**Path:** SOC Level 1
**Room:** SOC Workbook and Lookup
**Category:** SOC Fundamentals / Alert Handling
**Author:** Andrew Vinston D Souza (andyydz57)

---

## Introduction
Covers the reference resources an L1 analyst leans on during investigation — asset/identity inventories, the corporate network diagram, and the SOC workbook — and how they speed up and standardize triage.

## Learning Objectives
- Familiarize yourself with the SOC investigation workbook
- Learn where to find and how to use the asset inventory in a SOC
- Understand the importance of the corporate network diagram
- Practice the workflow hands-on inside an interactive interface

## Assets and Identities

### Identity Inventory
Systems used to look up "who" during an investigation — resolving a username or account to a real person and their role:
- **Active Directory** — central identity store for on-prem accounts
- **SSO Provider** — single sign-on platform tying identities across apps
- **HR System** — confirms employment status, role, and department
- **Custom solutions** — org-specific identity tooling

### Asset Inventory
Systems used to look up "what" during an investigation — resolving a hostname or IP to a specific device, its owner, and its purpose:
- **Active Directory** — device objects and domain membership
- **SIEM/EDR** — endpoint telemetry and current status
- **MDM solution** — mobile/device management records (ownership, patch state, compliance)
- **Custom solutions** — org-specific asset tracking tools

## Network Diagram
Covers reading a corporate network diagram — how traffic flows between zones such as the process network, database subnet, and other segments — so an analyst can quickly judge whether an alert's source/destination path makes sense or is suspicious.

## Workbook Theory
Explains what a **SOC workbook** is: a predefined, step-by-step guide for handling a specific alert type, so investigation is consistent across analysts rather than improvised each time. A workbook typically guides an analyst through three stages:
- **Enrichment stage** — pulling in supporting context (asset owner, identity, related logs)
- **Investigation stage** — following defined steps to assess whether the activity is malicious
- **Escalation stage** — clear criteria for when and how to hand off to L2

A worked example walks through applying a workbook end-to-end against a sample alert.

## Workbook Practice
Hands-on exercise applying the workbook process to real alerts inside the SOC dashboard, capturing flags at each stage (enrichment, investigation, escalation) to confirm correct workbook usage.

## Conclusion
This room fills in the "how do I actually investigate efficiently" gap left by **SOC L1 Alert Triage** — asset/identity inventories and network diagrams give an analyst the context to interpret an alert correctly, while the workbook turns that context into a repeatable, auditable process. Together with Alert Triage and Alert Reporting, this completes the practical toolkit for handling an alert from first look to final verdict.
