![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Web%20Security-blue?style=for-the-badge)



> **Key Finding:** Every HTTP request and response contains headers, methods, and status codes that reveal how web applications behave — and where they can be exploited.

## Overview
This room covers the fundamentals of web applications — how they are structured, how browsers communicate with servers via HTTP, and how security headers protect against common attacks. Includes hands-on tasks making real GET, POST, and DELETE requests to an API.



---

## What I Actually Found

| Topic | Finding |
|---|---|
| Web app components | Frontend (HTML, CSS, JS) + Backend (database, infrastructure, WAF) |
| URL anatomy | Scheme, user, host/domain, port, path, query string, fragment |
| Typosquatting | Registering misspelled domain names to exploit user error for malicious activity |
| Query string | The part of a URL used to pass conditional information like search terms or form input |
| HTTP message structure | Start line, headers, empty line, body |
| HTTP methods | GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS, TRACE, CONNECT |
| HTTP versions | 0.9 → 1.0 → 1.1 → HTTP/3 (latest) |
| Status code categories | 1xx Informational, 2xx Success, 3xx Redirect, 4xx Client Error, 5xx Server Error |
| Common status codes | 100, 200, 301, 404, 500 |
| Security headers | CSP, HSTS, X-Content-Type-Options, Referrer-Policy |

---

## Hands-On Activities

### URL Anatomy Breakdown
Dissected a full URL into its components — scheme, user, host, port, path, query string, and fragment — and understood the role each part plays in locating web resources.

### HTTP Request Structure
Explored how an HTTP request is built:
- **Request line:** Method + URL path + HTTP version
- **Headers:** Host, User-Agent, Referer, Cookie, Content-Type
- **Body:** Form data, JSON (`application/json`), or XML (`application/xml`)

### HTTP Response Structure
Analysed HTTP responses including:
- **Status line:** Status code + reason phrase
- **Required headers:** Date, Content-Type, Server
- **Common headers:** Set-Cookie, Cache-Control, Location
- **Body:** The actual content returned by the server

### Security Headers
Reviewed critical security response headers:
- **Content-Security-Policy (CSP):** Restricts sources of executable scripts
- **Strict-Transport-Security (HSTS):** Forces HTTPS; includes `max-age`, `includeSubDomains`, `preload`
- **X-Content-Type-Options:** Set to `nosniff` to prevent MIME-type sniffing
- **Referrer-Policy:** Controls referrer info sent — options include `no-referrer`, `same-origin`, `strict-origin-when-cross-origin`

### Practical: Making HTTP Requests
Performed real API interactions:
- **GET** `/api/users` — retrieved user data and captured the flag
- **POST** `/api/users` — updated a user's country from UK to US
- **DELETE** `/api/users` — deleted the target user entry

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| HTTP method analysis | Identifying abnormal methods (e.g. TRACE, DELETE) in web logs |
| Status code interpretation | Detecting brute force (429), unauthorized access (401/403), or server errors (500) |
| URL structure analysis | Parsing malicious URLs in phishing and SIEM alerts |
| Security header review | Assessing web app hardening during security assessments |
| Request/response analysis | Core skill for web traffic investigation in SOC triage |
| WAF awareness | Understanding how WAFs filter malicious web requests |

---

## Key Takeaways

- Web applications have a frontend (HTML/CSS/JS) and backend (server, database, WAF)
- Every URL has a structured anatomy — each component serves a specific purpose
- Typosquatting exploits user error by registering lookalike domain names
- HTTP methods define the action — GET retrieves, POST creates, PUT updates, DELETE removes
- Status codes instantly communicate what happened — essential for log analysis
- Security headers like CSP and HSTS are a first line of defence for web applications
- Understanding HTTP request/response flow is foundational for any SOC or web security role

---

*Part of my [TryHackMe Writeups](https://github.com/andyydz/TryHackMe-Writeups) portfolio — documenting my SOC analyst journey.*
