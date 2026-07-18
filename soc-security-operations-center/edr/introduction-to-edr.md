# Introduction to EDR

**Room:** Introduction to EDR
**Category:** SOC / Security Operations Center
**Platform:** TryHackMe

---

## Learning Objectives

- Understand the basics of EDR and how it works
- Differentiate EDR from traditional antivirus software
- Examine the architecture of an EDR solution
- Analyze the types of telemetry it collects from endpoints
- Understand the detection and response capabilities of EDR
- Investigate a realistic alert in EDR

---

## What is EDR?

EDR (Endpoint Detection and Response) is a security solution that continuously monitors endpoints — laptops, servers, workstations — to detect, investigate, and respond to threats. Unlike traditional antivirus, EDR doesn't just look for known malware signatures; it watches endpoint behavior in real time, records it, and gives analysts the tools to investigate and respond to suspicious activity.

### Popular EDR Solutions

| EDR Solution | Vendor |
|---|---|
| CrowdStrike Falcon | CrowdStrike |
| SentinelOne Singularity (Active EDR) | SentinelOne |
| Microsoft Defender for Endpoint | Microsoft |
| OpenEDR | Comodo/Xcitium |
| Cynet EDR | Cynet |

### Core Features of EDR

- **Visibility** — continuous, real-time insight into everything happening on an endpoint
- **Detection** — identifying malicious or suspicious behavior as it happens
- **Response** — the ability to act on a threat directly from the console (isolate, kill, quarantine)

---

## Beyond Antivirus: Why Do We Need EDR?

Traditional antivirus works mostly on **signature-based detection** — it checks files against a database of known, preloaded virus signatures. If a threat isn't in that database (a new variant, a fileless attack, a living-off-the-land technique), antivirus simply won't catch it.

EDR goes further. It doesn't just check files against a list — it continuously scans and monitors *behavior* across the endpoint: process activity, network connections, registry changes, and more. This lets it catch threats antivirus was never designed to see, including attacks that use legitimate system tools maliciously.

### Antivirus vs. EDR Response — Key Differences

| Step | Antivirus | EDR |
|---|---|---|
| 1. Detection basis | Known malware signatures | Behavioral analysis + signatures + IOCs |
| 2. Scope of visibility | File-level scans | Full endpoint activity (process, network, registry, files) |
| 3. Response action | Delete/quarantine the file | Isolate host, kill process, quarantine, remote triage |
| 4. Investigation | None — no context provided | Full timeline/context for analyst investigation |
| 5. Threat coverage | Known threats only | Known + unknown + fileless + living-off-the-land |
| 6. Integration | Standalone | Integrates with SIEM, SOAR, threat intel platforms |

---

## How Does EDR Work?

EDR operates on a simple agent–console model:

1. **Agent** — a lightweight piece of software installed on the endpoint. It continuously monitors and records activity (processes, files, network, registry) and forwards this data to a central console.
2. **EDR Console** — the centralized management platform where all agent data is aggregated. Analysts view alerts, investigate telemetry, and issue response actions from here.

### What Happens After Detection?

Once the agent detects suspicious behavior, it generates an alert and sends it to the console. From there:

- The alert is correlated against known IOCs, behavioral rules, and threat intelligence
- Analysts investigate the alert using the collected telemetry (timeline of events, parent-child process trees, network connections)
- A response action can be triggered — either automatically (per policy) or manually by an analyst

### EDR with Other Tools

EDR rarely works alone. It's commonly integrated with:

- **SIEM** — for centralized log correlation across the environment
- **SOAR** — for automated playbook-driven response
- **Threat Intelligence platforms** — to enrich alerts with IOC context

---

## EDR Telemetry

Telemetry is the raw activity data the EDR agent collects from the endpoint. This is what gives EDR its visibility advantage over antivirus.

### Types of Telemetry Collected

- **Process execution and termination** — every process that starts or stops, along with parent-child relationships
- **Network connections** — outbound/inbound connections, destination IPs, ports, protocols
- **Command-line activity** — the exact command-line arguments used to launch a process (critical for spotting living-off-the-land binaries)
- **File and folder modification** — creation, deletion, or modification of files on disk
- **Registry modification** — changes to Windows registry keys, often used for persistence

---

## Detection and Response Capabilities

### Detection

- **Behavioral detection** — flags abnormal or suspicious sequences of activity rather than relying on a static signature
- **Abnormal/anomaly detection** — baselines normal endpoint behavior and flags deviations
- **IOC matching** — compares observed artifacts (hashes, IPs, domains) against known indicators of compromise
- **MITRE ATT&CK mapping** — maps detected behavior to known adversary tactics and techniques for context
- **Machine learning algorithms** — used to classify and score activity that doesn't match a known rule

### Response

- **Isolate host** — cuts the endpoint off from the network to contain the threat
- **Terminate process** — kills the malicious process directly from the console
- **Quarantine** — isolates the malicious file so it can't execute
- **Remote access** — allows an analyst to remotely access the endpoint for live investigation
- **Artifact collection** — pulls forensic artifacts (files, memory, logs) from the endpoint for deeper analysis

---

## Investigating an Alert in EDR

When an alert fires, the general investigation workflow is:

1. Review the alert summary and severity
2. Trace the process tree — what spawned what, and in what order
3. Check the command-line arguments for suspicious flags or obfuscation
4. Correlate with network telemetry — did the process reach out anywhere unusual?
5. Check file/registry telemetry for persistence mechanisms
6. Map the behavior to MITRE ATT&CK for context
7. Decide on a response action based on findings — isolate, kill, quarantine, or escalate

---

## Conclusion

EDR fills the gap that traditional antivirus leaves open. Where antivirus only checks files against a known-bad list, EDR watches the full behavioral picture of an endpoint — processes, network activity, files, and registry — and gives analysts the visibility and response tools to catch, investigate, and contain threats that would otherwise go unnoticed. Understanding EDR architecture, telemetry, and detection/response workflows is a foundational skill for any SOC analyst role.
