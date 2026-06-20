# Networking Tool: Ping — SOC Lab Writeup





> **Key finding:** Ping is more than "is it up or down" — round-trip time and packet loss patterns reveal latency issues and unstable links before they ever hit a ticket queue.

---

## Overview

Ping is one of the most fundamental networking tools, used to test reachability between a host and a target by sending ICMP Echo Request packets and measuring the Echo Reply. This writeup documents my hands-on walkthrough of TryHackMe's **Networking Tool: Ping** room, covering basic usage, IPv4-specific pings, interval control, and verbose output.


---

## What I Actually Found

| Investigation | Finding |
|---|---|
| Basic ping to bbc.co.uk | Continuous ICMP Echo Requests sent to target host, displaying response time per packet |
| Packet statistics | Summary shown after stopping ping — packets sent, received, lost, and round-trip time (min/avg/max) |
| IPv4-forced ping | Using the IPv4 flag forces resolution and requests over IPv4 instead of defaulting to IPv6 |
| Interval-controlled ping | Changing the interval between requests slows or speeds up how frequently ICMP packets are sent |
| Verbose output | More detailed packet-level information displayed per request compared to default output |

---

## Hands-On Activities

### Basic Ping Usage
- Ran a continuous ping against `bbc.co.uk`
- Observed real-time response times for each ICMP packet
- Reviewed final packet statistics: sent, received, lost, and RTT min/avg/max

### IPv4-Specific Ping
- Forced the ping request to use IPv4 explicitly
- Compared behavior against default ping resolution

### Adjusting Ping Interval
- Modified the interval flag to change time between each Echo Request
- Observed how shorter intervals increase request frequency, useful for stress-testing reachability, while longer intervals reduce network noise

### Verbose Ping Output
- Enabled verbose mode to get more detailed per-packet output
- Compared verbose results against standard ping output for additional diagnostic detail

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| ICMP fundamentals | Recognizing normal vs abnormal ICMP traffic in packet captures |
| Reachability testing | First-line triage step when investigating host/network availability alerts |
| Packet loss & RTT analysis | Identifying latency issues or unstable links during incident investigation |
| IPv4 vs IPv6 awareness | Avoiding misdiagnosis when dual-stack hosts behave differently per protocol |
| Verbose diagnostics | Pulling deeper detail when default tool output isn't enough during an investigation |

---

## Key Takeaways

- Ping relies on ICMP Echo Request/Reply — a foundational protocol worth understanding at the packet level, not just the command line
- Packet loss and RTT statistics are quick indicators of network health during triage
- Forcing IPv4 avoids ambiguity on dual-stack systems where IPv6 may be tried first by default
- Adjusting the interval is useful for both testing stability and avoiding unnecessary network noise
- Verbose output is a simple way to get more diagnostic detail without switching tools

---

*Part of my [TryHackMe SOC & Blue Team writeups](https://github.com/andyydz/TryHackMe-Writeups) series.*
