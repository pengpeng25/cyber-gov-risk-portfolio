# Public Key Cryptography Basics

This project documents my learning from the TryHackMe room **Public Key Cryptography Basics**.  
It focuses on how cryptography supports secure communication by providing **authentication, authenticity, integrity, and confidentiality**—core concepts for both real-world cybersecurity and the CompTIA Security+ exam.


---

## Security Concepts Explained (Everyday Analogy)

Consider a real-life scenario: meeting a business partner over coffee to discuss confidential plans.

From a security perspective:

- **Authentication**  
  You can see the person in front of you and confirm they are who they claim to be.

- **Authenticity**  
  You know the words you hear are coming from your business partner, not someone else nearby.

- **Integrity**  
  You can be confident that the message is not altered while being communicated across the table.

- **Confidentiality**  
  By choosing a quiet seat and speaking softly, you prevent others from overhearing the conversation.

These same principles are required in digital communication—but enforcing them online is much harder.

---

## The Cybersecurity Challenge

When communicating over a network, such as sending messages or accessing online services, several questions arise:

- How can you be sure the other party is not impersonating someone else?
- How can you confirm the message was not altered in transit?
- How can you prevent unauthorized parties from eavesdropping?

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


