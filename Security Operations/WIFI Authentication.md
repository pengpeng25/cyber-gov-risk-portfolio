# Wi-Fi Authentication Methods

This course content focuses on Wi-Fi authentication methods, detailing the different types, mechanisms, and associated security concerns.

---

## Wi-Fi Authentication Types

There are three main types of Wi-Fi authentication:

- **Open**  
  No authentication is required; anyone can connect to the network.  

- **Personal**  
  Methods that rely on a shared secret between the user and the network. Includes:  
  - **Pre-Shared Key (PSK)**  
  - **Simultaneous Authentication of Equals (SAE)**  

- **Enterprise**  
  Designed for larger networks, requiring credentials verified by a central server.

---

## Personal Authentication Methods

- **Pre-Shared Key (PSK)**  
  - Uses a passphrase (8–63 characters) to generate a 256-bit HMAC value known as the **Pairwise Master Key (PMK)**.  

- **WPA3 Enhancements**  
  - Introduces **Password Authenticated Key Exchange (PAKE)**.  
  - Replaces the four-way handshake with the **Dragonfly handshake** for enhanced security.

---

## Enterprise Authentication

- Utilizes **IEEE 802.1X** and the **Extensible Authentication Protocol (EAP)** for secure credential validation through an **AAA server**.  

- **EAP Methods**  
  - Supports various authentication methods including **smart cards** and **biometric identifiers**.  
  - **EAP-TLS** is considered one of the strongest forms of authentication.

---

## Wi-Fi Authentication Protocols

- **Protected Extensible Authentication Protocol (PEAP)**  
  - Establishes an **encrypted tunnel** between the supplicant and the authentication server.  
  - Requires only a **server-side public key certificate**.  

- **EAP-TLS**  
  - Similar to PEAP but can use **any authentication protocol**, such as CHAP.  
  - PEAP is limited to **EAP-MSCHAPv2** or **EAP-GTC**, while EAP-TLS offers broader flexibility.

---

## Attacks Against Wi-Fi Authentication

- **Rogue Access Points and Evil Twins**  
  - Rogue APs are **unauthorized installations**.  
  - Evil twins **mimic legitimate access points** to deceive users.  

- **Disassociation and Replay Attacks**  
  - Disassociation attacks exploit **unencrypted management frames** to disconnect users.  
  - They can be combined with **replay attacks** to recover network keys.

---

## Mitigation Strategies

- **Management Frame Protection (MFP)**  
  - Protects against **disassociation attacks** and similar threats.  

- **Identifying Rogue Access Points**  
  - Use **physical inspections** and **Wi-Fi analyzers** to detect unauthorized APs.

