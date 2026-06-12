Wireshark

Overview

Wireshark is a network protocol analyzer used by SOC analysts to capture and analyze network traffic in real time.

This folder contains my hands-on writeup and notes from completing TryHackMe's Wireshark: The Basics room.

---

Wireshark: The Basics

Platform: TryHackMe
Difficulty: Easy
Status: Completed ✅

Room Link

https://tryhackme.com/room/wiresharkthebasics

---

What I Learned

- Navigating Wireshark's packet list, details, and bytes pane
- Applying display filters (e.g. "http", "tcp")
- Analyzing HTTP traffic and packet metadata
- Using Expert Information to identify anomalies
- Extracting files from PCAP using Export Objects
- Verifying file integrity using "md5sum" in Linux terminal
- Following HTTP streams to analyze web server responses
- Examining capture file properties and SHA256 hashes

---

Hands-on Activities Performed

Packet Analysis

- Investigated packet structures and protocol layers
- Navigated large packet captures using packet numbers
- Analyzed packet metadata and comments
- Located hidden clues within the packet capture

HTTP Traffic Investigation

- Examined HTTP requests and responses
- Identified XML content within network traffic
- Exported transferred objects from captured traffic

File Integrity Verification

- Generated and verified MD5 hashes using Linux terminal
- Compared file hashes for integrity validation
- Reviewed SHA256 values from capture file properties

Wireshark Features Explored

- Expert Information Window
- Packet Comments
- Export Objects
- HTTP Stream Analysis
- Capture File Properties

---

Challenges I Faced

- Linux is case-sensitive — "desktop/" vs "Desktop/" caused command errors.
- Initially assumed the markup language under HTTP traffic was HTML when it was actually XML.
- Packet 12 comment acted as a distraction trap; the actual clue was located much later in the capture.
- Navigating thousands of packets required careful filtering and investigation.

---

Tools Used

- Wireshark
- Linux Terminal
- md5sum

---

SOC Analyst Relevance

This room introduced several tasks commonly performed by SOC analysts:

- Investigating network traffic
- Reviewing packet captures (PCAPs)
- Extracting files from network communications
- Verifying file integrity using cryptographic hashes
- Identifying suspicious activity through packet analysis
- Performing basic incident investigation workflows

These skills form an important foundation for network analysis and threat investigation.

---

## Screenshots
![Completion Badge](screenshots/completion-badge.png)

---

## Expert Informat

![Expert Information Window](screenshots/expert-information-window.png)

---

## MD5 Hash Verification

![MD5 Hash Verification](screenshots/md5sum-terminal.png)

---

## HTTP Export Objects

![HTTP Export Objects](screenshots/httpexportobject.png)

---

## Capture File Properties with SHA256

![Capture File Properties](screenshots/capture-file-properties.png)

---

## Packet Comment Investigation

![Packet Comment Investigation](screenshots/packet12commenttrap.png)
---

Key Takeaways

- Developed foundational Wireshark investigation skills.
- Learned how to inspect and analyze network traffic.
- Practiced recovering files from packet captures.
- Gained experience using cryptographic hashes for verification.
- Improved troubleshooting and investigation methodology.
- Built practical skills relevant to future SOC Analyst responsibilities.

---

Status

✅ Room Completed
