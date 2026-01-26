# File Transfer, Email, and Video Services Protocols

This summary focuses on various **file transfer, email, and video services**, along with their associated protocols and ports.

---

## File Transfer Protocols

- **FTP (File Transfer Protocol)**
  - Most popular protocol for transferring files.
  - **Not secure**: Transmits credentials in plain text.
  - Default ports: **21** (control), **20** (data).

- **SFTP (SSH File Transfer Protocol)**
  - Secure version of FTP over **SSH**.
  - Encrypts both authentication and data transfer.
  - Uses **TCP port 22**.

- **FTPS (FTP Secure)**
  - Uses **SSL/TLS** for security.
  - **Explicit TLS (FTPES)**: Upgrades insecure connection on **port 21**.
  - **Implicit TLS (FTPS)**: Secure connection from the start on **port 990**.

---

## Email Protocols

- **SMTP (Simple Mail Transfer Protocol)**
  - Used for sending emails.
  - Port **25**: Message relay between servers.
  - Port **587**: Message submission from client to server.
  - Can be secured using **STARTTLS**, which upgrades an unencrypted connection to an encrypted one using TLS.

- **SMTPS (Secure SMTP)**
  - Establishes a secure connection before any commands are exchanged.
  - Typically uses **port 465 deprecated**.

- **POP3 (Post Office Protocol 3)**
  - Downloads emails from server to client.
  - Secure version **POP3S** uses **port 995**.

- **IMAP (Internet Message Access Protocol)**
  - Port **143**: Manages emails on the server without downloading.
  - Secure version **IMAPS** uses **port 993**.

- **S/MIME (Secure/Multipurpose Internet Message Extensions)**
  - Encrypt content with asymmetric cryptography
---

## Voice and Video Services

- **SIP (Session Initiation Protocol)**
  - Manages communication sessions (voice/video calls).
  - Port **5060**: Standard.
  - Port **5061**: Secure (TLS).

- **RTP (Real-time Transport Protocol)**
  - Delivers voice and video data in real-time.
  - Often used in conjunction with SIP.

---

This summary highlights the key protocols and their respective ports used in **file transfer, email, and voice/video services**, emphasizing security considerations where applicable.
