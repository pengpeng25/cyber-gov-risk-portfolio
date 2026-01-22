# Task 5: Secure Shell (SSH)

Secure Shell (SSH) is a cryptographic network protocol used to securely access and manage remote systems over an insecure network. SSH provides **confidentiality, integrity, and authentication** using public key cryptography and symmetric encryption.

---

## Authenticating the Server

When connecting to a server via SSH for the first time, the client prompts the user to verify the server’s identity:

Are you sure you want to continue connecting (yes/no)?


This occurs because the SSH client does not yet recognize the server’s **public key fingerprint**.

- The server proves its identity using a **public/private key pair**
- The client verifies the server’s public key
- This process helps prevent **man-in-the-middle (MITM) attacks**

Once accepted, the server’s public key is stored locally in:

```bash
~/.ssh/known_hosts
```

Future connections will only succeed if the server presents the same public key.

---

## Authenticating the Client

After the server is authenticated, the client must authenticate itself.

### Password Authentication
- Uses a username and password
- Vulnerable to brute-force attacks and credential reuse
- Not recommended for high-security environments

### Key-Based Authentication (Best Practice)
- Uses **public and private key cryptography**
- The client proves identity using a **private key**
- The server verifies identity using the corresponding **public key**

No passwords are transmitted over the network.

---

## SSH Key Generation

SSH key pairs are generated using `ssh-keygen`.

Example using the recommended algorithm:

```bash
ssh-keygen -t ed25519
```
---

## 🔐 SSH Key Algorithms

Common SSH key algorithms include:

| Algorithm | Description |
|---------|-------------|
| RSA | Widely supported, requires large key sizes |
| ECDSA | Elliptic curve variant of DSA |
| Ed25519 | Fast, secure, and modern (**recommended**) |
| `*-SK` | Uses hardware security keys |

---

## 🔒 Private Key Security

SSH private keys must be protected like passwords.

### Best Practices
- Never share private keys
- Use a strong passphrase
- Passphrases are never transmitted over the network

### Required File Permissions

SSH enforces strict permissions on private keys:

```bash
chmod 600 private_key
```
SSH will refuse to use private keys with insecure permissions.

## 🗝️ Authorized Keys on the Server

Public keys trusted by the server are stored in:

```bash
~/.ssh/authorized_keys
```


- One public key per line
- Determines which users are allowed to authenticate
- More secure than password-based authentication

🔐 **Root SSH access** should use key-based authentication only or be disabled entirely.

---

## ⚙️ Common SSH Commands

```bash
ssh-keygen -t ed25519
cat ~/.ssh/id_ed25519.pub
ssh-copy-id user@host
ssh -i privateKeyFileName user@host
```



