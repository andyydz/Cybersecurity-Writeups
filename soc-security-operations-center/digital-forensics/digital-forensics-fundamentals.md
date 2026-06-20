# Digital Forensics Fundamentals — TryHackMe Writeup



![Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)
![Category](https://img.shields.io/badge/Category-Digital%20Forensics-blue)



>  **Key Finding:** Digital forensics follows a strict four-stage methodology — **Collection, Examination, Analysis, Reporting** — and the integrity of every step depends on proper chain of custody and write-blocking to keep evidence court-admissible.

## Overview

This room covers the foundations of digital forensics: how investigations connect to law enforcement after a cybercrime, the standard forensic methodology, the different forensic specialties, evidence handling procedures, and core Windows forensic tools. It ends with a hands-on investigation — recovering metadata from a PDF and an image to track down a missing cat.

🔗 Room link: [TryHackMe — Digital Forensics Fundamentals](https://tryhackme.com/room/digital-forensics-fundamentals)

## What I Actually Found

| Concept | Detail |
|---|---|
| Forensic Methodology | Collection → Examination → Analysis → Reporting |
| Forensic Types | Network, Database, Memory, Mobile, Malware, Email, Cloud, Disk forensics |
| Evidence Handling | Proper authorization, chain of custody documentation, write blockers |
| Windows Forensic Tools | Disk imaging, memory imaging, FTK Imager / Autopsy, Volatility |
| Investigation Artifacts | PDF metadata, image EXIF data (GPS coordinates, camera model) |

## Hands-On Activities

### Digital Forensics Methodology
Learned the four-stage process every investigation follows:
- **Collection** — acquiring evidence from the source without altering it
- **Examination** — identifying and extracting relevant data
- **Analysis** — interpreting the data to reconstruct events
- **Reporting** — documenting findings in a way that's clear and legally defensible

### Types of Digital Forensics
Covered the major specialties and how each maps back to the same core methodology, just applied to a different evidence source:
- **Network Forensics** — traffic and log analysis
- **Database Forensics** — database access/manipulation history
- **Memory Forensics** — volatile data captured from RAM
- **Mobile Forensics** — data from smartphones/devices
- **Malware Forensics** — analyzing malicious code behavior
- **Email Forensics** — header and content analysis for phishing/fraud
- **Cloud Forensics** — evidence from cloud-hosted services
- **Disk Forensics** — data recovery and analysis from storage drives

### Evidence Acquisition & Chain of Custody
This was the most interesting conceptual section — treating evidence handling like an actual investigation team workflow:
- **Proper authorization** required before any evidence is touched
- **Chain of custody** — documented record of who collected, handled, and accessed evidence, and when, to preserve its integrity for legal proceedings
- **Write blockers** — hardware/software tools that prevent any modification to original evidence during acquisition, a non-negotiable part of a forensic investigator's toolkit

### Windows Forensics Tools
Got an introduction to the core toolkit used in Windows-based investigations:
- **Disk imaging** — creating a bit-for-bit copy of a drive for analysis without touching the original
- **Memory imaging** — capturing the contents of RAM for volatile data analysis
- **FTK Imager / Autopsy** — tools used to create and analyze forensic images
- **Volatility** — memory forensics framework for analyzing RAM dumps

### Practical Exercise: The Missing Cat Investigation
A scenario-based investigation (styled like a detective case) using a provided VM to recover metadata clues:

**PDF Metadata Analysis**
- Used `pdfinfo` to extract metadata from a PDF file
- Recovered the document **creator**, **file size**, and other embedded metadata used to identify the author of the letter

**Image EXIF Data Analysis**
- Used `exiftool` to extract EXIF metadata from an image
- Recovered embedded **GPS coordinates** — had to cross-reference them manually since the raw coordinates didn't resolve directly to a readable address
- Recovered the **camera model** used to take the photo from the EXIF data

These two metadata trails combined to piece together the case (author identity + location + device used).

**Flag:** `[REDACTED]`

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Forensic Methodology (CEAR) | Structures any post-incident investigation a SOC hands off to IR/forensics teams |
| Chain of Custody | Critical when an incident escalates to legal/HR action — improper handling can void evidence |
| EXIF/Metadata Analysis | Common technique in phishing investigations, insider threat cases, and OSINT during triage |
| PDF Metadata Extraction | Useful for analyzing malicious email attachments or verifying document authenticity |
| Disk/Memory Imaging Awareness | Foundational knowledge for escalating an incident to a forensics team, even if SOC L1 doesn't perform imaging directly |

## Key Takeaways

- Every forensic discipline (network, memory, mobile, etc.) is just the same Collection → Examination → Analysis → Reporting methodology applied to a different evidence type.
- Chain of custody isn't bureaucracy — it's what makes evidence usable in a legal or HR context. Get it wrong and the whole investigation can be challenged.
- Metadata (PDF info, EXIF data) is an underrated, low-effort goldmine — file authorship, GPS location, and device fingerprints are often sitting in plain sight.
- Write blockers exist for one reason: never let an investigation contaminate its own evidence.

---
📂 Part of my [TryHackMe Writeups series](https://github.com/andyydz/TryHackMe-Writeups)
