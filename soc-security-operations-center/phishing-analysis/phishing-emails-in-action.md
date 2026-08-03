# TryHackMe — Phishing Emails in Action

## Introduction

This room builds on Phishing Analysis Fundamentals with hands-on practice analyzing real phishing email scenarios inside a lab mail client (webmail / Thunderbird). Each scenario presents a realistic phishing email, and the goal is to identify the phishing technique(s) used and document the observable red flags.

---

## Scenario 1 — "Cancel Your Order"

**Phishing Techniques Used:** Spoofed email address, URL shortening, branded HTML.

**Observations:**
- Attention-grabbing subject line designed to prompt immediate action.
- Mismatch between the **From display name** and the **actual From email address**.
- Email body used a branded HTML "Cancel Order" button rather than a plain link.
- Inspecting the button's underlying HTML revealed a **suspicious link embedded behind the Cancel button**.
- The link was a shortened URL; checking it (via a URL un-shortening tool) revealed the true, malicious destination hidden behind the shortener.

---

## Scenario 2 — "Track Your Package"

**Phishing Techniques Used:** Spoofed email address, tracking pixel, link manipulation.

**Observations:**
- Subject line and From address inspected first.
- Using **Thunderbird** to inspect the message, a **tracking pixel** (a tiny, invisible embedded image used to confirm when/if the email is opened) was identified.
- The **hyperlink destination did not match the displayed link text** — a classic link manipulation technique.
- The email included a "Download Document" link/attachment as the delivery mechanism.

---

## Scenario 3 — "Urgent Notice" (Credential Harvesting)

**Phishing Techniques Used:** Brand impersonation, link/URL reduction, credential harvesting.

**Observations:**
- Checked the **send date** and an artificial **expiration date** used to create urgency.
- Email contained a "Download Document Here" link that was actually a **shared/shortened URL**.
- Following the link (safely, in the lab) led to a **fake login page** requesting an **email and password** — confirming this was a **credential harvesting** attempt rather than a malware delivery.

---

## Scenario 4 — "Your Account Is On Hold"

**Phishing Techniques Used:** Spoofed email address, sense of urgency, brand impersonation, poor grammar/typos, malicious attachment.

**Observations:**
- Email subject, From address, and brand impersonation checked first.
- Analysis covered **two components**: the **email body** (urgency + grammar issues) and a **PDF attachment**, which was examined for malicious indicators.

---

## Scenario 5 — "Your Recent Purchase"

**Phishing Techniques Used:** Spoofed email address, recipient BCC'd, poor grammar/typos, malicious attachment.

**Observations:**
- Email subject and From address inspected.
- Noted the recipient was **BCC'd** rather than directly addressed — a sign of a mass phishing blast rather than a legitimate targeted receipt.
- Attachment analyzed for malicious content.

---

## Scenario 6 — "Scheduled Shipment"

**Phishing Techniques Used:** Spoofed email address, brand impersonation, malicious attachment.

**Observations:**
- Brand impersonation noted, along with a **mismatched From address**.
- Email body included an **XLSX (Excel) attachment** containing a **hyperlink/macro leading to an executable**.
- If successfully executed, this attack chain could allow the attacker to **establish persistence**, **exfiltrate data**, and potentially **deploy ransomware** — all via a weaponized Excel file acting as the initial execution vector.

---

## Conclusion

Working through these six scenarios reinforced how varied phishing delivery and technique combinations can be — from HTML button obfuscation and URL shorteners, to tracking pixels, BCC'd mass mailings, and weaponized Office attachments. Consistently checking the **From address vs. display name, links vs. their true destination, attachment types, and send/expiration metadata** surfaced the red flags in every case, confirming that a methodical header-and-body analysis process is effective regardless of the specific phishing technique used.
