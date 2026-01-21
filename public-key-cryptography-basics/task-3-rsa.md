# Task 3: RSA

RSA is a **public-key encryption algorithm** used to securely transmit data over **insecure networks**, where attackers may be able to eavesdrop on communications.

It uses **two keys**:
- A **public key** to encrypt (lock) data
- A **private key** to decrypt (unlock) data

Only the private key can decrypt data encrypted with the corresponding public key.

---

RSA is **not typically used to encrypt large amounts of data** because it is slow compared to symmetric encryption.

Instead, RSA is commonly used for:
- Secure **key exchange**
- **Authentication**
- **Digital signatures**

## Once a secure connection is established, communication switches to **symmetric encryption** for efficiency.

Examples

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

# Why RSA Is Secure – Numeric Example

RSA is a public-key cryptographic algorithm whose security is based on a **mathematical problem that is easy to perform in one direction but extremely difficult to reverse**.

- n is public n = p × q
- ϕ(n) is **secret**, because it depends on the secret primes p and q.  
- ϕ(n) is used to compute the **private key**.  
- Without factoring n, an attacker cannot calculate ϕ(n) and cannot derive the private key.  


Example:

- p = 4391  
- q = 6659  

n = p × q = 4391 × 6659 = 29,239,669

This calculation is quick and easy.

**n** is made public.

---

## Hard Operation: Factoring

An attacker sees only the public value:

n = 29,239,669


The attacker’s challenge is to determine the two prime numbers p and q such that:

p × q = n


Even with a number this small, factoring already requires effort. As the size of **p** and **q** increases, factoring becomes dramatically harder.

In real-world RSA:
- Prime numbers are **hundreds of digits long**
- The resulting value of **n** can be **600+ digits**
- Factoring such numbers is computationally infeasible with current technology

---

### Why Factoring Matters in RSA

RSA security depends on keeping the prime numbers **p** and **q** secret.

The private key is derived using Euler's totient function:

ϕ(n) = (p - 1) × (q - 1)

Using our example:

ϕ(n) = (4391 - 1) × (6659 - 1) = 4390 × 6658 = 29,228,620

If an attacker could factor `n` to find `p` and `q`, they could compute ϕ(n) and derive the **private key**, breaking the system.

Because factoring `n` becomes impractical for large numbers, the private key remains secure. This imbalance is what protects RSA.

---

### Security Relevance

- RSA security is based on **prime factorization**
- Public values are easy to compute
- Private values are protected by mathematical hardness
- Larger key sizes = stronger security

---


## Key Takeaway

RSA is secure because it relies on a mathematical problem that is easy to perform in one direction but extremely difficult to reverse. As long as large prime numbers are used, deriving the private key from the public key remains computationally infeasible.

