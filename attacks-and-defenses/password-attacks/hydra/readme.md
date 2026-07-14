#  Hydra - Password Brute Forcing

This folder contains my writeup and screenshots from the **Hydra** room on TryHackMe — part of my attacks and defenses learning path.

---

##  Folder Structure

```
hydra/
├── screenshots/
│   ├── 01-hydra-login-page.png
│   ├── 02-web-login-success.png
│   ├── 03-http-post-form-command.png
│   ├── 04-http-password-found.png
│   └── 05-ssh-password-found.png
└── hydra.md
```

---

##  What This Room Covers

- What Hydra is and how it works
- Brute forcing a web login form via HTTP POST method
- Brute forcing SSH using a wordlist
- Understanding Hydra flags and command structure
- Retrieving flags after successful credential cracking

---

##  Tools Used

- Hydra
- rockyou.txt wordlist
- TryHackMe AttackBox
- Firefox (web login verification)
- SSH client

---

##  Commands Used

**HTTP POST Form:**
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.x.x http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
```

**SSH Brute Force:**
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.x.x -t 4 ssh
```

---

##  Key Takeaways

- Hydra automates credential attacks against live services
- Weak passwords near the top of rockyou.txt fall within seconds
- HTTP POST attacks require the login path, field names, and failure string
- SSH brute force uses `-t 4` threads to avoid connection drops
- As a SOC analyst, repeated failed logins followed by success is a critical alert pattern
- Any internet-exposed service without rate limiting is vulnerable to this attack

---

