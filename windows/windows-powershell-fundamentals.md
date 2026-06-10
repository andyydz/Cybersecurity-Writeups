# PowerShell

## Overview
PowerShell is a command-line shell and scripting language developed by Microsoft. It is used for system administration, automation, configuration management, and cybersecurity tasks in Windows environments.

---

# Basic PowerShell Commands

## Get-Help
Displays help information about commands.

```powershell
Get-Help
Get-Help Get-Process
```

---

## Get-Command
Lists available commands.

```powershell
Get-Command
```

---

## Get-Process
Displays running processes.

```powershell
Get-Process
```

---

## Get-Service
Shows system services.

```powershell
Get-Service
```

---

## Get-Location
Displays current directory.

```powershell
Get-Location
```

---

## Set-Location
Changes directory.

```powershell
Set-Location Desktop
```

---

# File Management

## New-Item
Creates new files or folders.

```powershell
New-Item file.txt
New-Item test -ItemType Directory
```

---

## Copy-Item
Copies files or directories.

```powershell
Copy-Item file.txt backup.txt
```

---

## Move-Item
Moves files.

```powershell
Move-Item file.txt Documents
```

---

## Remove-Item
Deletes files or directories.

```powershell
Remove-Item file.txt
```

---

# Networking Commands

## Test-Connection
Checks connectivity.

```powershell
Test-Connection google.com
```

---

## Get-NetIPAddress
Displays IP address information.

```powershell
Get-NetIPAddress
```

---

# User Management

## Get-LocalUser
Lists local users.

```powershell
Get-LocalUser
```

---

# What I Learned

- Basic PowerShell commands
- File and process management
- Networking commands
- User management
- Windows automation basics
```
```
# My Notes
I initially got confused between get-help and get-commands
---

# What I Found Intresting
-Powershell feels much faster for automation compared to CMD
---
---

