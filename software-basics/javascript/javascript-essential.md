![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Web%20Security-blue?style=for-the-badge)



> **Key Finding:** JavaScript runs client-side and can be manipulated directly in the browser — hardcoded secrets, client-side validation, and obfuscated code are all attackable if you know where to look.

## Overview
This room covers JavaScript fundamentals from a security perspective — how JS integrates with HTML, how dialogue functions and control flow can be abused, and how obfuscated/minified code can be deobfuscated to reveal hidden logic. Includes hands-on tasks on a lab machine using browser DevTools and a code editor.



---

## What I Actually Found

| Topic | Finding |
|---|---|
| JavaScript nature | Interpreted language; runs directly in the browser |
| Integration methods | Internal (inline in HTML) vs External (separate `.js` file) |
| External JS advantage | External files are better for reusing JavaScript across multiple web pages |
| Internal JS | Places code directly within the HTML document |
| External JS filename | Began with `external` (e.g. `external.js`) |
| Dialogue functions | `alert()`, `prompt()`, `confirm()` — all abusable by attackers |
| Obfuscation | Minified/obfuscated JS can be deobfuscated via browser DevTools → Sources tab |
| Login bypass | Control flow statements can be manipulated to bypass login forms |
| Hardcoded secrets | Secrets embedded in JS are exposed to anyone who inspects the page |
| Client-side validation | Easily bypassed — never rely on it alone |

---

## Hands-On Activities

### Connecting to the Lab Machine
Connected to the provided lab machine and used Pluma as the code editor to write and test JavaScript integrated into HTML files.

### Internal vs External JavaScript
Verified both integration methods:
- **Internal:** JS written directly inside `<script>` tags within the HTML document
- **External:** JS loaded via `<script src="external.js">` — preferred for reusability across pages

### Abusing Dialogue Functions
Explored how `alert()`, `prompt()`, and `confirm()` can be exploited — attackers can trigger fake prompts or use them to extract user input through social engineering or XSS.

### Bypassing Control Flow & Login Forms
Manipulated control flow statements (if/else conditions) in the browser console to bypass login form logic — demonstrating how client-side-only validation is a critical security weakness.

### Exploring Minified & Obfuscated Files
Used browser DevTools (Inspect → Sources tab) to locate minified JavaScript files. Applied deobfuscation techniques to reverse the obfuscation and read the underlying logic, similar to how analysts triage malicious scripts.

### Obfuscation in Action
Opened Google in the browser, inspected the source, navigated to Sources, copied obfuscated JS, and used a deobfuscator to decode it — reinforcing how obfuscation hides but does not protect code.

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| Browser DevTools usage | Analysing client-side code during web threat investigations |
| JS deobfuscation | Reverse engineering malicious scripts found in phishing pages or drive-by downloads |
| Login bypass techniques | Understanding attacker methods for web application exploitation |
| Hardcoded secret detection | Identifying exposed credentials or API keys in web app source code |
| Client-side validation awareness | Recognising security misconfigurations during assessments |
| Obfuscation recognition | Spotting suspicious minified code in malware or malicious web pages |

---

## Key Takeaways

- JavaScript is interpreted and runs client-side — making it directly accessible to anyone with a browser
- External JS files are preferred for reusability; internal JS embeds code directly in HTML
- Dialogue functions (`alert`, `prompt`, `confirm`) can be abused for phishing and social engineering
- Control flow statements can be bypassed in the browser console to circumvent login logic
- Never rely solely on client-side validation — all input must be validated server-side
- Hardcoded secrets in JavaScript are fully visible to anyone who inspects the page
- Obfuscation makes code harder to read but does not make it secure — deobfuscation tools easily reverse it
- Avoid loading untrusted third-party libraries — they can introduce malicious code into your app

---

*Part of my [TryHackMe Writeups](https://github.com/andyydz/TryHackMe-Writeups) portfolio — documenting my SOC analyst journey.*
