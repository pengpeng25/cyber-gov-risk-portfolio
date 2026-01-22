# Public Key Cryptography Basics

This project documents my learning from the TryHackMe room **Public Key Cryptography Basics**.  
It focuses on how cryptography supports secure communication by providing **authentication, authenticity, integrity, and confidentiality**

Consider a real-life scenario: communicating with your business partner over an online messaging platform, you need to be sure of the following:

- **Authentication**: You want to be sure you communicate with the right person, not someone else pretending.

- **Authenticity**: You can verify that the information comes from the claimed source.

- **Integrity**: You must ensure that no one changes the data you exchange.

- **Confidentiality**: You want to prevent an unauthorised party from eavesdropping on your conversations.

To address these challenges, modern systems rely on **cryptography**.

---

## Role of Cryptography

- **Symmetric (Private Key) Cryptography**
  - Primarily used to ensure **confidentiality**
  - Same key is used for encryption and decryption

- **Asymmetric (Public Key) Cryptography**
  - Plays a critical role in:
    - Authentication
    - Authenticity
    - Integrity
  - Uses a public/private key pair
 
- **Digital Signature = Hash + Public Key**
  - Does **not** ensure **confidentiality**
 
- **Public Key Infrastructure (PKI)**
  - CA verify the public key / certificate
    
This project focuses on **public key cryptography** and how it is applied in real-world systems.

---


## Topics Covered in This Project

This project explores the fundamentals and real-world applications of **public key (asymmetric) cryptography**, with each topic documented in detail:

- **[Use of Asymmetric Encryption](task-2-asymmetric-encryption.md)**  
  How public key cryptography is used to solve key distribution, authentication, and trust problems in secure communications.

- **[RSA](task-3-rsa.md)**  
  An overview of the RSA algorithm, how public/private key pairs work, and how RSA supports encryption and digital signatures.

- **[Diffie-Hellman Key Exchange](task-4-diffie-hellman.md)**  
  How two parties securely establish a shared secret over an untrusted network.

- **[SSH (Secure Shell)](task-5-ssh.md)**  
  How asymmetric cryptography enables secure remote authentication and encrypted administration sessions.

- **[Digital Signatures and Certificates (SSL/TLS)](task-6-digital-signatures-certificates.md)**  
  How digital signatures, certificate authorities (CAs), and PKI establish trust, integrity, and authentication on the web.

- **[PGP and GPG](task-7-pgp-gpg.md)**  
  How public key cryptography is used to secure email communication and verify message authenticity.

Each section includes:
- Core concept explanations
- Security implications
- Real-world use cases
- Relevance to the CompTIA Security+ exam

---


## Public Key Cryptography Commands 

- **[practical commands and examples](commands.md)** 

