![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Category](https://img.shields.io/badge/Category-Web%20Application%20Basics-blue)



> **Key Finding:** Burp Suite's Proxy sits as a man-in-the-middle between browser and server, letting every HTTP/HTTPS request be intercepted, modified, and replayed — and getting HTTPS traffic visible at all depends entirely on trusting Burp's own CA certificate in the browser first.

## Overview

Room: **Burp Suite: The Basics**

This room covers Burp Suite fundamentals — editions, dashboard navigation, proxy configuration through FoxyProxy, HTTPS interception via CA certificate trust, and using the Proxy/Target tools to find an unusual endpoint containing a flag.

## What I Actually Found

| Area | Details |
|------|---------|
| Burp Editions | Community (free, limited), Professional, and Enterprise editions |
| Community Edition Features | Proxy and Intruder (rate-limited compared to Pro) |
| Core Tabs | Dashboard, Target, Proxy, Intruder — plus session tabs that can be detached |
| Proxy Setup | FoxyProxy used to route browser traffic through Burp's listening port |
| HTTPS Interception | Requires importing Burp's CA certificate into the browser's trusted authorities |
| Flag Location | Found via Site Map / issue detection by spotting an unusual endpoint |

## Hands-On Activities

**1. Introduction to Burp Suite**
Reviewed what Burp Suite is and the difference between its **Professional** and **Enterprise** editions, along with the free **Community Edition** used in the room — noting Community's limited feature set (Proxy and Intruder only, with throttling).

**2. Installation & Dashboard Walkthrough**
Installed Burp Suite and explored the **Dashboard**, covering:
- **Task** scheduling/status
- **Event log** for recorded actions
- **Issue activity** and **advisory** panels for findings

**3. Interface Navigation**
Practiced working across multiple sessions/tabs, including detaching tabs into separate windows, and reviewed keyboard shortcuts for faster navigation. Explored general **Options**, **global search**, **Projects**, and **Settings**, along with search type/filter categories for narrowing results.

**4. Introduction to Burp Proxy**
Covered the core concept behind Burp's Proxy tool — sitting between the browser and the target server to intercept and inspect traffic. Learned key proxy concepts: intercepting requests, taking control of a request before it's forwarded, capturing/logging traffic, and WebSocket support for non-HTTP traffic. Reviewed notable proxy settings including response interception and **Match and Replace** rules for automatic request/response modification.

**5. Connecting Through the Proxy (FoxyProxy)**
Installed the FoxyProxy browser extension, accessed its options, and created a new proxy configuration:
- Set a **title** and **proxy ID**
- Entered the **proxy details** (host/port matching Burp's listener)
- Activated the proxy configuration and enabled **Intercept** in Burp Suite
- Tested the proxy by browsing to confirm traffic was being captured

**6. Site Map & Issue Detection**
Used Burp's **Site Map** and issue/vulnerability detection features to browse the target application and locate an **unusual endpoint**, which contained the room's flag.

**7. Scope & Targeting**
Defined a **scope** in the Target tab to restrict Burp's proxy/site map to only the relevant target application, reducing noise from unrelated traffic.

**8. Proxying HTTPS Traffic**
Since HTTPS traffic can't be inspected without trust established first:
- Downloaded Burp's **CA certificate**
- Imported it into the browser's trusted authority/certificate store
- Configured the certificate as trusted for all traffic, enabling full HTTPS interception

**9. Practical Exercise**
Completed a hands-on walkthrough applying everything above — configuring the proxy, trusting the CA cert, intercepting traffic, and locating the flag through the Site Map.

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Proxy interception concepts | Understanding how MITM tooling works — relevant when investigating proxy-based attacks or malicious browser extensions |
| CA certificate trust process | Recognizing rogue/unauthorized CA certificate installs as a red flag during endpoint investigations |
| Site Map / endpoint discovery | Understanding how attackers map application attack surface before exploitation |
| Match and Replace rules | Spotting request/response tampering techniques used in web app attacks |
| Scope management | Applying the same "define scope first" discipline when scoping an investigation or pentest engagement |

## Key Takeaways

- Burp Suite's proxy is fundamentally a MITM tool — understanding it from the attacker/tester side makes it much easier to recognize similar MITM patterns in real incidents (rogue proxies, malicious certs).
- HTTPS interception only works because the browser is made to trust Burp's CA certificate — a good reminder of why unexpected certificate authority installs on an endpoint should always be investigated.
- Defining scope early keeps both testing and investigation focused — noise reduction matters as much in a pentest as it does in log analysis.
- Community Edition's limitations (rate-limited Intruder, no scanner) are worth knowing when interpreting what tooling an attacker with only the free edition could realistically achieve.

---
 More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
