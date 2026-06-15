# TCPdump: The Basics — SOC Lab Writeup



![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

 

![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)

 

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-blue)

 

![Category](https://img.shields.io/badge/Category-Network%20Analysis-orange)



> **Key finding:** TCPdump filters look simple but get powerful fast. Binary operations on TCP flags let you isolate exact packet types — something no basic GUI tool exposes this cleanly.

---

## Overview

TCPdump is a command-line packet analyzer used to capture and inspect network traffic without a GUI. This writeup documents my hands-on experience from completing TryHackMe's **TCPdump: The Basics** room — including the filters I used, what I found in the DNS capture, and why this tool matters more than Wireshark in certain SOC scenarios.

---

## What I Actually Found

| Investigation | Finding |
|---|---|
| DNS traffic | Captured DNS queries on port 53 — plaintext, readable without decryption |
| MAC address discovery | Used `-e` flag to reveal link-layer headers and identify host MAC via ARP |
| ARP request | Identified the ARP request sent by the host to resolve IP to MAC |
| Hex inspection | Used `-XX` to display raw packet bytes — confirmed payload content |
| Advanced filter | Applied binary operation `tcp[13] & 2 != 0` to isolate SYN packets specifically |

---

## Challenges & Real Lessons

**1. DNS is not private by default**
Capturing DNS queries showed them in plaintext — no decryption needed. In a real SOC, DNS logs are often the first place to look for C2 beaconing or data exfiltration via DNS tunneling.

**2. Binary filtering feels confusing at first**
`tcp[13] & 2 != 0` looks intimidating. But once you understand that byte 13 of the TCP header holds the flags, it makes complete sense. SYN = bit 1, so `& 2` isolates it. This level of control isn't possible in basic Wireshark filters.

**3. TCPdump is the real-world tool**
Most servers don't have a GUI. If you're SSH'd into a Linux box during an incident, TCPdump is what you use — not Wireshark. This room made that very clear.

---

## Hands-On Activities

### Basic Packet Capture
- Captured live traffic on a network interface using `-i eth0`
- Used verbosity flags (`-v`, `-vv`) to get more packet detail
- Saved captures to `.pcap` files using `-w` for later analysis

### Filtering Expressions
- Filtered by host IP and port number
- Isolated DNS traffic using `port 53`
- Combined filters using `and`, `or`, `not` operators

### DNS Query Analysis
- Captured and read DNS queries in real time
- Identified query type, domain name, and response IP
- Confirmed DNS traffic is unencrypted by default

### Advanced Filtering
- Used binary operations on TCP header bytes to filter by flag type
- Displayed raw hex and ASCII using `-XX`
- Revealed link-layer headers (MAC addresses) using `-e`
- Identified ARP request from host to resolve target IP

### Features Used
- `-i` interface selection
- `-v` / `-vv` verbosity
- `-XX` hex + ASCII display
- `-e` link-layer headers
- `-w` / `-r` write and read pcap files
- BPF (Berkeley Packet Filter) syntax

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| CLI packet capture | Capturing traffic on servers without GUI access |
| DNS query analysis | Detecting DNS tunneling or C2 beaconing |
| MAC address identification | Device attribution on LAN during investigation |
| Advanced BPF filtering | Isolating specific attack traffic from noisy captures |
| Hex byte inspection | Manual payload analysis when automated tools miss it |

---

---

## Tools Used

```
TCPdump | Linux Terminal | BPF Filters
```

---

## Key Takeaways

- TCPdump is the go-to tool when there's no GUI — every SOC analyst needs it
- DNS queries are plaintext — easy to capture and analyze for suspicious domains
- The `-e` flag exposes MAC addresses — useful for LAN-level device identification
- Binary filtering on TCP header bytes gives surgical precision no GUI tool matches
- Always save captures with `-w` during real incidents for evidence preservation

---

*Part of my [TryHackMe SOC & Blue Team writeups](https://github.com/andyydz/TryHackMe-Writeups) series.*
