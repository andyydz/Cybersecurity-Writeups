# Gobuster

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Category](https://img.shields.io/badge/Category-Web%20Security-blue)

This folder contains my notes and write-up on **Gobuster**, a fast directory, file, and DNS enumeration tool used to discover hidden content on web servers.

## Overview

Gobuster brute-forces URIs (directories and files), DNS subdomains, virtual host names, and S3 buckets using a wordlist — making it a core reconnaissance tool for mapping out a web application's attack surface before deeper testing begins.

## Writeup

📄 `gobuster-the-basic.md` — Covers the fundamentals of using Gobuster for directory and file enumeration, wordlist selection, and interpreting scan results to uncover hidden endpoints.

## SOC Analyst Relevance

Recognizing Gobuster's traffic signature — a burst of rapid, sequential HTTP requests to varying paths from a single source — is a common indicator used to detect reconnaissance activity against web-facing assets during log and traffic analysis.

---
More writeups: [github.com/andyydz/TryHackMe-Writeups](https://github.com/andyydz/TryHackMe-Writeups)
