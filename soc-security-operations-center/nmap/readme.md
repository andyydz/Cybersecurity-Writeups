# Nmap



![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-blue)
![Category](https://img.shields.io/badge/Category-Network%20Reconnaissance-orange)



> **Key finding:** When the TryHackMe AttackBox wasn't working properly, I connected via OpenVPN directly from my own machine and ran Nmap from my local terminal. That ended up teaching me more than the room itself.

---

## Overview

Nmap is the industry-standard tool for host discovery and port scanning. This writeup documents my hands-on experience from completing TryHackMe's **Nmap: The Basics** room — including how I worked around a broken lab VM, what I found during port scanning, and why understanding scan types matters in a real SOC context.

---

## What I Actually Found

| Investigation | Finding |
|---|---|
| Host discovery | Identified live hosts on the subnet using ping scan (`-sn`) |
| Target IP | Located exact target IP by scanning the provided subnet range |
| Open TCP ports | Found open ports using both Connect and SYN scan methods |
| Web server version | Detected web server name and version using `-sV` flag |
| Flag capture | Successfully retrieved the room flag after full port enumeration |
| VPN workaround | Connected to TryHackMe lab directly via OpenVPN when AttackBox failed |

---

## Challenges & Real Lessons

**1. The lab VM wasn't working — so I went around it**
The TryHackMe AttackBox wasn't responding properly. Instead of waiting, I downloaded the OpenVPN config file, connected directly from my local machine, and ran Nmap from my own terminal via SSH. It worked. That's a real-world problem-solving skill — knowing how to reach a target when your primary tool fails.

**2. SYN scan vs Connect scan — they're not the same**
Connect scan (`-sT`) completes the full TCP handshake — it gets logged. SYN scan (`-sS`) sends a SYN and drops the connection before it completes — stealthier and faster. In a real environment, defenders can see `-sT` scans more easily in logs. This distinction matters for both red and blue team work.

**3. UDP scanning is painfully slow — and that's intentional**
UDP doesn't have a built-in response mechanism like TCP, so Nmap has to wait for timeouts. It taught me to be selective with UDP scans using `-p` rather than scanning all 65535 ports — something every SOC analyst should know when building detection rules.

---

## Hands-On Activities

### Host Discovery
- Used ping scan (`-sn`) to identify live hosts on the network
- Scanned by IP range, subnet (`/24`), and hostname
- Differentiated between local and remote network scanning behavior

### TCP Port Scanning
- Connect Scan (`-sT`): Full TCP handshake — reliable but logged
- SYN Scan (`-sS`): Half-open scan — stealthier, faster
- Limited port scan using `-p` to target specific ports only

### UDP Port Scanning
- Ran UDP scan (`-sU`) against target
- Observed significantly slower scan speed vs TCP
- Identified open UDP services on the target machine

### Version Detection
- Used `-sV` to fingerprint services running on open ports
- Identified exact web server name and version number

### Output & Reporting
- Saved scan results using `-oN` for normal output
- Reviewed output file for documentation purposes

### OpenVPN Direct Connection (Bonus)
- Downloaded `.ovpn` config from TryHackMe
- Connected to the lab network directly from local machine
- Ran all Nmap scans from personal terminal without AttackBox

---

## Key Findings & Tasks

- Discovered live hosts on the subnet using `-sn` ping scan
- Located the exact target IP address by scanning the provided subnet range
- Identified open TCP ports using both Connect scan (`-sT`) and SYN scan (`-sS`)
- Detected the web server name and version running on the target using `-sV`
- Ran a UDP scan (`-sU`) and observed the difference in speed compared to TCP
- Successfully captured the room flag after completing full port enumeration
- Worked around a broken AttackBox by connecting via OpenVPN directly from my local machine
- Saved Nmap output using `-oN` for documentation

---

## What I Learned

- SYN scan (`-sS`) doesn't complete the TCP handshake — it's stealthier and faster than Connect scan, and less likely to appear in basic logs
- UDP scanning is slow because there's no built-in acknowledgment — always use `-p` to limit ports when scanning UDP
- Version detection (`-sV`) is one of the most useful flags in real SOC work — knowing what's running on a port matters more than just knowing it's open
- OpenVPN gives you direct access to TryHackMe lab networks from your own terminal — more realistic and flexible than the browser AttackBox
- When your primary tool fails, find another way — that mindset is what separates good analysts from average ones
- Always save Nmap results with `-oN` — in real SOC environments, scan output becomes part of the incident report

Nmap | OpenVPN | SSH | Linux Terminal

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Host discovery | Asset inventory and rogue device detection |
| Port scanning | Attack surface mapping during incident response |
| Service version detection | Identifying vulnerable or outdated services |
| Scan type selection | Understanding attacker behavior from IDS/IPS alerts |
| VPN-based remote access | Secure access to isolated lab or production networks |
| Output documentation | Creating scan reports for SOC tickets |

---

## Tools Used

Nmap | OpenVPN | SSH | Linux Terminal

---

## Key Takeaways

- SYN scan is stealthier than Connect scan — understanding this helps build better detection rules
- UDP scanning is slow by design — be targeted with `-p` to save time
- Version detection (`-sV`) is critical for identifying vulnerable services during triage
- OpenVPN lets you connect to lab networks directly — more realistic than a browser-based VM
- Always save Nmap output with `-oN` — documentation matters in real SOC workflows

---

*Part of my [TryHackMe SOC & Blue Team writeups](https://github.com/andyydz/TryHackMe-Writeups) series.*
