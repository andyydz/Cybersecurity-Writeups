# Attacks and Defenses

This folder contains my notes and write-ups from attack and defense-related rooms and modules completed on TryHackMe, aimed at building a strong understanding of cybersecurity fundamentals, threat detection, offensive techniques, and the defensive mindset needed to counter them.

---

## Contents

###  cryptography/
Core cryptographic concepts — symmetric vs. asymmetric encryption, RSA, Diffie-Hellman key exchange, digital signatures, certificates, hashing, and PGP/GPG.
- `basics-and-public-key.md`
- `cryptographic-concepts.md`
- `hashing-basic.md`

###  eternal-blue/
Full offensive lifecycle walkthrough of the classic EternalBlue (MS17-010) SMB exploitation chain — recon, exploitation, credential harvesting, privilege escalation, and hash cracking with John the Ripper.
- `blue.md`

###  exploitation-basics/
Foundational exploitation concepts — a real-world CVE walkthrough and the core shell types used in post-exploitation.
- `moniker-link (CVE-2024-21413).md`
- `shells-overview.md`

###  metasploit/
Metasploit Framework series covering the fundamentals of the tool through to active exploitation and post-exploitation with Meterpreter.
- `metasploit-introduction.md`
- `metasploit-exploitation.md`
- `metasploit-meterpreter.md`

###  password-attacks/hydra/
Password attack techniques using Hydra for brute-forcing and credential attacks against various services.

###  became-a-hacker.md
Notes on offensive security mindset and the attacker's perspective — how threat actors think and operate.

###  become-a-defender.md
Notes on the defensive counterpart — blue team mindset and how defenders detect and respond to the techniques covered on the offensive side.

###  cia-triad.md
Core security principles — Confidentiality, Integrity, and Availability — and how they underpin every attack and defense concept in this repository.

---

## Why This Structure

Each subfolder groups write-ups by technique or tool so related concepts stay together — cryptography concepts in one place, exploitation techniques in another, and so on — while root-level files cover foundational, cross-cutting concepts (mindset, CIA triad) that apply across every room in this folder.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
