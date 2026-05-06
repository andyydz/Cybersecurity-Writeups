# Windows File System

## Overview
The Windows file system organizes and stores files, folders, applications, and system data. Understanding the file system is important for system administration, digital forensics, and cybersecurity.

---

# Important Directories

## C:\Windows
Contains Windows operating system files.

---

## C:\Users
Stores user profiles and personal files.

---

## C:\Program Files
Contains installed applications.

---

## C:\ProgramData
Stores application data shared between users.

---

# NTFS File System

NTFS (New Technology File System) is the default Windows file system.

## Features
- File permissions
- Encryption
- Compression
- Journaling

---

# Hidden Files

View hidden files using File Explorer settings or CMD.

```cmd
dir /a
```

---

# File Permissions

Windows uses ACLs (Access Control Lists) for permissions.

## Permission Types
- Read
- Write
- Modify
- Full Control

---

# Environment Variables

Important system variables:

```cmd
echo %PATH%
echo %TEMP%
```

---

# What I Learned

- Windows directory structure
- NTFS basics
- File permissions
- Hidden files
- Environment variables
