# Firewall Inspection Levels and OSI Layer Mapping

This document explains **how firewalls inspect traffic at different OSI layers** and clarifies the common confusion between **firewall placement (Layer 2/3)** and **firewall inspection depth (Layer 4/7)**. This topic is critical for **Security+ exam preparation** and practical network security design.

---

## Two Ways to Classify Firewalls

Firewalls can be classified in **two independent dimensions**:

1. **Where the firewall is deployed** (Network placement)
2. **What the firewall inspects** (Inspection depth)

These classifications are **not mutually exclusive**.

---

## 1. Firewall Classification by Network Placement

### Layer 2 Firewalls (Data Link Layer)
- Operate within the same network segment
- Filter traffic based on:
  - MAC addresses
  - VLAN membership
- Used for internal segmentation and east-west traffic control

**Use case**: Limiting lateral movement inside a network

---

### Layer 3 Firewalls (Network Layer)
- Operate between different networks or subnets
- Filter traffic based on:
  - Source IP address
  - Destination IP address
  - IP protocol (TCP, UDP, ICMP)

**Use case**: Protecting network boundaries and routing traffic securely

---

## 2. Firewall Classification by Inspection Depth

### Layer 4 Firewalls (Transport Layer) – “ID and Ticket Check”

Layer 4 firewalls inspect **transport-level information** without examining packet payloads.

#### Inspected Fields
- Source IP address
- Destination IP address
- Source port
- Destination port
- Transport protocol (TCP/UDP)
- Connection state:
  - NEW
  - ESTABLISHED
  - RELATED
- TCP flags:
  - SYN
  - ACK
  - FIN
  - RST

#### Capabilities
- Stateful inspection
- Allows return traffic from established sessions
- Blocks unsolicited inbound traffic

**Limitations**
- Cannot detect application-layer attacks
- Does not inspect payload content

---

### Layer 7 Firewalls (Application Layer) – “Bag Contents Inspection”

Layer 7 firewalls inspect the **actual content of traffic** and understand application protocols.

#### Inspected Data
- Application protocols (HTTP, HTTPS, FTP, SMTP, DNS)
- URLs and URI paths
- HTTP methods (GET, POST, PUT, DELETE)
- Headers (Cookies, User-Agent, Authorization)
- Payload content:
  - Form data
  - JSON/XML
  - File uploads
- Application behavior and protocol compliance

#### Capabilities
- Detects application-layer attacks:
  - SQL injection
  - Cross-site scripting (XSS)
  - Command injection
- Enforces application-specific security policies

**Common Example**
- Web Application Firewall (WAF)

---

## Analogy: Security Checkpoint

| Analogy Component | OSI Layer | Firewall Function |
|------------------|----------|------------------|
| ID check | Layer 3 | IP address verification |
| Ticket check | Layer 4 | Port and session validation |
| Bag inspection | Layer 7 | Payload and application analysis |

---

## How These Classifications Work Together

A single firewall can:
- Be **placed at Layer 3** (between networks)
- Perform **Layer 4 and Layer 7 inspection**

Example:
- A perimeter firewall between the internet and internal network
- Performs stateful inspection (Layer 4)
- Also runs a WAF module (Layer 7)

---

## Comparison Table

| Firewall Aspect | Layer 2 | Layer 3 | Layer 4 | Layer 7 |
|----------------|--------|--------|--------|--------|
| Focus | Segmentation | Routing | Sessions | Applications |
| Inspects | MAC / VLAN | IP | Ports / State | Payload |
| Visibility | Low | Medium | Medium | High |
| Performance | High | High | Medium | Lower |
| Security Depth | Low | Medium | High | Very High |

---

## Security+ Exam Tips

- **Layer 2 / Layer 3** → Where the firewall sits
- **Layer 4 / Layer 7** → How deeply it inspects traffic
- Packet filtering = stateless
- Stateful inspection = Layer 4
- WAF = Layer 7

---

## Key Takeaways

- Firewall placement and inspection depth are separate concepts
- Layer 4 firewalls validate sessions and traffic flow
- Layer 7 firewalls inspect actual application data
- Defense-in-depth often combines multiple inspection layers
- Understanding this distinction is essential for secure network design

---
