# Task 3: RSA

RSA is a **public-key encryption algorithm** used to securely transmit data over **insecure networks**, where attackers may be able to eavesdrop on communications.

It uses **two keys**:
- A **public key** to encrypt (lock) data
- A **private key** to decrypt (unlock) data

Only the private key can decrypt data encrypted with the corresponding public key.

---

## Why RSA Is Secure (High-Level)

RSA’s security relies on a mathematical problem that is **easy to perform one way but extremely difficult to reverse**.

- Multiplying two large prime numbers together is easy
- Factoring the resulting large number back into its original primes is extremely difficult

This asymmetry is what makes RSA practical for secure communication.

---

## The Math (Conceptual, Not Detailed)

For example:
- Multiplying two prime numbers is straightforward
- Even moderately large numbers become very difficult to factor once multiplied
- In real-world RSA, the prime numbers used are **hundreds of digits long**

Modern computers can multiply large numbers easily, but factoring a number with **600+ digits** is computationally infeasible with current technology.

This makes it impractical for attackers to derive the private key from the public key.

---

## How RSA Is Used in Practice

RSA is **not typically used to encrypt large amounts of data** because it is slow compared to symmetric encryption.

Instead, RSA is commonly used for:
- Secure **key exchange**
- **Authentication**
- **Digital signatures**

Once a secure connection is established, communication switches to **symmetric encryption** for efficiency.

---

## Real-World Examples

- **TLS/HTTPS** – RSA helps securely exchange encryption keys
- **SSH** – RSA authenticates users or servers
- **Digital certificates** – RSA verifies identity and trust

---

## Security+ Exam Relevance

For Security+, it is important to understand:
- RSA is an **asymmetric (public-key) algorithm**
- It uses a **public/private key pair**
- It is based on the difficulty of **factoring large numbers**
- It is used for **secure key exchange and authentication**, not bulk encryption

---

## Key Takeaway

RSA enables secure communication over insecure channels by using asymmetric keys. Its security depends on the practical impossibility of factoring very large numbers, making it a foundational component of modern cryptographic systems.
