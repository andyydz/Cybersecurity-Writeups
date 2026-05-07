# Packets and Frames – TryHackMe

## Overview
In this room, I learned how data is transferred across networks using packets and frames. The room explained how communication works between devices using TCP/IP and UDP/IP protocols. I also completed practical exercises related to the TCP three-way handshake and Port 101, which helped me understand how ports and communication protocols work in real-world networking.

---

## Key Concepts

### Packets and Frames
Learned the difference between packets and frames in networking.

- Packet → A unit of data used at the Network Layer
- Frame → A unit of data used at the Data Link Layer

Frames are responsible for local delivery, while packets help data travel between networks.

### TCP/IP Three-Way Handshake
Learned how TCP establishes a reliable connection between devices using the three-way handshake process:

1. SYN  
2. SYN-ACK  
3. ACK  

This process ensures both devices are ready before communication starts.

### Practical TCP Handshake Exercise
Completed a practical activity that demonstrated how the TCP handshake works between systems during communication.

### UDP/IP
Learned how UDP communication works without establishing a connection first. UDP is faster than TCP but does not guarantee packet delivery.

### Ports
Learned that ports are used to identify specific services and applications running on a device.

Some common examples:
- Port 80 → HTTP
- Port 443 → HTTPS
- Port 22 → SSH
- Port 53 → DNS

### Port 101 Practical
Completed a Port 101 practical exercise to understand how ports are used in network communication and how services listen on specific ports.

---

## Practical Commands

### Test Connectivity
```bash
ping <IP_ADDRESS>
```

Used to check whether another device is reachable.

### Trace Packet Path
```bash
tracert <IP_ADDRESS>
```

Used to view the route packets take through a network.

### View Active Connections
```bash
netstat
```

Displays active network connections and listening ports.

---

## Practical Examples

- Understanding how packets move between devices
- Learning the difference between frames and packets
- Observing the TCP three-way handshake process
- Understanding how UDP communication works
- Identifying common ports and their services
- Practicing port-related networking tasks through Port 101

---

## What I Learned

- Difference between packets and frames
- How TCP creates reliable connections
- Basics of the TCP three-way handshake
- How UDP communication works
- Importance of ports in networking
- Common networking ports and services
- Better practical understanding through hands-on exercises

---

## SOC Analyst Perspective

This room is very useful for a SOC Analyst because network traffic analysis is heavily based on packets, protocols, and ports. Understanding TCP handshakes, UDP communication, and port behavior helps in detecting suspicious traffic, identifying malicious connections, and investigating network-based attacks.

Ports are something SOC Analysts deal with regularly, so understanding how services communicate through ports is an important foundational skill in cybersecurity.

---

## Conclusion

This room helped me better understand how devices communicate over networks using packets, frames, and protocols like TCP and UDP. The practical exercises made the concepts much easier to understand and gave me more confidence with networking fundamentals that are important for cybersecurity and SOC Analyst roles.

---

## LinkedIn Post

Completed the “Packets and Frames” room on TryHackMe.

In this room, I learned how devices communicate across networks using packets and frames, along with the basics of TCP/IP and UDP/IP communication.

I also completed practical exercises on the TCP three-way handshake and Port 101, which helped me better understand how ports and protocols work in real-world networking.

This room improved my understanding of network communication and concepts that are important for cybersecurity and SOC Analyst roles.

#TryHackMe #CyberSecurity #Networking #PacketsAndFrames #SOCAnalyst #LearningInPublic

---

## File Name Suggestion

packets-and-frames-tryhackme-writeup.md
