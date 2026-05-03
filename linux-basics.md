# Linux Fundamentals – TryHackMe

## Overview

This write-up summarizes my learning from the *Linux Fundamentals* room on TryHackMe. It covers basic Linux commands, file system structure, and essential concepts used in cybersecurity.

---

## Key Concepts

### Linux Operating System

* Command-line based operating system
* Widely used in servers and cybersecurity environments

---

### File System Structure

* `/` → Root directory
* `/home` → User directories
* `/etc` → Configuration files
* `/var` → Logs and variable data

---

### File and Directory Commands

* `ls` → List files
* `cd` → Change directory
* `pwd` → Show current directory
* `mkdir` → Create directory
* `rm` → Remove files/directories

---

### File Viewing and Editing

* `cat` → View file content
* `less` → View large files
* `nano` → Edit files

---

### Permissions

* `chmod` → Change permissions
* `chown` → Change ownership
* Permissions:

  * Read (r)
  * Write (w)
  * Execute (x)

---

### User Management

* `whoami` → Current user
* `sudo` → Execute commands as superuser

---

## Practical Commands

```bash
ls -la
cd /home
pwd
cat file.txt
chmod +x script.sh
sudo apt update
```

---

## What I Learned

* Linux is widely used in cybersecurity and servers
* Command-line usage is essential for efficiency
* File permissions are important for security
* Understanding file structure helps in navigation and analysis

---

## SOC Perspective

* Linux logs are critical for detecting suspicious activity
* Commands help in investigating compromised systems
* Permissions misconfiguration can lead to security issues
* Analysts often use Linux to analyze logs and incidents

---

## Platform

TryHackMe — Linux Fundamentals
