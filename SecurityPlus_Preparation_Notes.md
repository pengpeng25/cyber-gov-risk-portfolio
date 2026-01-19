# Security+ SY0-701 Prep Notes

## Digital Signature Steps
- The executive creates a **hash** of the document (e.g., using SHA-256) and **encrypts the hash with their private key**.
- This creates a **Digital Signature** that gets attached to the document.
- The recipient receives both the document and the sender's **public key** (from a trusted source).
- The recipient decrypts the signature using the sender's **public key**.
- The recipient compares the resulting hash with their own computed hash of the document.
  - If the hashes match, the document's **integrity is verified** and the sender is **authenticated**.
