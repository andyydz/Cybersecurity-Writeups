# Phishing Prevention

> **TryHackMe Room — Phishing Prevention**

## Overview

This room focused on understanding how organizations detect, prevent, and respond to phishing through a combination of **email authentication, message analysis, network protocols, technical controls, and user awareness**.

The room provided practical exposure to technologies and techniques used to determine whether an email is legitimate, suspicious, or potentially malicious.

Key areas covered included:

* SPF
* DKIM
* DMARC
* MIME
* SMTP
* Email header analysis
* Email and attachment inspection
* Anti-phishing technologies
* Email filtering
* Secure Email Gateways
* Link rewriting
* Sandboxing
* Security awareness and user training

---

## 🎯 Learning Objectives

By completing this room, I worked toward understanding:

* Core email security mechanisms
* How SPF validates sending infrastructure
* How DKIM provides message integrity and domain-level authentication
* How DMARC uses authentication results to define email-handling policies
* How SMTP communication works
* How to inspect SMTP responses and network traffic
* How email headers can reveal useful security information
* How MIME handles email content and attachments
* How organizations implement technical anti-phishing controls
* Why security awareness and user training remain important defensive layers

---

# 1. Email Security Fundamentals

Email is a major communication mechanism but is also commonly abused for phishing, spoofing, malware delivery, credential theft, and social engineering.

Because email can be manipulated at multiple stages, organizations use several security mechanisms to establish trust and identify suspicious messages.

A simplified email-security model is:

```text
Email
  ↓
SMTP Communication
  ↓
Sender Authentication
  ├── SPF
  ├── DKIM
  └── DMARC
  ↓
Email Filtering
  ↓
Content / Attachment Analysis
  ↓
User
```

---

# 2. Sender Policy Framework (SPF)

**Sender Policy Framework (SPF)** is an email authentication mechanism that allows a domain owner to specify which mail servers are authorized to send email on behalf of that domain.

An SPF policy is published through DNS.

Conceptually:

```text
Sending Server
      ↓
Recipient checks sender domain
      ↓
DNS SPF Record
      ↓
Is the sending server authorized?
      ↓
SPF Result
```

---

## 2.1 SPF Records

SPF records are stored in DNS as TXT records.

They can specify which hosts or services are authorized to send mail for a domain.

SPF helps reduce certain forms of sender-address spoofing by allowing receiving systems to verify whether the sending infrastructure is authorized.

---

## 2.2 SPF Verification Results

SPF checks can produce different outcomes depending on the sender's authorization and the domain's policy.

The verification result can contribute to the recipient's decision about how an email should be handled.

---

## 2.3 SPF Intent and Action

An important concept is separating:

**What the authentication mechanism determines**

from:

**What the receiving organization decides to do with the result.**

An SPF failure does not automatically mean that a message is malicious. Organizations can use authentication results as one signal among several when evaluating email.

---

# 3. DKIM

**DomainKeys Identified Mail (DKIM)** provides cryptographic authentication for email messages.

A sending system uses a private key to generate a digital signature associated with the email.

The receiving system can use the corresponding public key published through DNS to verify the signature.

Conceptually:

```text
Email
  ↓
Private Key
  ↓
DKIM Signature
  ↓
Recipient
  ↓
Public Key
  ↓
Signature Verification
```

DKIM can help verify that signed parts of the message have not been modified after signing and that the message is associated with the signing domain.

---

# 4. DMARC

**Domain-based Message Authentication, Reporting, and Conformance (DMARC)** builds on SPF and DKIM.

DMARC allows domain owners to publish policies describing how receiving systems should handle messages that fail authentication checks under the relevant DMARC requirements.

Conceptually:

```text
Email
  ↓
SPF Check
  +
DKIM Check
  ↓
DMARC Evaluation
  ↓
Policy / Handling Decision
```

DMARC can also provide reporting capabilities that help organizations understand how their domains are being used for email.

---

## 4.1 SPF + DKIM + DMARC

These technologies serve different but complementary purposes:

| Technology | Primary Purpose                                                  |
| ---------- | ---------------------------------------------------------------- |
| **SPF**    | Identifies authorized sending infrastructure                     |
| **DKIM**   | Provides cryptographic message authentication                    |
| **DMARC**  | Uses authentication results to enforce domain-level email policy |

Together they form an important part of modern email security.

---

# 5. Email Headers

Email headers contain metadata about an email message.

Headers can provide information such as:

* Sender information
* Recipient information
* Mail servers involved
* Timestamps
* Authentication results
* Message identifiers
* Routing information

Security analysts can use headers to investigate suspicious messages and identify inconsistencies.

---

## 5.1 Message Header Analysis

Important fields can include:

* `From`
* `To`
* `Date`
* `Subject`
* `Message-ID`
* `Received`
* Authentication-related headers

The `Received` headers can be particularly useful for understanding the path a message took through mail servers.

---

# 6. Sample Spam Email Analysis

Analyzing a suspicious email header can reveal indicators that may not be visible from the email's user-facing content.

An analyst may investigate:

```text
Sender identity
      ↓
Sending infrastructure
      ↓
Received headers
      ↓
SPF result
      ↓
DKIM result
      ↓
DMARC result
      ↓
Suspicious indicators
```

This approach can help distinguish legitimate messages from spoofed or suspicious communications.

---

# 7. Domain Checking and Email Security Tools

Domain and email security tools can be used to inspect:

* SPF records
* DKIM configuration
* DMARC policies
* DNS information
* Email authentication status

These tools can assist security analysts in validating an organization's email-security configuration.

---

# 8. Administrative Email Security Tooling

Administrative tooling can provide visibility into email-security events and configuration.

For organizations using managed email platforms, administrative consoles can help security teams investigate:

* Message delivery
* Authentication results
* Suspicious messages
* Security policies
* Email activity

This type of visibility can support both prevention and incident investigation.

---

# 9. MIME

**Multipurpose Internet Mail Extensions (MIME)** allows email messages to carry different types of content.

MIME enables email to contain:

* Plain text
* HTML
* Images
* Documents
* Other attachments

This is important for security because attachments can contain malicious content.

---

# 10. Email and Attachment Inspection

Email content and attachments should be treated carefully because phishing campaigns can use malicious documents, scripts, links, or other payloads.

Security analysis can include:

* Inspecting the sender
* Reviewing headers
* Checking authentication results
* Examining links
* Inspecting attachment types
* Evaluating suspicious content
* Checking whether attachments contain potentially malicious payloads

The goal is to identify indicators that distinguish legitimate communication from malicious or suspicious messages.

---

# 11. SMTP Analysis

**Simple Mail Transfer Protocol (SMTP)** is used for transferring email between mail systems.

Understanding SMTP is useful for security analysis because email security investigations may require examining how messages are transmitted between systems.

---

## 11.1 SMTP Responses

SMTP servers return response codes and messages that indicate the result of operations.

Analyzing these responses can provide information about:

* Connection status
* Authentication
* Mail delivery
* Recipient validation
* Server behavior
* Errors

Understanding SMTP behavior helps analysts interpret email-related network activity.

---

# 12. Analyzing SMTP Network Traffic

Network traffic analysis can provide additional visibility into email communication.

Tools such as **Wireshark** can be used to inspect network packets and identify protocol behavior.

A security analyst can investigate:

```text
Network Traffic
      ↓
SMTP Packets
      ↓
Protocol Analysis
      ↓
Server Responses
      ↓
Security Indicators
```

This connects email security with broader network-security analysis.

---

# 13. How Organizations Prevent Phishing

Organizations generally use multiple defensive layers rather than relying on a single anti-phishing mechanism.

A simplified model is:

```text
Sender Authentication
        ↓
Email Filtering
        ↓
Secure Email Gateway
        ↓
Link Protection
        ↓
Attachment Sandboxing
        ↓
User Awareness
        ↓
Incident Reporting
```

---

# 14. Technical Phishing Defenses

## 14.1 Email Filtering

Email filters analyze messages and attempt to identify suspicious or malicious email.

Filtering can consider factors such as:

* Sender reputation
* Authentication results
* Message content
* URLs
* Attachments
* Known malicious indicators

---

## 14.2 Secure Email Gateways

Secure Email Gateways provide centralized security controls for inbound and outbound email.

They can help organizations:

* Filter spam
* Detect phishing
* Scan attachments
* Inspect URLs
* Enforce email policies
* Block suspicious messages

---

## 14.3 Link Rewriting

Link rewriting can redirect links through a security service that checks the destination before allowing the user to access it.

This can help protect users against malicious URLs.

---

## 14.4 Sandboxing

Sandboxing executes suspicious files or content within an isolated environment.

This allows security systems to observe potentially malicious behavior without exposing production systems directly to the payload.

---

# 15. User-Facing Security Controls

Technical controls are only one part of phishing prevention.

Users are also an important defensive layer.

Security awareness programs can teach users to identify:

* Suspicious senders
* Unexpected attachments
* Urgent requests
* Credential requests
* Suspicious URLs
* Impersonation attempts
* Unusual payment requests

Users should also know how to report suspected phishing attempts.

---

# 16. Phishing Investigation Workflow

The concepts from this room can be combined into a basic investigation workflow:

```text
Suspicious Email
       ↓
Inspect Sender
       ↓
Analyze Headers
       ↓
Check SPF
       ↓
Check DKIM
       ↓
Evaluate DMARC
       ↓
Inspect URLs
       ↓
Inspect Attachments
       ↓
Analyze SMTP / Network Evidence
       ↓
Determine Risk
       ↓
Report / Block / Investigate
```

This provides a useful foundation for email-based security investigations.

---

# 17. SOC Relevance

Phishing is highly relevant to Security Operations Center operations because phishing frequently acts as an initial access vector for broader attacks.

SOC analysts may investigate:

* Suspicious emails
* Email authentication failures
* Malicious URLs
* Malicious attachments
* Credential harvesting attempts
* Spoofed domains
* Compromised accounts
* Suspicious SMTP activity

The techniques practiced in this room provide foundational skills for **email threat analysis and incident investigation**.

---

# 18. Key Takeaways

After completing the room, I developed an understanding of:

* Email security fundamentals
* SPF
* SPF records and verification results
* DKIM
* DKIM signatures
* DMARC
* Email authentication alignment and policy
* MIME
* SMTP
* SMTP response analysis
* Email header analysis
* Spam email investigation
* Domain security checking
* Email administrative tooling
* Email and attachment inspection
* Wireshark-based network analysis
* Secure Email Gateways
* Email filtering
* Link rewriting
* Sandboxing
* Security awareness and phishing prevention

---

# 19. Skills Demonstrated

This room helped develop practical knowledge in:

* Email Security
* Phishing Analysis
* Email Header Analysis
* Network Traffic Analysis
* SPF / DKIM / DMARC
* SMTP
* MIME
* Security Tooling
* Threat Detection
* Security Awareness
* SOC Investigation Fundamentals

---

# 20. Conclusion

Phishing prevention requires multiple defensive layers.

Email authentication mechanisms such as **SPF, DKIM, and DMARC** help establish trust in email identity and improve detection of spoofed messages.

Network and content analysis provide additional visibility, while technical controls such as **email filtering, Secure Email Gateways, link rewriting, and sandboxing** help reduce the likelihood of malicious messages reaching users.

However, technical controls alone are not sufficient. User awareness, reporting procedures, and security training remain important components of an effective anti-phishing strategy.

The room provided a practical foundation for understanding how email security mechanisms work together and how a security analyst can investigate suspicious email activity.

---

## TryHackMe

**Room:** Phishing Prevention
**Platform:** TryHackMe
**Focus:** Email Security, Phishing Prevention, SPF, DKIM, DMARC, SMTP Analysis, and Email Threat Detection
