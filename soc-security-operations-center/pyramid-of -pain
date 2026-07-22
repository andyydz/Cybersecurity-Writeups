# TryHackMe — Pyramid of Pain

**Room:** Pyramid of Pain
**Category:** SOC / Threat Intelligence
**Difficulty:** Easy

---

## Introduction

The Pyramid of Pain, created by David Bianco, is a model used to describe the relationship between the types of indicators an analyst can use to detect an adversary's activity and how much "pain" it causes that adversary when you deny or block that indicator. The higher up the pyramid an indicator sits, the harder it is for an attacker to change it — and the more disruption it causes them when you act on it.

This room walks through each layer of the pyramid, from the easiest indicators to change (bottom) to the hardest (top).

---

## The Pyramid of Pain — Layers

### 1. Hash Values

The base of the pyramid. A hash (MD5, SHA1, SHA256) uniquely identifies a specific file, such as a malware sample. Blocking a hash is trivial for an attacker to bypass — a single byte change in the file produces a completely different hash. Low pain, low effort to block, low effort for the attacker to evade.

### 2. IP Address

An adversary's infrastructure often includes IP addresses used for C2 (command and control) or hosting malicious payloads. Blocking an IP is slightly more disruptive than a hash, but attackers can rotate IPs easily — especially with cloud hosting, proxies, or Tor. Still relatively low pain.

### 3. Domain Names

Slightly more painful than IPs because domains take more effort to register and change (registration, DNS propagation), though tools like Dynamic DNS make this easier for attackers than it used to be. Blocking a domain forces the adversary to acquire a new one and update any hardcoded references to it.

### 4. Host Artifacts

Traces left behind on a victim machine — registry keys, files dropped in specific paths, unusual scheduled tasks, or mutexes created by malware. These require the attacker to change their tooling or behavior, not just infrastructure, so blocking/detecting on host artifacts causes more pain than the layers below.

### 5. Network Artifacts

Observable patterns in network traffic — a distinctive User-Agent string, a specific URI pattern in an HTTP request, patterns in DNS requests, or C2 beacon intervals. Examples covered in this layer:

- **Viewing connections** – identifying unusual outbound connections from a host.
- **HTTP request patterns** – recognizing a consistent URI structure or header used by malware C2.
- **DNS requests** – malware often uses DNS for C2 or exfiltration; recognizing beaconing patterns or unusual query structures is key.
  - **What is DNS?** The Domain Name System translates human-readable domain names into IP addresses. Because DNS traffic is usually allowed outbound by default, it's a common channel for malicious C2 and data exfiltration — which is exactly why network artifacts at this layer matter so much to defenders.

Detecting on network artifacts (e.g., via **Snort** rules matching a specific packet pattern) forces attackers to change how their tools communicate, not just where they're hosted.

### 6. Tools

At this layer, defenders target the actual software the attacker uses — a specific RAT, keylogger, or exploitation framework. Denying a tool (through detection signatures, hash/behavioral rules, or blocking its infrastructure entirely) forces the attacker to find, build, or learn a new tool. This is a significant time and resource cost, causing real pain.

### 7. TTPs (Tactics, Techniques, and Procedures)

The apex of the pyramid — and the most painful for an attacker to have disrupted. TTPs describe *how* an adversary operates: their methodology for gaining access, escalating privileges, moving laterally, and exfiltrating data. Detecting and responding to TTPs (rather than any single tool or IP) means you're defending against the attacker's actual behavior. To evade this, an attacker would have to fundamentally change how they operate — retraining, rebuilding workflows, and rethinking their entire approach. This is why frameworks like MITRE ATT&CK, which catalog TTPs, are so central to mature threat detection.

---

## Practical Application

Working through the room's practical exercises reinforces the pyramid by requiring identification of indicators at each layer — recognizing a hash, an IP, a domain, then moving up to spotting host and network artifacts, naming the tool involved, and finally describing the TTP being used. The exercise makes clear why SOC teams should always aim to detect as high up the pyramid as possible: it's more work up front, but it denies the adversary far more than blocking a hash or IP ever will.

---

## Conclusion

The Pyramid of Pain reframes threat detection around a simple question: *how much does this indicator cost the attacker to change?* Hashes and IPs are cheap and disposable for adversaries — blocking them barely slows a determined attacker down. Detecting TTPs, on the other hand, targets the attacker's actual tradecraft, forcing them to rebuild their approach from the ground up. For a SOC analyst, this model is a practical guide for prioritizing detection engineering: build detections that climb the pyramid whenever possible.

---

*Room: TryHackMe — Pyramid of Pain*
