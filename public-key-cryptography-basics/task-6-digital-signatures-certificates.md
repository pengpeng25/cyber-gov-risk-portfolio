# Task 6: Digital Signatures and Certificates

## Digital Signatures
Digital signatures verify the **authenticity** and **integrity** of digital documents:  
- Created using a **private key**  
- Verified using the corresponding **public key**  
- Protects against tampering, unlike pasted images of signatures  

**How it works:**  
1. Compute a hash of the document  
2. Encrypt the hash with your private key → digital signature  
3. Recipient decrypts the hash with your public key and compares it to the document hash  

---

## Certificates
Certificates prove **identity** in digital communications (e.g., HTTPS):  
- Contain a **public key** and identity information  
- Signed by a trusted **Certificate Authority (CA)**  
- Browsers trust websites via a **chain of trust**:  
  `Website Certificate → Organization → Root CA → Browser`  

**Practical notes:**  
- TLS certificates can be purchased or obtained for free via **Let’s Encrypt**  
- Certificates ensure secure communication and trust on the web  

---

**Key Takeaways:**  
- Digital signatures = authenticity + integrity  
- Certificates = identity + trust chain  
- Both are essential for secure digital communication and legal validity
