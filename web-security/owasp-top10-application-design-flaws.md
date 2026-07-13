![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Room](https://img.shields.io/badge/Room-OWASP%20Top%2010%3A%20Application%20Design%20Flaws-blue)
![Category](https://img.shields.io/badge/Category-Web%20Security-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)



> **Key Finding:** The three categories in this room — misconfiguration, supply chain, cryptographic failure, and insecure design — all share a root cause: they're baked in before an attacker ever sends a request, which means they can't be patched away, only designed out from the start.

## Overview

**Room:** OWASP Top 10 2025: Application Design Flaws


This room covers four OWASP Top 10 categories rooted in how an application is built and configured rather than how it's coded line-by-line: A02 Security Misconfiguration, A03 Software Supply Chain Failures, A04 Cryptographic Failures, and A06 Insecure Design. Each section defines the vulnerability class, explains why it matters, walks through common real-world patterns, covers prevention, and includes a hands-on challenge.

## What I Actually Found

| Category | What It Is | Why It Matters | Common Pattern |
|---|---|---|---|
| **A02: Security Misconfiguration** | Insecure default settings, unnecessary features enabled, missing hardening | Often the easiest entry point — no exploit dev needed, just default creds or exposed admin panels | Default credentials left active, verbose error messages, unnecessary services/ports exposed, missing security headers |
| **A03: Software Supply Chain Failures** | Vulnerabilities introduced via third-party dependencies, libraries, or build pipelines | A single compromised upstream package can silently affect every application that depends on it | Outdated/unpatched dependencies, unverified third-party packages, compromised CI/CD pipelines |
| **A04: Cryptographic Failures** | Weak, missing, or misapplied cryptography protecting data in transit or at rest | Sensitive data (credentials, PII, tokens) becomes trivially exposed even if other controls hold | Weak/outdated algorithms (e.g., MD5/SHA-1 for passwords), hardcoded keys, missing encryption in transit (no TLS) |
| **A06: Insecure Design** | Security flaws baked into the architecture/business logic itself, not a coding bug | No amount of secure coding fixes a fundamentally flawed design — it has to be re-architected | Missing threat modeling, business logic that trusts client-side checks, design that ignores abuse cases (including AI-era risks like prompt injection or model abuse) |

## Hands-On Activities

- **A02 Security Misconfiguration:** Reviewed why misconfiguration matters (low effort, high impact for attackers), examined common patterns (default creds, verbose errors, exposed services), covered prevention (hardening baselines, disabling unused features, automated config scanning), and completed the hands-on challenge to exploit a misconfigured instance.
- **A03 Software Supply Chain Failures:** Explored how vulnerabilities enter through dependencies and build pipelines rather than first-party code, and worked through the challenge demonstrating exploitation of a supply-chain weakness.
- **A04 Cryptographic Failures:** Covered what qualifies as a cryptographic failure, why weak/misapplied crypto undermines confidentiality and integrity even when other controls are solid, and completed the challenge exploiting a cryptographic weakness (e.g., recovering data protected by a weak algorithm).
- **A06 Insecure Design:** Defined insecure design as distinct from implementation bugs, reviewed real-world examples, discussed secure-by-design principles, examined how insecure design manifests differently in the AI era (e.g., inadequate guardrails around AI-driven features), and covered how to design securely from the outset (threat modeling, abuse-case planning, secure defaults).

## SOC Analyst Relevance

| Category | SOC Use Case |
|---|---|
| A02: Security Misconfiguration | Explains why baseline configuration audits and default-credential scans should be routine, not reactive |
| A03: Software Supply Chain Failures | Justifies SBOM (Software Bill of Materials) tracking and dependency vulnerability monitoring as ongoing SOC/vuln-management tasks |
| A04: Cryptographic Failures | Flags where to look during data-exposure incidents — was data actually encrypted, or "encrypted" with a broken algorithm? |
| A06: Insecure Design | Reminds analysts that some findings aren't fixable with a patch — they need to be escalated as architecture/design review items |
| AI-era insecure design | Increasingly relevant as orgs adopt AI features — SOC needs to consider new abuse patterns (prompt injection, data leakage via AI outputs) that don't fit older vulnerability categories |

## Key Takeaways

- A02, A03, A04, and A06 all sit "upstream" of the code itself — in configuration, dependencies, cryptographic choices, and architecture — which is why they require process and design fixes, not just patches.
- Security misconfiguration remains one of the highest-ROI attack paths because it requires no exploit development, just checking for defaults that were never changed.
- Supply chain risk is only growing — trusting a dependency is now effectively trusting everyone who can push to that dependency's repo or pipeline.
- Cryptographic failures are often invisible until exploited — "encrypted" doesn't mean secure if the algorithm or key management is weak.
- Insecure design is the hardest category to fix late, and the room's inclusion of AI-era design risk is a good reminder that this category keeps expanding as application architectures change.

---
📁 More writeups: [my writeups repo — add your link here]
