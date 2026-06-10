# Networking Concepts

## Overview

This write-up covers the fundamental concepts of computer networking, including networking models, protocols, addressing, and communication methods used across modern networks.

Networking forms the foundation of cybersecurity because every device, service, and application communicates through networks.

---

# Topics Covered

## 1. OSI Model

Understanding the seven-layer networking model used to standardize communication between devices.

### Key Concepts

- Physical Layer
- Data Link Layer
- Network Layer
- Transport Layer
- Session Layer
- Presentation Layer
- Application Layer

### Example

- A web browser communicating with a web server through multiple network layers.

### Use Cases

- Troubleshooting
- Network analysis
- Security investigations

---

## 2. TCP/IP Model

Learning the practical networking model used by the Internet.

### Key Concepts

- Application Layer
- Transport Layer
- Internet Layer
- Network Access Layer

### Example

- Sending a request to a website using HTTP over TCP/IP.

### Use Cases

- Internet communication
- Network design
- Protocol analysis

---

## 3. IP Addresses and Subnetting

Understanding how devices are identified on networks.

### Key Concepts

- IPv4
- Network addressing
- Host addressing
- Subnet masks

### Example

```text
192.168.1.10
```

### Use Cases

- Device identification
- Network management
- Routing

---

## 4. TCP and UDP

Exploring the two major transport protocols.

### TCP

- Reliable
- Connection-oriented
- Error checking

### UDP

- Fast
- Connectionless
- Low overhead

### Use Cases

- TCP → Web browsing, Email
- UDP → Streaming, Gaming, VoIP

---

## 5. Encapsulation

Understanding how data is packaged as it moves through networking layers.

### Key Concepts

- Headers
- Packets
- Frames
- Layered communication

### Example

Application Data → TCP Segment → IP Packet → Ethernet Frame

### Use Cases

- Packet analysis
- Network troubleshooting

---

## 6. Telnet

Introduction to remote communication protocols.

### Key Concepts

- Remote access
- Client-server communication
- Command execution

### Example

```bash
telnet 192.168.1.10
```

### Use Cases

- Legacy administration
- Network testing

---

# Skills Learned

- Networking fundamentals
- OSI model understanding
- TCP/IP communication
- IP addressing
- Subnetting basics
- Protocol analysis

---

# Cybersecurity Relevance

These concepts are essential for:

- SOC Analysis
- Threat Hunting
- Incident Response
- Network Security
- Penetration Testing

---

# Platform

**TryHackMe**

# Room

**Networking Concepts**

# Status

✅ Completed
