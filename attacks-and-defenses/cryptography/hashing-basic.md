![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Cryptography-blue?style=for-the-badge)



> **Key Finding:** Hash functions produce a fixed-size output from any input — and with the right tools, cracked hashes reveal plaintext passwords hiding in plain sight.

## Overview
This room covers the fundamentals of hashing — how hash functions work, why they matter for security, and how attackers crack them. It includes hands-on tasks involving password hash identification, cracking with Hashcat and John the Ripper, and integrity verification using HMAC.



---

## What I Actually Found

| Topic | Finding |
|---|---|
| Hash functions | Produce a fixed-size hexadecimal output from any input string |
| Hash collision | Two different inputs producing the same hash output |
| Insecure storage | Passwords stored in plaintext or with weak encryption algorithms |
| Rainbow tables | Precomputed hash-to-password lookup tables used to crack unsalted hashes |
| Password cracking tools | Hashcat (GPU-based), John the Ripper (CPU-based, works on VMs out of the box) |
| Online cracking | CrackStation and Hashes.com can identify and crack common hashes |
| HMAC | Hash-based Message Authentication Code used for integrity checking |
| Windows hashes | NTLM format; Linux hashes prefixed with `$y$`, `$6$`, `$1$` etc. depending on algorithm |
| Cisco hashes | Algorithm identified by prefix — `$9$` indicates a specific Cisco hashing algorithm |

---

## Hands-On Activities

### Connecting to the Virtual Machine
SSH'd into the room's target machine using provided credentials to perform tasks directly on the system.

### Insecure Password Storage
Explored a file containing stored passwords — including plaintext and weakly encrypted entries. Located the 20th password in the file, highlighting why plaintext and weak encryption storage is dangerous in real environments.

### Identifying Hash Types
Practiced recognizing hash formats by prefix and length:
- Linux password hashes use prefixes like `$6$` (SHA-512), `$1$` (MD5), `$y$` (yescrypt)
- Windows uses NTLM hashes
- Cisco IOS uses `$9$` to indicate its hashing algorithm
- Hash mode numbers used in Hashcat differ per algorithm

### Cracking Hashes
Used **Hashcat** (GPU) and **John the Ripper** (CPU) to crack provided hashes against a wordlist. John the Ripper works out of the box on the TryHackMe VM. Also used online tools — **CrackStation** and **Hashes.com** — to verify cracked values.

### Rainbow Tables & Salting
Manually checked how a rainbow table attack works against unsalted hashes. Demonstrated how adding a salt prevents rainbow table lookups by making identical passwords produce different hashes.

### Hashing for Integrity Checking
Used SHA-256 to verify file integrity on Windows. Explored HMAC as a method for both integrity and authenticity checking, and identified the correct Hashcat mode number for HMAC-based hashing.

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Hash identification | Recognizing credential formats in logs and memory dumps |
| Password cracking | Supporting incident response and forensic investigations |
| Rainbow table awareness | Understanding why unsalted hashes are a critical vulnerability |
| HMAC & integrity checking | Verifying file and log integrity during investigations |
| Tool usage (Hashcat / JtR) | Standard tools in SOC and DFIR workflows |
| Online hash lookup | Quick triage of compromised credentials in threat intel |

---

## Key Takeaways

- A hash function always produces a fixed-size output regardless of input size
- Hash collisions are a known weakness — older algorithms like MD5 are vulnerable
- Storing passwords in plaintext or with weak encryption is a critical security failure
- Salting passwords defeats rainbow table attacks by ensuring unique hashes per password
- Hashcat leverages GPU power; John the Ripper runs on CPU and works natively on VMs
- HMAC combines hashing with a secret key for both integrity and authentication
- Hash prefixes in Linux and Cisco configs immediately reveal the algorithm in use

---

*Part of my [TryHackMe Writeups](https://github.com/andyydz/TryHackMe-Writeups) portfolio — documenting my SOC analyst journey.*
