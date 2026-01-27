# Transport Layer: UDP vs TCP

This file documents my learning progress on **transport layer networking concepts**, based on hands-on study and labs (e.g. TryHackMe). The focus is on understanding how **process-to-process communication** works and why it matters for **security, risk assessment, and governance**.

---

## Overview

While the IP protocol allows communication between hosts using IP addresses, it does not identify **which application or process** should receive the data. This functionality is provided by **transport layer protocols**.

The two main transport layer protocols are:

- **UDP (User Datagram Protocol)**
- **TCP (Transmission Control Protocol)**

Both operate at **Layer 4 of the OSI model**.

---

## UDP (User Datagram Protocol)

UDP is a **connectionless** transport protocol. It allows sending data to a specific process on a destination host **without establishing a connection** and **without guaranteeing delivery**.

### Key Characteristics

- Connectionless
- No delivery confirmation
- No retransmission
- Low overhead and high speed
- Uses **port numbers** to identify processes

Port numbers use **16 bits**, allowing values from **1 to 65535** (port 0 is reserved).

### Real-World Analogy

UDP is similar to **standard postal mail without delivery confirmation**:
- Fast and efficient
- No guarantee that the message arrives

### Typical Use Cases

- DNS
- VoIP
- Live audio/video streaming
- Online gaming

---

## TCP (Transmission Control Protocol)

TCP is a **connection-oriented** transport protocol designed for **reliable communication** between processes.

Before data transfer begins, TCP establishes a connection and continuously ensures data integrity.

### Key Characteristics

- Connection-oriented
- Reliable delivery
- Packet sequencing
- Acknowledgements and retransmission
- Flow control

Each data octet is assigned a **sequence number**, allowing the receiver to detect:
- Missing packets
- Duplicate packets
- Out-of-order delivery

---

## TCP Three-Way Handshake

A TCP connection is established using a **three-way handshake**, relying on two control flags:

- **SYN** (Synchronize)
- **ACK** (Acknowledgment)

### Steps

1. **SYN**
   - Client initiates the connection
   - Sends a SYN packet with an initial sequence number

2. **SYN-ACK**
   - Server responds with a SYN-ACK
   - Acknowledges the client’s sequence number
   - Provides its own sequence number

3. **ACK**
   - Client acknowledges the server
   - Connection is established

This mechanism ensures both parties are synchronized before data transfer.

---

## UDP vs TCP Comparison

| Feature | UDP | TCP |
|------|----|----|
| Connection | No | Yes |
| Reliability | No | Yes |
| Speed | Faster | Slower |
| Overhead | Low | Higher |
| Packet Ordering | No | Yes |
| Common Uses | Streaming, DNS | Web, Email, File Transfer |

---

## Security & GRC Relevance

Understanding transport protocols is important for:

- Firewall and network security rule design
- Detection of attacks (e.g. SYN floods, UDP amplification)
- Risk assessments involving availability and resilience
- Governance and compliance frameworks, including:
  - **ISO/IEC 27001** (network security, access control)
  - **NIS2 Directive** (availability and resilience of network services)

---

## Learning Outcome

This module strengthened my understanding of how **reliability, availability, and performance trade-offs** at the transport layer influence both **technical security controls** and **organizational risk decisions**.
