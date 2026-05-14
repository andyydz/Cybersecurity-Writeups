# Intro to LAN – TryHackMe

## Overview
This room introduced the fundamentals of Local Area Networks (LANs) and how devices communicate within a network. It covered important networking concepts such as LAN topology, subnetting, ARP, DHCP, and basic network communication used in real-world environments.

---

## Key Concepts

### LAN Topology
Learned different network topologies and how devices are connected within a LAN environment.

### Primer on Subnetting
Understood how subnetting divides networks into smaller segments for better organization and communication.

### ARP (Address Resolution Protocol)
Learned how ARP maps IP addresses to MAC addresses within a local network.

### DHCP (Dynamic Host Configuration Protocol)
Understood how DHCP automatically assigns IP addresses to devices connected to the network.

### IP Address
An IP address uniquely identifies a device on a network and enables communication.

### MAC Address
A MAC address is a physical hardware address assigned to a network interface.

### Packet and Frame
- Packet → Data unit used at the Network Layer
- Frame → Data unit used at the Data Link Layer

### TCP vs UDP
- TCP provides reliable communication with error checking.
- UDP is faster but does not guarantee delivery.

---

## Practical Commands

### Check IP Configuration
```bash
ipconfig
```

Displays the IP configuration of the system.

### Test Connectivity
```bash
ping <IP_ADDRESS>
```

Checks whether another device is reachable on the network.

### View MAC Address
```bash
getmac
```

Displays MAC addresses of network interfaces.

### Trace Route
```bash
tracert <IP_ADDRESS>
```

Shows the path packets take to reach the destination.

---

## Practical Examples

- Understanding communication between devices in a LAN
- Identifying IP and MAC addresses
- Learning how DHCP assigns IP addresses
- Understanding ARP requests and responses
- Troubleshooting connectivity issues using networking commands

---

## What I Learned

- Basics of LAN networking
- Different LAN topologies
- Fundamentals of subnetting
- Role of ARP and DHCP in networking
- Difference between IP and MAC addresses
- Difference between TCP and UDP
- Basic networking troubleshooting commands

---

## SOC Analyst Perspective

This room is useful for a SOC Analyst because it helps build a strong understanding of network communication and traffic flow. Knowledge of ARP, DHCP, subnetting, and LAN communication is important for monitoring suspicious activity, analyzing network logs, detecting internal threats, and investigating security incidents.

---

## Conclusion

The Intro to LAN room provided a solid foundation in networking fundamentals and helped improve my understanding of how devices communicate inside a network. These concepts are essential for cybersecurity and SOC Analyst roles.

---

## LinkedIn Post

Completed the “Intro to LAN” room on TryHackMe.

In this room, I learned networking fundamentals including LAN topology, subnetting, ARP, DHCP, IP addressing, and network communication basics.

I also practiced basic networking commands used for troubleshooting and connectivity testing.

This room helped strengthen my understanding of networking concepts that are essential for cybersecurity and SOC Analyst roles.

#TryHackMe #CyberSecurity #Networking #SOCAnalyst #LearningInPublic

---

## File Name Suggestion

intro-to-lan-tryhackme-writeup.md
