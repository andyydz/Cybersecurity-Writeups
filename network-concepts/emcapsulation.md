# Networking Fundamentals: Encapsulation — SOC Lab Writeup


![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-blue)
![Category](https://img.shields.io/badge/Category-Networking%20Fundamentals-orange)



> **Key finding:** The Data Link Layer is the only OSI layer that adds both a header and a trailer — the trailer is what enables error-checking before a frame ever hits the wire.

---

## Overview

Encapsulation is the process of adding protocol information to data as it moves down the OSI layers before transmission, with each layer wrapping the data in its own header (and, at one layer, a trailer) so it can be properly addressed, routed, and delivered. This writeup documents my hands-on walkthrough of TryHackMe's **Networking Fundamentals: Encapsulation** room, covering how data is built up layer by layer for transmission and torn back down on arrival.



---

## What I Actually Found

| Investigation | Finding |
|---|---|
| Layers 7–5 (App/Presentation/Session) | User data is created and prepared for transmission — no transport/network info added yet |
| Layer 4 (Transport) | TCP wraps data into a **Segment**; UDP wraps data into a **Datagram** |
| Layer 3 (Network) | Adds logical addressing (source/destination IP) — data unit becomes a **Packet** |
| Layer 2 (Data Link) | Adds MAC addressing and error-checking info — data unit becomes a **Frame**; only layer that adds a trailer |
| Layer 1 (Physical) | Frame converted into electrical, optical, or radio signals and transmitted as raw bits |
| De-encapsulation | Reverse process on the receiving host — each layer strips its own header/trailer until original data is recovered |

---

## Hands-On Activities

### Mapping the Encapsulation Process
- Traced data moving down from Layer 7 to Layer 1, identifying what each layer adds
- Identified the correct data unit name at each layer (Segment, Datagram, Packet, Frame, Bits)

### Identifying the Trailer
- Confirmed the Data Link Layer is the only layer in the OSI model that appends a trailer in addition to a header
- Connected this to the layer's role in error-checking

### De-encapsulation Walkthrough
- Reversed the process to understand how the receiving host strips headers/trailers layer by layer
- Mapped how the original application data is reconstructed at the top of the stack

### Security vs Encapsulation
- Distinguished encapsulation (a packaging mechanism) from security (provided separately by protocols like TLS, SSH, and IPsec)

---

## Key Terms

| OSI Layer | Data Unit |
|---|---|
| Layer 4 (TCP) | Segment |
| Layer 4 (UDP) | Datagram |
| Layer 3 | Packet |
| Layer 2 | Frame |
| Layer 1 | Bits |

---

## SOC Analyst Relevance

| Skill Practiced | SOC Application |
|---|---|
| OSI layer mapping | Quickly identifying which layer a network alert or anomaly originates from |
| Data unit terminology | Communicating precisely in incident reports (segment vs packet vs frame) |
| Header/trailer awareness | Understanding what's available for inspection at each layer during packet analysis |
| De-encapsulation logic | Reasoning through how traffic is reconstructed when reading PCAPs in Wireshark |
| Encapsulation vs security distinction | Avoiding false assumptions that routing/addressing protocols imply confidentiality |

---

## Conclusion

Encapsulation is a fundamental networking concept that enables communication between devices. Each OSI layer adds the information required for routing, delivery, and error checking, while the receiving host performs de-encapsulation to recover the original data. Understanding this layer-by-layer breakdown is foundational for reading packet captures and reasoning about where in the stack a given security control or vulnerability actually sits.

---

## Key Takeaways

- Each OSI layer adds its own header (and, at Layer 2, a trailer) as data moves down the stack toward transmission
- Data unit names change per layer: Segment/Datagram (L4) → Packet (L3) → Frame (L2) → Bits (L1)
- The Data Link Layer is uniquely responsible for the trailer, which supports error-checking
- De-encapsulation is simply encapsulation in reverse, performed by the receiving host
- Encapsulation handles packaging and delivery — it is not a security mechanism on its own; that's the job of protocols like TLS, SSH, and IPsec

---

*Part of my [TryHackMe SOC & Blue Team writeups](https://github.com/andyydz/TryHackMe-Writeups) series.*
