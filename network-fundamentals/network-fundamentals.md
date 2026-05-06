# Network Fundamentals – TryHackMe

## Overview
This room introduced the fundamentals of computer networking and how devices communicate across networks and the internet. It covered core networking concepts such as IP addressing, MAC addresses, subnetting, network communication, and the basics of the TCP/IP model. The room also provided practical understanding of tools like `ping` and introduced concepts relevant to cybersecurity and SOC operations.

---

## Key Concepts

### What is Networking
Networking is the process of connecting devices so they can communicate and share data with each other.

### What is the Internet
The internet is a global network of interconnected systems that communicate using TCP/IP protocols.

### Identifying Devices on a Network
Devices are identified using:
- **IP Addresses** → Logical addresses used for communication
- **MAC Addresses** → Physical hardware addresses assigned to network interfaces

### IP Addresses
An IP address helps identify a device on a network and allows communication between systems.

Example:
```bash
192.168.1.10
```

### MAC Addresses
A MAC address is a unique hardware identifier assigned to a network device.

Example:
```bash
00:1A:2B:3C:4D:5E
```

### IPv4 Structure
IPv4 addresses contain 4 sections called octets separated by dots.

Example:
```bash
192.168.0.1
```

Each octet ranges from:
```bash
0 - 255
```

### Octets in IP Addressing
Each octet represents 8 bits of binary data.

Example:
```bash
11000000.10101000.00000000.00000001
```

### IP Addressing & Subnetting
Subnetting divides networks into smaller segments for better organization, performance, and security.

### Identifying IP and MAC Address Patterns
Recognizing address formats helps identify devices, vendors, and network ranges during investigations.

### MAC Spoofing
MAC spoofing changes a device’s MAC address to impersonate another device on a network.

### Ping (ICMP)
`ping` uses ICMP packets to test connectivity between devices.

### Basic Network Communication
Devices communicate through protocols that define how data is transmitted and received.

### Intro to TCP/IP Networking
TCP/IP is the foundational networking model used for internet communication.

---

## Commands Practiced

### Ping Command
Checks connectivity between systems.

```bash
ping 8.8.8.8
```

### View IP Configuration (Windows)
Displays network configuration details.

```bash
ipconfig
```

### View IP Configuration (Linux)
Shows IP and network interface information.

```bash
ip addr
```

### View MAC Address (Windows)

```bash
getmac
```

### View MAC Address (Linux)

```bash
ip link
```

---

## Practical Examples

### Checking Internet Connectivity

```bash
ping google.com
```

Used to verify whether a system can communicate with external networks.

### Identifying Devices in a Network
Using IP addresses and MAC addresses to identify systems connected to a local network.

### Detecting Suspicious Activity
Unusual MAC address changes may indicate MAC spoofing attempts.

### Understanding Subnetting
Splitting networks into smaller groups to improve security and network management.

---

## What I Learned

- The difference between IP addresses and MAC addresses
- How devices communicate across networks
- The structure of IPv4 addresses and octets
- Basic subnetting concepts
- How ICMP and ping work
- Introduction to TCP/IP networking
- How MAC spoofing can be used in attacks
- The importance of identifying network devices correctly

---

## SOC / Real-World Perspective

These networking concepts are essential in cybersecurity and SOC environments.

### SOC Analysts
- Monitor suspicious IP activity
- Investigate unauthorized devices on networks
- Analyze ICMP traffic and network communication logs

### Blue Team Operations
- Detect MAC spoofing attempts
- Identify unusual network behavior
- Monitor internal network traffic for threats

### System Administrators
- Configure IP addressing and subnetting
- Troubleshoot connectivity issues
- Manage network communication between systems

### Cybersecurity Professionals
- Perform network reconnaissance
- Analyze packets and protocols
- Investigate attacks using IP and MAC address information

Understanding networking fundamentals is critical for incident response, threat hunting, penetration testing, and defensive security operations.

---

## Skills Gained

- Basic networking knowledge
- Understanding of TCP/IP communication
- IP and MAC address identification
- Introductory subnetting concepts
- Network troubleshooting basics
- ICMP and ping usage
- Recognizing network communication patterns
- Foundational cybersecurity networking skills

---

## Platform
TryHackMe — Network Fundamentals
