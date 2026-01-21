# Task 4: Diffie-Hellman Key Exchange

One challenge with **symmetric encryption** is sharing the secret key securely.  
For example, if you want to send a password-protected document to a business partner, how can you share the password without anyone else reading it?  

The **Diffie-Hellman (DH) Key Exchange** solves this problem. It allows two parties to create a **shared secret key** over an insecure channel **without sending the key directly**. This shared key can then be used for symmetric encryption in future communications.

---

## How Diffie-Hellman Works (Conceptually)

1. Alice and Bob agree on some public values. These are safe to share openly.  
2. Each chooses a private secret that they never reveal.  
3. They exchange information derived from their private secrets and the public values.  
4. Using their own secret and the received information, both arrive at the **same shared secret key**.  

> The key is that an eavesdropper can see all the public information but **cannot compute the shared secret** without knowing the private secrets.

---
## Numeric Example: Diffie-Hellman Key Exchange

To illustrate Diffie-Hellman in action:

- Public prime: p = 29  
- Public generator: g = 5  

Alice chooses a private key a = 12 → calculates her public key:  
A = g^a mod p = 7

Bob chooses a private key b = 17 → calculates his public key:  
B = g^b mod p = 9

Each calculates the shared secret key:

- Alice: key = B^a mod p = 9^12 mod 29 = 24  
- Bob: key = A^b mod p = 7^17 mod 29 = 24

✅ Both arrive at the **same shared secret key: 24**
---
## Why Diffie-Hellman is Useful

- **Secure key agreement:** Lets two parties establish a secret key over an insecure channel.  
- **Works with RSA:** DH creates the shared symmetric key, while RSA can provide authentication and digital signatures.  
- **Prevents man-in-the-middle attacks** if combined with authentication.  

Many security protocols (TLS, SSH, VPNs) use **Diffie-Hellman** for secure key exchange, combined with other cryptographic techniques for authentication and integrity.
