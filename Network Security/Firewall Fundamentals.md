
# Firewall Fundamentals

This module introduces the **core concepts of firewalls**, focusing on how different firewall types inspect traffic and enforce security policies. It also covers **iptables**, a common Linux-based firewall management tool. These concepts are highly relevant to **Security+** and real-world network defense.

---

## What Is a Firewall?

A firewall is a security control that monitors and filters network traffic between trusted and untrusted networks based on predefined rules. Its primary goal is to **prevent unauthorized access** while allowing legitimate communication.

---

## Packet Filtering Firewalls (Stateless)

### Overview
- The **earliest type of firewall**
- Also known as **stateless firewalls**
- Use **Access Control Lists (ACLs)** to define rules

### How They Work
Packet filtering firewalls inspect **packet headers only**, including:
- Source IP address
- Destination IP address
- Source and destination ports
- Protocol (TCP, UDP, ICMP)

Each packet is evaluated **independently**, without awareness of previous packets.

### Limitations
- No understanding of connection state
- Cannot distinguish between legitimate response traffic and malicious packets
- Vulnerable to spoofing and certain attacks

---

## Stateful Inspection Firewalls

### Overview
- More advanced than packet filtering firewalls
- Maintain awareness of active connections

### How They Work
- Track sessions using a **state table**
- Monitor the **TCP three-way handshake**
- Allow return traffic only if it belongs to an **established session**

### OSI Layer Involvement
- Primarily operate at **Layer 4 (Transport)**
- Some can also inspect **Layer 7 (Application)** data to:
  - Validate protocol behavior
  - Detect malformed or suspicious traffic

### Advantages
- Improved security
- Blocks unsolicited inbound traffic
- Reduces attack surface while preserving functionality

---

## Iptables and Firewall Management

### What Is iptables?
- A **Linux command-line utility** for managing firewall rules
- Supports both packet filtering and stateful inspection

### Key Capabilities
- Define allow/deny rules for traffic
- Set default policies (accept or drop traffic)
- Filter traffic based on:
  - IP addresses
  - Ports
  - Protocols
  - Connection states (NEW, ESTABLISHED, RELATED)

### Stateful Rules
- iptables can permit traffic from **established connections**
- Commonly used to allow return traffic while blocking unsolicited access

---

## Security+ Exam Relevance

This module supports understanding of:
- Stateless vs stateful firewalls
- Transport and application layer inspection
- Firewall rule logic
- Linux-based firewall concepts

---

## Key Takeaways

- Packet filtering firewalls are fast but limited and stateless
- Stateful inspection firewalls provide stronger security by tracking sessions
- iptables is a practical implementation of firewall concepts in Linux systems
- Proper firewall configuration is essential for network defense

