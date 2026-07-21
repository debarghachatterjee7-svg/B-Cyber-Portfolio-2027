# 📚 Day 17 Notes – SSH Fundamentals, Authentication Flow & Linux File Identification

---

# What is SSH?

SSH (Secure Shell) is a secure network protocol used to remotely access another computer over an encrypted connection.

It replaces insecure protocols like Telnet by encrypting all communication between a client and a server.

Common uses:

- Remote server administration
- Secure file transfer
- Cloud server management
- DevOps automation
- Ethical hacking
- Penetration testing

---

# Public Key Authentication

SSH commonly uses asymmetric cryptography.

Two mathematically related keys are generated.

## Public Key

- Can be shared.
- Stored on servers.
- Used for verification.
- Safe to distribute.

## Private Key

- Must remain secret.
- Stored only on the owner's machine.
- Used to prove identity.
- Never shared.

---

# SSH Authentication Flow

1. Client requests access.
2. Server checks for the user's public key.
3. Server sends a challenge.
4. Client signs the challenge using its private key.
5. Server verifies the signature using the stored public key.
6. Authentication succeeds.

---

# authorized_keys

Location:
Server

Purpose:
Stores trusted public keys that are allowed to authenticate.

Think of it as:

> The guest list of the server.

---

# known_hosts

Location:
Client

Purpose:
Stores fingerprints of trusted servers.

It helps SSH detect if a server's identity changes unexpectedly.

---

# SSH Fingerprints

SSH keys are very long.

Instead of comparing entire keys, SSH generates a fingerprint.

A fingerprint is:

- Short
- Unique
- Easy to compare

Usually generated using SHA-256.

---

# SHA-256

SHA-256 is a cryptographic hashing algorithm.

Properties:

- Deterministic
- One-way
- Collision resistant
- Fast

In SSH, SHA-256 creates fingerprints for easier verification.

---

# RandomArt

RandomArt is an ASCII visualization of an SSH fingerprint.

Purpose:

- Easier human verification
- Visual comparison of keys

RandomArt improves usability rather than security.

---

# Linux File Identification

Linux does not depend only on file extensions.

Instead, it examines the internal structure of files.

Useful command:

```bash
file filename
```

Example outputs:

```
OpenSSH private key
```

```
OpenSSH ED25519 public key
```

```
ASCII text
```

---

# Why the `file` Command Matters

Extensions can be changed easily.

Example:

```
virus.exe
↓

holiday_photo.jpg
```

The extension changes, but the file contents remain the same.

Linux identifies files based on their actual contents.

This is important during:

- Malware Analysis
- Digital Forensics
- Incident Response
- Penetration Testing

---

# Commands Learned Today

```bash
ssh-keygen
```

Generate an SSH key pair.

---

```bash
ls -la ~/.ssh
```

Display all SSH-related files.

---

```bash
cat ~/.ssh/id_ed25519.pub
```

View the public key.

---

```bash
cat ~/.ssh/id_ed25519
```

View the private key.

---

```bash
cat ~/.ssh/known_hosts
```

View trusted server entries.

---

```bash
file ~/.ssh/id_ed25519
```

Identify the private key.

---

```bash
file ~/.ssh/id_ed25519.pub
```

Identify the public key.

---

```bash
file ~/.ssh/known_hosts
```

Identify the known_hosts file.

---

# Important Points to Remember

- SSH encrypts communication.
- Public keys are shared.
- Private keys remain secret.
- authorized_keys trusts users.
- known_hosts trusts servers.
- SHA-256 generates fingerprints.
- RandomArt visualizes fingerprints.
- Linux identifies files by content, not extension.

---

# Summary

Today's session built the theoretical foundation of SSH authentication. Rather than focusing on advanced commands, the emphasis was placed on understanding how SSH establishes trust, how key-based authentication works, and how Linux identifies SSH-related files. These concepts are essential before moving to advanced `ssh-keygen` operations and continuing the OverTheWire Bandit roadmap.