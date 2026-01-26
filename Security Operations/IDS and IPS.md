# Network Security Monitoring: IDS and IPS

This content focuses on network security monitoring, specifically discussing **Intrusion Detection Systems (IDS)** and **Intrusion Prevention Systems (IPS)**, their functions, and detection methods.

---

## Intrusion Detection Systems (IDS)

- **Purpose:** IDS uses software tools for **real-time analysis** of network traffic or system/application logs to detect potential threats.  

- **Network-based IDS (NIDS):**  
  - Captures traffic via **packet sniffers**.  
  - Performs **passive detection**, alerting administrators of suspicious activity without blocking malicious traffic.  

- **Key Function:** Monitoring and alerting to suspicious network or host activity.

---

## Network Intrusion Prevention Systems (IPS)

- **Purpose:** IPS actively responds to network threats to **prevent attacks**.  

- **Key Actions:**  
  - Blocks attackers' IP addresses.  
  - Applies firewall filters or other countermeasures.  

- **Deployment:**  
  - IPS appliances are typically positioned at **network borders**.  
  - Must handle **high bandwidth** to avoid slowing down legitimate network traffic.  

---

## Detection Methods

- **Signature-based Detection:**  
  - Matches traffic against **known attack patterns**, similar to how antivirus software operates.  

- **Behavioral / Anomaly-based Detection:**  
  - Identifies **deviations from normal traffic patterns**.  
  - Often uses **machine learning** to establish a baseline of normal network behavior.

---

## Summary

IDS and IPS are critical components of **network security monitoring**. IDS focuses on **detection and alerting**, while IPS adds **active prevention**. Both systems rely on **signature and anomaly-based detection** to identify malicious activity, helping organizations protect networks and systems from attacks.

