# Wireshark

## Overview
Wireshark is a network protocol analyzer used by SOC analysts 
to capture and analyze network traffic in real time.

This folder contains my hands-on writeups and notes from 
TryHackMe's Wireshark rooms.

---

## Wireshark: The Basics
**Platform:** TryHackMe  
**Difficulty:** Easy  
**Status:** Completed ✅

---

## What I Learned
- Navigating Wireshark's packet list, details, and bytes pane
- Applying display filters (e.g. `http`, `tcp`)
- Analyzing HTTP traffic and packet metadata
- Using Expert Information to identify anomalies
- Extracting files from PCAP using Export Objects
- Verifying file integrity using `md5sum` in Linux terminal
- Following HTTP streams to analyze web server responses

---

## Challenges I Faced
- Linux is case-sensitive — `desktop/` vs `Desktop/` caused errors
- Assumed markup language under HTTP was HTML — it was XML
- Packet 12 comment was a distraction trap — real answer was at the very end

---

## Tools Used
- Wireshark
- Linux Terminal
- md5sum

---

## Room Link
https://tryhackme.com/room/wiresharkthebasics
