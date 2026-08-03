# TryHackMe — Phishing Analysis Fundamentals

## Introduction

Spam and phishing remain the most common social engineering threats faced by modern organizations. While spam is often low-risk (unsolicited but generally harmless), phishing is far more dangerous — it can trick a user into disclosing sensitive information or unknowingly deploying malware on their system.

### Learning Objectives

- Learn the basics of **email delivery**.
- Explore **email header analysis**.
- Investigate and analyze **email bodies**.
- Learn about different **types of phishing**.
- Analyze emails to identify potential threats.

---

## Anatomy of an Email Address

An email address is made up of two core parts:

```
username@domain.com
```

- **Username** — identifies the specific mailbox/account.
- **Domain name** — identifies the mail server/organization that hosts the mailbox.

---

## Email Delivery

Email delivery relies on a few core protocols:

- **SMTP (Simple Mail Transfer Protocol)** — used to **send** email between servers/clients.
- **POP3 (Post Office Protocol v3)** — **downloads** emails from the server to a single device (removing them from the server, in most configurations).
- **IMAP (Internet Message Access Protocol)** — **syncs** email across multiple devices, keeping messages on the server.

### An Email's Journey

1. A **user sends an email** from their mail client.
2. The **sending mail server** performs a **DNS query** to resolve the recipient domain's mail server (MX record).
3. The DNS response returns the **destination mail server**, and the email is **delivered** to it.
4. The **receiving mail server** places the email into the recipient's **mailbox**.
5. The **recipient receives** the email in their inbox.

**Example:** When `alice@companyA.com` sends an email to `bob@companyB.com`, her mail client hands the message to companyA's SMTP server. That server queries DNS for companyB.com's MX record, finds companyB's mail server address, and relays the message there. companyB's server drops it into Bob's mailbox, where Bob retrieves it via IMAP or POP3.

---

## Email Headers

The email header contains key metadata about a message, including:

- **From** — the claimed sender.
- **To** — the recipient.
- **Reply-To** — the address replies are actually routed to (can differ from "From" — a common phishing red flag).
- **Subject**
- **Date**

### Viewing the Message Source

The raw message source (headers + body) can be viewed in most webmail clients — in the room, this was done in a lab environment (referred to as "Pandaboard"/webmail) using **Ctrl+U** to view the message source. The raw source reveals a lot of useful information, including the **sender's originating IP address**, routing hops, and authentication results (SPF/DKIM/DMARC), which aren't visible in the normal rendered view.

---

## Email Body

Email bodies come in two main formats:

- **Plain text emails** — body is just raw text.
- **HTML-formatted emails** — body is rendered from HTML, allowing styling, links, and embedded content.

### Viewing HTML Content

- **Rendered HTML** — the email as it visually appears to the recipient (as intended by the sender).
- **Raw HTML** — the underlying HTML source, useful for spotting hidden/obfuscated links, mismatched anchor text vs. actual href targets, and hidden tracking elements.

### Reconstructing Attachments

Attachments in the raw source are identified by key MIME headers:

- **Content-Type** — the attachment's file type (e.g., `application/pdf`, `application/zip`).
- **Content-Disposition** — indicates the content should be treated as an attachment (vs. displayed inline), often including the filename.
- **Content-Transfer-Encoding** — how the binary attachment is encoded as text for transport (commonly `base64`).

Decoding the base64 block under these headers reconstructs the original attachment file for safe, isolated analysis.

---

## Types of Phishing

- **Spam** — unsolicited bulk email, usually commercial and low-risk.
- **Phishing** — generic, mass-targeted fraudulent emails aiming to steal credentials or deliver malware.
- **Spear Phishing** — highly targeted phishing aimed at a specific individual or organization, using personalized details to increase credibility.
- **Vishing** — phishing conducted over voice calls (voice + phishing).
- **Smishing** — phishing conducted via SMS text messages.

---

## Anatomy of a Phishing Email

Common red flags to look for when analyzing a suspicious email:

- **Spoofed "From" address** — sender address that mimics a legitimate domain but isn't quite right.
- **Urgent subject or message** — creating pressure to act quickly without thinking.
- **Brand impersonation** — mimicking a trusted company's logo, tone, or formatting.
- **Grammar and spelling issues** — often present in poorly crafted phishing attempts.
- **Generic content** — greetings like "Dear Customer" instead of a real name.
- **Hidden or shortened links** — anchor text that doesn't match the actual destination URL, or link shorteners masking the true target.
- **Malicious attachments** — files designed to execute malware when opened.

---

## Safe Analysis

Practiced safely analyzing sample phishing emails by examining headers, extracting URLs/attachments, and identifying the red-flag indicators above — without directly interacting with any live malicious links or opening attachments outside of a sandboxed environment.

---

## Conclusion

Phishing analysis starts with understanding how email is structured and delivered — from the SMTP/POP3/IMAP protocols that move a message, to the headers and body that carry its content. By learning to read raw headers and HTML source, decode attachments, and recognize the common anatomy of a phishing email (spoofed senders, urgency, brand impersonation, hidden links, malicious attachments), an analyst can reliably separate legitimate email from social engineering attempts — a foundational skill for any SOC analyst.
