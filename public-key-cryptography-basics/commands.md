# 🔐 Public Key Cryptography Commands

This repository contains **practical commands and examples** of public key cryptography, key management, and secure communications.  
It is useful for **Security+ exam preparation** and demonstrates hands-on cybersecurity skills.

---

## 1. SSH Key Management

**Generate an Ed25519 SSH Key Pair**
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**Creates a private/public key pair**

-C adds a comment (useful for identification)

Default files: ~/.ssh/id_ed25519 and ~/.ssh/id_ed25519.pub

**Copy Public Key to Remote Host**
```bash
ssh-copy-id user@remote-host
```
Adds your public key to ~/.ssh/authorized_keys on the server

Enables passwordless SSH login

**Connect Using a Specific Private Key**
```bash
ssh -i ~/.ssh/id_ed25519 user@remote-host
```
Useful for multiple keys

---
**Set Secure Permissions on Private Key**

```bash
chmod 600 ~/.ssh/id_ed25519
```
Prevents unauthorized access

## 2. OpenSSL Key Generation and Management
Generate a 4096-bit RSA Private Key (Encrypted)
```bash
openssl genrsa -aes256 -out private_key.pem 4096
```

-aes256: Encrypts private key with AES-256

Strong key size for modern security

Generate Corresponding Public Key
```bash
openssl rsa -in private_key.pem -pubout -out public_key.pem
```
Generate a Self-Signed Certificate
```bash
openssl req -x509 -new -key private_key.pem -out cert.pem -days 365
```
Useful for testing TLS/SSL

req generates certificate signing request (CSR)
```bash
-x509 creates a self-signed cert
```
Inspect a Certificate
```bash
openssl x509 -in cert.pem -text -noout
```
Displays certificate details in human-readable format
Convert Key Formats (PEM ↔ DER)
```bash
openssl rsa -in key.pem -outform DER -out key.der
```

Useful for interoperability

## 3. File Encryption Using Public Key Cryptography
Encrypt a File Using RSA Public Key
```bash
openssl rsautl -encrypt -inkey public_key.pem -pubin -in secret.txt -out secret.enc
```
Decrypt a File Using RSA Private Key
```bash
openssl rsautl -decrypt -inkey private_key.pem -in secret.enc -out secret.txt
```

## 4. Digital Signatures
Sign a File
```bash
openssl dgst -sha256 -sign private_key.pem -out signature.bin file.txt
```
dgst = digest (hash)

SHA-256 ensures integrity

Verify a Signature
```bash
openssl dgst -sha256 -verify public_key.pem -signature signature.bin file.txt
```
Confirms authenticity and integrity

## 5. Hashing (Integrity Verification)
Generate SHA-256 Hash of a File
```bash
sha256sum file.txt
```
Verify File Integrity
```bash
sha256sum -c file.txt.sha256
```
Checks if file matches known hash

## 6. PKI (Public Key Infrastructure) Examples
Generate Certificate Signing Request (CSR)
```bash
openssl req -new -key private_key.pem -out request.csr
```

CSR can be submitted to a CA for a signed certificate

View CSR Details
```bash
openssl req -in request.csr -noout -text
```

