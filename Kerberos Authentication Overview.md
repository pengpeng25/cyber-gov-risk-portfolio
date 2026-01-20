# Kerberos Authentication and Ticketing – Technical Overview

Kerberos is a **network authentication protocol** designed to provide **secure, centralized, and mutual authentication** between users and services over an untrusted network.  
It is the **default authentication mechanism in modern Windows domains** and relies on **tickets** rather than repeatedly transmitting user credentials.

At its core, Kerberos uses a trusted third party called the **Key Distribution Center (KDC)**, typically running on a **Domain Controller**, to issue cryptographic tickets that prove a user has already authenticated.

---

## Kerberos Tickets Overview

Kerberos authentication revolves around **tickets**, which act as **proof of prior authentication**.

The two most important ticket types are:

- **Ticket Granting Ticket (TGT)** – proves the user authenticated successfully
- **Service Ticket (TGS)** – grants access to a specific service

Tickets are commonly:
- Base64 encoded
- Stored as `.kirbi` (Rubeus) or `.ccache` (Impacket)
- Reusable until expiration
- Frequently targeted in Kerberos-based attacks

---

## High-Level Kerberos Authentication Flow

![Kerberos – Full Authentication Flow](images/kerberos_all_steps.png)

> *Diagram source: TryHackMe – Kerberos Authentication*

---

## The 5 Core Steps of Kerberos Authentication

### **Step 1 – Initial Authentication Request (AS-REQ)**

The user initiates authentication by sending:
- Their **username**
- A **timestamp encrypted with a key derived from their password**

to the **Key Distribution Center (KDC)**.

This step proves knowledge of the password **without sending the password itself**.

---

### **Step 2 – Ticket Granting Ticket Issued (AS-REP)**

If the credentials are valid, the KDC responds with:

- A **Ticket Granting Ticket (TGT)**  
- A **Session Key**

The **TGT is encrypted using the `krbtgt` account’s password hash**, meaning:
- The user **cannot read or modify** the TGT
- Only the KDC can decrypt it

The encrypted TGT **contains a copy of the Session Key**, allowing the KDC to recover it later without storing session state.

![Kerberos – Steps 1 and 2](images/kerberos_step1_2.png)

> *Diagram source: TryHackMe – Kerberos Authentication*

---

### **Step 3 – Service Ticket Request (TGS-REQ)**

When the user wants to access a network service (file share, website, database, etc.), they send:

- The **TGT**
- A **timestamp encrypted with the Session Key**
- The **Service Principal Name (SPN)** of the target service

to the KDC.

The SPN identifies **which service and server** the user wants to access.

---

### **Step 4 – Service Ticket Issued (TGS-REP)**

If the request is valid, the KDC issues a **Service Ticket (TGS)** along with a **Service Session Key**.

Key details:

- The **TGS is encrypted using the service account’s password hash**
- Only the target service can decrypt it
- The encrypted TGS contains a copy of the Service Session Key

![Kerberos – Steps 3 and 4](images/kerberos_step3_4.png)

> *Diagram source: TryHackMe – Kerberos Authentication*

---

### **Step 5 – Service Authentication**

The user presents the **Service Ticket** to the target service.

The service:
- Decrypts the TGS using its account password hash
- Validates the Service Session Key
- Grants access if validation succeeds

At this point, **mutual authentication is complete**, and the user is allowed to interact with the service.

![Kerberos – Step 5](images/kerberos_step5.png)

> *Diagram source: TryHackMe – Kerberos Authentication*

---

## Ticket Deep Dive

### Ticket Granting Ticket (TGT)

![Ticket Granting Ticket (TGT)](images/kerberos_tgt.png)

Key characteristics:

- Issued after successful authentication
- Encrypted with the **krbtgt account key**
- Cannot be read or altered by the user
- Used **only to request service tickets**
- Valid for a limited lifetime

The TGT allows Kerberos to avoid repeatedly transmitting credentials, improving both **security and performance**.

---

### Service Ticket (TGS)

![Kerberos Service Ticket](images/kerberos_service_ticket.png)

Key characteristics:

- Grants access to **one specific service**
- Encrypted with the **service account’s password hash**
- Contains a Service Session Key
- Presented directly to the target service

Because service tickets are tied to service accounts, they are commonly targeted in attacks such as **Kerberoasting**.

---

## Why Kerberos Uses Tickets

Kerberos tickets enable:

- **Single Sign-On (SSO)**  
- Reduced exposure of credentials  
- Centralized authentication and authorization  
- Mutual authentication between users and services  

Tickets serve as cryptographic proof that authentication has already occurred.

---

## Security Relevance

Kerberos is central to enterprise security, but it is also a frequent attack target. Common attack techniques include:

- Kerberoasting
- Golden Ticket attacks
- Silver Ticket attacks
- Ticket reuse and pass-the-ticket attacks

Understanding ticket structure and flow is critical for **both defense and detection**.

---

## Attribution

> **Image Source and Credit**  
> All diagrams used in this document are adapted from **TryHackMe – Kerberos Authentication** learning materials.  
> They are used for **educational and portfolio purposes only**.  
> All rights belong to their respective owners.  
>  
> Source: https://tryhackme.com
