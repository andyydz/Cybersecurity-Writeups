![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Web%20Application%20Basics-blue)



>  **Key Finding:** GoBuster is a single tool with three distinct enumeration modes — `dir` for directories/files, `dns` for subdomains, and `vhost` for virtual hosts — each critical for uncovering attack surface that isn't visible through normal browsing.

## Overview

Room: **GoBuster: The Basics**

This room covers the fundamentals of enumeration using GoBuster — a fast, Go-based brute-forcing tool used to discover hidden directories/files, subdomains, and virtual hosts on a target web application.

## What I Actually Found

| Area | Details |
|------|---------|
| Tool | GoBuster — Go-based directory/DNS/VHost brute-forcer |
| Core Modes | `dir` (directory & file enumeration), `dns` (subdomain enumeration), `vhost` (virtual host enumeration) |
| Key Flags | Extensions, cookies, headers, status code filters/blacklist, TLS validation skip, follow-redirect, username/password (basic auth) |
| Wordlists | Used pre-supplied wordlists for brute-forcing paths, subdomains, and vhosts |
| Objective | Locate hidden flags in each mode (dir, DNS, vhost) not visible through normal browsing |

## Hands-On Activities

**1. Introduction & Learning Objectives**
Reviewed the room's goals — understanding enumeration fundamentals and learning how GoBuster is used across web, dictionary/directory, subdomain, and virtual host enumeration.

**2. Environment & Setup**
Set up the lab environment and confirmed GoBuster was available, along with the wordlists needed for each enumeration mode.

**3. GoBuster Overview**
Covered GoBuster's general syntax and use cases, understanding it as a modular tool where the mode (`dir`, `dns`, `vhost`) determines what kind of brute-force enumeration is performed.

**4. Directory & File Enumeration (`dir` mode)**
Practiced `dir` mode to brute-force hidden directories and files on the target, using various options:
- **Extensions** — appending file extensions (e.g. `.php`, `.txt`) to wordlist entries
- **Cookies** — passing session cookies for authenticated enumeration
- **Headers** — adding custom HTTP headers to requests
- **No TLS validation** — skipping certificate checks on HTTPS targets
- **Status codes / status code blacklist** — filtering results by HTTP response code, or excluding noisy ones (e.g. 404s)
- **Username/password** — supplying basic auth credentials for protected paths
- **Follow redirect** — following HTTP redirects instead of just reporting them
Used `dir` mode to uncover a hidden path and retrieve the first flag.

**5. Subdomain Enumeration (`dns` mode)**
Switched to `dns` mode to brute-force valid subdomains against the target domain using a wordlist, uncovering subdomains not listed anywhere publicly and retrieving a flag from a discovered subdomain.

**6. Virtual Host Enumeration (`vhost` mode)**
Covered the use case for `vhost` enumeration — discovering virtual hosts that respond differently on the same IP based on the `Host` header, which regular DNS/subdomain enumeration can miss. Ran `vhost` mode with a wordlist to identify a valid virtual host and located the final flag.

**7. Conclusion**
Wrapped up by tying all three modes together as complementary enumeration techniques — directory/file discovery, subdomain discovery, and vhost discovery — each revealing different hidden attack surface on a target.

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| `dir` mode brute-forcing | Recognizing directory brute-force noise (high volume of 404s/403s) in web server logs |
| `dns` mode subdomain enumeration | Detecting subdomain enumeration attempts during recon-stage monitoring |
| `vhost` enumeration | Understanding how attackers find hidden internal apps hosted behind a shared IP |
| Status code filtering | Knowing which response codes matter when triaging suspicious web request patterns |
| Header/cookie manipulation during enumeration | Spotting authenticated brute-force attempts vs. anonymous scanning in logs |

## Key Takeaways

- Enumeration is almost always the first visible sign of an attack in web server logs — high-volume, sequential requests to nonexistent paths are a strong indicator worth alerting on.
- Knowing GoBuster's three modes (`dir`, `dns`, `vhost`) makes it easier to distinguish between different recon techniques when reviewing traffic — each leaves a slightly different pattern.
- Status code filtering/blacklisting is a good reminder that attackers tune their tools to reduce noise — meaning naive "count all requests" detection isn't enough; behavioral patterns matter more.
- Virtual host enumeration is an easy blind spot — a SOC should account for the possibility of hidden apps sharing an IP, not just publicly known domains.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
