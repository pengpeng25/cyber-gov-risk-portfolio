# Secure Switching and Routing (Layer 2 Security)

This file focuses on **security risks and defensive measures in Layer 2 networking**, specifically around switching and routing. It highlights common attacks that exploit trust-based protocols and the controls used to mitigate them. This content is aligned with **Security+ exam objectives** and demonstrates practical network security knowledge.

---

## Learning Objectives

- Understand common **Layer 2 attacks** and their impact  
- Explain how **ARP works** and why it is vulnerable  
- Identify **switch and router security controls**  
- Apply **defense-in-depth** to network infrastructure  

---

## Layer Two Attacks

Layer 2 attacks often target **information gathering and traffic manipulation**, frequently enabling **man-in-the-middle (MITM)** attacks due to weak trust mechanisms.

### Common Attacks

- **MAC Address Spoofing**  
  Attackers modify their MAC address to impersonate trusted devices, potentially bypassing access controls.

- **Man-in-the-Middle (MITM)**  
  Exploits Layer 2 weaknesses to intercept or alter traffic between hosts without detection.

---

## Address Resolution Protocol (ARP)

### Purpose of ARP
- Maps **IP addresses to MAC addresses**
- Enables communication between devices on the same local network

### ARP Vulnerabilities
- ARP has no authentication mechanism
- Devices trust received ARP replies by default

### ARP Poisoning
- Attackers send false ARP messages
- Traffic is redirected through the attacker
- Enables sniffing, session hijacking, and MITM attacks

---

## Switch Security Measures

### 1. Physical Port Security
- Restrict physical access to switches
- Disable unused ports
- Secure wiring closets and racks

### 2. MAC Filtering
- Allow only approved MAC addresses per port
- Prevents unauthorized device connections

### 3. MAC Limiting
- Limit the number of MAC addresses on a port
- Helps defend against MAC flooding attacks

### 4. DHCP Snooping
- Accept DHCP responses only from trusted ports
- Prevents rogue DHCP servers
- Mitigates traffic redirection attacks

### 5. Network Access Control (NAC)
- Enforces authentication before network access
- Devices must meet security policies
- Supports zero trust networking principles

### 6. Spanning Tree Protocol (STP)
- Prevents network loops
- Avoids broadcast storms
- Ensures network stability and availability

---

## Router Security Measures

### 1. Access Control
- Restrict access to router management interfaces
- Use strong authentication and role-based access

### 2. Firmware Updates
- Patch vulnerabilities
- Maintain secure and supported firmware versions

### 3. Network Segmentation
- Use VLANs to isolate traffic
- Reduces lateral movement by attackers

### 4. Secure Management Protocols
- Use SSH instead of Telnet
- Encrypt administrative traffic

### 5. Disable Unused Services
- Reduce attack surface
- Remove unnecessary features and ports

### 6. Monitoring and Logging
- Track configuration changes
- Detect unauthorized access
- Support incident response and audits

### 7. Firewall Configuration
- Filter inbound and outbound traffic
- Enforce network security policies

### 8. Intrusion Detection Systems (IDS)
- Monitor traffic for malicious activity
- Alert on potential router-targeted attacks

---

## Security+ Exam Relevance

This module supports understanding of:
- Layer 2 attacks and defenses
- ARP poisoning and MAC spoofing
- Defense-in-depth strategies
- Network infrastructure hardening

---

## Key Takeaway

Layer 2 networks rely heavily on trust, making them vulnerable to spoofing and MITM attacks. Strong security requires a combination of physical controls, protocol protections, access enforcement, and continuous monitoring.
