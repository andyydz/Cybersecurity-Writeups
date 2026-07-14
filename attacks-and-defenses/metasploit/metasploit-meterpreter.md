![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-orange)
![Category](https://img.shields.io/badge/Category-Exploitation%20Basics-blue)



>  **Key Finding:** Meterpreter turns a single successful exploit into a full post-exploitation toolkit — from process migration and credential dumping (via Kiwi/Mimikatz) to filesystem search — all without dropping a new payload to disk.

## Overview

Room: **Metasploit: Meterpreter**
Room Link: [TryHackMe - Metasploit Meterpreter](https://tryhackme.com/room/metasploitmeterpreter)

This room covers the Meterpreter payload in depth — its variants, core command categories, and practical post-exploitation techniques including process migration, hash dumping with Kiwi, and locating sensitive credentials on a compromised host.

## What I Actually Found

| Area | Details |
|------|---------|
| Payload Type | Meterpreter — advanced, in-memory Metasploit payload |
| Payload Flavors | Multiple Meterpreter variants (e.g. `windows/meterpreter/reverse_tcp`, staged vs. stageless) set via `msfvenom`/module `set PAYLOAD` |
| Command Categories | Core, File System, Networking, System, Other |
| Key Post-Exploitation Commands | `help`, `ps`, `migrate`, `hashdump`, `search`, `shell` |
| Credential Access | Kiwi extension (Mimikatz integration) for hash/credential dumping |
| Challenge Goal | Identify compromised computer name, hash owner, cleartext password, and locate a hidden credential in a text file |

## Hands-On Activities

**1. Meterpreter Introduction & Flavors**
Reviewed what makes Meterpreter different from a standard shell payload (runs in memory, extensible via loaded modules) and looked at the different Meterpreter flavors available depending on target OS/architecture, setting the payload in the same way practiced in earlier Metasploit rooms.

**2. Exploring Commands with `help`**
Ran `help` inside an active Meterpreter session to review all available command categories:
- **Core commands** — session/background management
- **File system commands** — navigating and transferring files on the target
- **Networking commands** — viewing interfaces, routes, connections
- **System commands** — OS-level info gathering
- **Other commands** — misc utilities and extensions

**3. Process Enumeration & Migration**
Used `ps` to list running processes on the target, then used `migrate <PID>` to move the Meterpreter session into a more stable/less suspicious process — reducing the chance of losing the session if the original exploited process crashed or got killed.

**4. Credential Dumping — `hashdump`**
Ran `hashdump` to pull the local SAM database hashes from the target, capturing usernames and NTLM hashes for accounts on the box.

**5. Kiwi (Mimikatz) Post-Exploitation Challenge**
Loaded the Kiwi extension and used it to go beyond hashdump — extracting cleartext credentials where available. Worked through the challenge objectives:
- Identified the **target computer's name**
- Identified **who owned/created a specific hash**
- Recovered the **cleartext password** for one user account
- Used `search` to locate a specific text file on the filesystem
- Opened the file and found a **stored password** (for a "Twitter" account referenced in the room) and a hidden **secret** contained within it

**6. Shell Access**
Dropped into a native `shell` from Meterpreter when a standard OS shell was needed for commands not covered by Meterpreter's built-ins.

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Meterpreter command categories | Recognizing in-memory payload behavior that won't show up as a dropped file |
| Process migration (`migrate`) | Spotting process injection/hollowing patterns during EDR investigation |
| `hashdump` / Kiwi credential access | Understanding credential theft TTPs (mirrors real Mimikatz activity in the wild) |
| Filesystem `search` for credentials | Knowing what attackers look for post-compromise (stored passwords, secrets in plaintext files) |
| Shell fallback from Meterpreter | Recognizing mixed shell/Meterpreter activity in process trees during forensics |

## Key Takeaways

- Meterpreter's in-memory, no-disk-write design is exactly why detecting it relies on behavioral/EDR telemetry rather than file-based AV signatures.
- Process migration is a key persistence/stealth technique — as a SOC analyst, unexpected parent-child process relationships or memory injection alerts should be investigated with this in mind.
- Finding cleartext credentials sitting in a plaintext file on a target is a very real, very common finding — reinforces why credential hygiene (no plaintext secrets) is a basic but critical control to flag.
- Kiwi/Mimikatz-style credential dumping is one of the most common post-exploitation techniques attackers use to escalate from single-host access to lateral movement across a network.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
