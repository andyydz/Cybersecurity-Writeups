# TryHackMe — Phishing Email Analysis Tools

## Introduction

This room covers the practical tooling used to analyze a phishing email end-to-end — from identifying the key artifacts in a message, to checking reputation data, to safely detonating suspicious attachments in a sandbox.

### Learning Objectives

- Identify the key **artifacts** present in a phishing email.
- Use tools for **email header analysis**.
- Use tools for **IP and URL reputation analysis**.
- Use tools for **email body analysis**.
- Use **malware sandboxes** to safely analyze suspicious attachments.

---

## Identifying Artifacts

Key artifacts to extract from a suspicious email for analysis:

**Header artifacts:**
- Sender email address
- Sender IP address
- Email subject line
- Recipient email address
- Reply-To email address
- Date and time

**Body artifacts:**
- URLs and hyperlinks
- Attachment names
- Attachment hashes

---

## Email Header Analysis Tools

- **MXToolbox Message Header Analyzer** and similar **mail header analyzer** tools — paste in the raw email header to get a parsed, readable breakdown of the sender IP, routing hops, and authentication results (SPF/DKIM/DMARC), rather than reading the raw source manually.

---

## IP and URL Reputation Analysis

- **IPinfo** — provides geolocation and ownership details for a given IP address.
- **urlscan.io** — scans and reports on a URL's behavior, redirects, and hosted content without directly visiting it in a browser.
- **IP and Domain Reputation Center (Talos Intelligence)** — checks the reputation/trust score of an IP address or domain based on historical data.

---

## Email Body Analysis

- Manually copying suspicious links from the body works, but a dedicated **URL extraction tool** is far more efficient — it pulls every embedded URL from a raw email at once, saving significant time compared to manually inspecting the source (e.g., versus CyberChef, which works but is more general-purpose/versatile rather than purpose-built for this).
- **Attachment hashing** — generating a **SHA-256 hash** of an email attachment to check it against reputation/threat-intel databases without needing to run the file.

---

## Malware Sandboxes

Running a suspicious attachment is never safe on a personal or production machine — sandboxes provide an isolated, controlled environment to detonate and observe malware safely:

- **ANY.RUN** — an interactive sandbox; took some time to understand the interface at first, but it's a powerful tool for observing malware behavior in real time and identifying key **Indicators of Compromise (IOCs)** and configuration/registry changes, all within a controlled environment.
- **Hybrid Analysis** — a similar free malware analysis sandbox.
- **Joe Sandbox** — another automated malware analysis sandbox platform.

---

## Practical Analysis — Applying the Tools

Used the tools above to identify artifacts and resolve the following case scenarios in a lab VM (Remnux/Thunderbird):

### Scenario: "Your Account Is On Hold"

- Inspected the email in **Thunderbird** to find the **sender email address** and **received IP address**.
- Viewed the **message source** to identify the **domain name** used and resolve the **shortened URL** to its real destination.

### Scenario: "Update Payment Info"

- Extracted the **SHA-256 hash** of the email's **PDF attachment** and the **Excel attachment** for reputation lookups.
- Investigated what **vulnerability** the malicious attachment attempted to exploit.

---

## Conclusion

This room tied together the theory from earlier phishing rooms with a practical toolkit: header analyzers to parse routing and authentication data, IP/URL/domain reputation tools to check indicators without direct interaction, URL extraction and hashing to pull artifacts out of the body/attachments efficiently, and sandboxes like ANY.RUN, Hybrid Analysis, and Joe Sandbox to safely detonate and observe suspicious files. Together, these tools let an analyst move from "this looks suspicious" to a fully documented, evidence-backed case.
