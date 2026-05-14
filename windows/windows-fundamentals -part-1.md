# Windows Fundamentals (TryHackMe)

## Overview

This write-up summarizes my learning from the *Windows Fundamentals* room on TryHackMe. It covers core Windows concepts, security features, and basic Active Directory knowledge.

---

## Key Concepts

### Windows OS Structure

* Common directories:

  * `C:\Windows`
  * `C:\Users`
  * `C:\Program Files`
* GUI-based operating system widely used in enterprises

---

### File System (NTFS)

* Supports permissions and access control
* Important for managing user and system access

---

### Windows Security

* Microsoft Defender for antivirus protection
* Firewall profiles:

  * Domain
  * Private
  * Public (used for untrusted networks)

---

### Windows Updates

* Keeps systems secure
* Includes:

  * Security updates
  * Feature updates
  * Definition updates

---

### BitLocker

* Disk encryption feature
* Uses TPM when available
* Without TPM, uses a startup key stored on a USB device

---

### Volume Shadow Copy Service (VSS)

* Creates snapshots of files
* Used for backup and recovery

---

### Active Directory Basics

* Centralized management of users and systems
* Key components:

  * Domain Controller
  * Organizational Units
  * Domain Admins

---

### Group Policy (GPO)

* Used to enforce system-wide configurations
* Stored in the SYSVOL share
* Applies to users and computers

---

### Authentication

* Kerberos (default authentication protocol)

  * Uses Ticket Granting Ticket (TGT)
* NetNTLM

  * Uses challenge-response
  * Does not transmit passwords

---

## Practical Learning

* Explored Windows Security settings
* Checked update history
* Identified firewall profiles
* Understood basic AD structure
* Learned how GPOs are applied

---

## What I Learned

* Windows security depends on proper configuration
* Active Directory is essential in enterprise environments
* GPOs help enforce security policies
* Authentication mechanisms are critical for secure access

---

## SOC Perspective

* Windows logs are important for monitoring and detection
* Misconfigured policies can introduce vulnerabilities
* Understanding authentication helps in detecting attacks

---

## Platform

TryHackMe — Windows Fundamentals
