![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Exploitation%20Basics-blue)



>  **Key Finding:** Metasploit Framework organizes every stage of an attack — recon, exploitation, and post-exploitation — into modular components (auxiliary, exploits, payloads, encoders, post) that can be searched, configured, and fired off entirely through `msfconsole`.

## Overview

Room: **Metasploit: Introduction**

This room covers the fundamentals of the Metasploit Framework — its architecture, core module types, and the basic `msfconsole` workflow used to search, configure, and run modules against a target.

## What I Actually Found

| Area | Details |
|------|---------|
| Metasploit Editions | Metasploit Pro (commercial, GUI-driven) vs. Metasploit Framework (free, CLI-driven) |
| Core Interface | `msfconsole` — the main CLI for interacting with the framework |
| Main Module Types | Auxiliary, Encoders, Evasion, Exploits, NOPs, Payloads, Post |
| Config Workflow | `search` → `use` → `show options` → `set` → `run`/`exploit` |
| Session Handling | Background sessions with `bg`, list with `sessions`, interact via `sessions -i <id>` |

## Hands-On Activities

**1. Metasploit Architecture**
Studied the difference between Metasploit Pro and Metasploit Framework, then broke down the Framework's main components:
- **Auxiliary** – scanning, fuzzing, DoS modules (no payload delivery)
- **Encoders** – obfuscate payloads to help evade detection
- **Evasion** – modules built specifically to bypass AV/EDR
- **Exploits** – code that takes advantage of a specific vulnerability
- **NOPs** – padding used to keep payload size/alignment consistent
- **Payloads** – the actual code executed on the target after exploitation
- **Post** – post-exploitation modules (privilege escalation, data gathering, pivoting)

**2. msfconsole Basics**
Launched `msfconsole` and practiced the core commands:
- `show <module_type>` — list available modules of a given type
- `use <module_path>` — load a specific module
- `search <keyword>` — e.g. `search apache` to find Apache-related modules
- `show options` — view required/optional parameters for the loaded module

**3. Working With a Module**
Practiced the standard configuration flow on a loaded module:
- `set <PARAMETER> <value>` — e.g. `set RHOSTS <target_ip>`
- `set PAYLOAD <payload_path>` — e.g. selecting an `MSF6`-compatible payload
- `set LHOST <attacker_ip>` / `set LPORT <port>` — configuring the reverse handler
- `setg` / `unsetg` — set or unset a parameter globally across modules, instead of per-module

**4. Running the Exploit**
Executed the configured module using `exploit` (or `run`), which launched the attack against the target using the set payload and options.

**5. Session Management**
Once a session opened, practiced:
- `background` (or `Ctrl+Z`) to send the session to the background
- `sessions` — list active sessions
- `sessions -i <session_id>` — interact with a specific session
- Reviewed a summary of session state and available post-exploitation options at the end

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Module architecture (auxiliary/exploit/payload/post) | Recognizing attacker toolsets and TTPs during investigations |
| `msfconsole` workflow | Understanding how logged exploitation attempts are structured, for better log/alert triage |
| Session & payload configuration (RHOSTS/LHOST/LPORT) | Spotting C2/reverse-shell indicators in network traffic |
| Global vs. per-module settings (`setg`/`unsetg`) | Understanding attacker efficiency/automation patterns during multi-target campaigns |
| Post-exploitation awareness | Knowing what to look for once initial access is suspected (lateral movement, persistence) |

## Key Takeaways

- Metasploit Framework's modular design (auxiliary, exploits, payloads, encoders, post) mirrors the real attack lifecycle — recon, exploit, execute, persist.
- Knowing the exact commands and parameters attackers use (`RHOSTS`, `LHOST`, `LPORT`, payload names) makes it much easier to recognize exploitation attempts in logs and traffic.
- Session management commands show how attackers maintain and pivot through footholds, which is directly useful when investigating suspected compromises.
- This room is foundational — future Metasploit rooms (Exploitation, Meterpreter) build directly on this command structure.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
