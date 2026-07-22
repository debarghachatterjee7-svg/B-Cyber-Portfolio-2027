# 📝 Notes 012 — SSH Keys, RSA, ED25519, Fingerprints & SSH Authentication

**Day:** 018  
**Date:** 22 July 2026  
**Status:** ✅ Completed

---

# 📚 SSH (Secure Shell)

SSH is a secure protocol used to remotely access and manage Linux systems over an encrypted connection.

It provides:

- Secure remote login
- Secure command execution
- Secure file transfer (SCP/SFTP)
- Encrypted communication

---

# 🔑 SSH Authentication Methods

There are two common authentication methods:

### 1. Password Authentication

- User enters a password.
- Server verifies the password.

Advantages:
- Simple

Disadvantages:
- Passwords can be guessed or stolen.

---

### 2. Public Key Authentication

Uses asymmetric cryptography.

Advantages:

- More secure
- No password sent over the network
- Resistant to brute-force attacks

---

# 🔐 Asymmetric Cryptography

SSH uses two mathematically related keys.

## Private Key

- Secret
- Stored on the client
- Never shared
- Used to prove identity

---

## Public Key

- Safe to share
- Stored on the server
- Used to verify the client

---

# ⚙️ ssh-keygen

`ssh-keygen` is the OpenSSH key management utility.

Functions:

- Generate SSH keys
- Display fingerprints
- Display Randomart
- Manage key files

---

# 🏷️ ssh-keygen Options

## `-t`

Specifies the **type (algorithm)** of key to generate.

Example:

```bash
ssh-keygen -t rsa
```

---

## `-b`

Specifies key length (mainly for RSA).

Example:

```bash
ssh-keygen -t rsa -b 3072
```

---

## `-f`

Specifies the file to read from or save to.

Example:

```bash
ssh-keygen -lf id_rsa.pub
```

---

## `-l`

Lists the fingerprint of a key.

---

## `-v`

Verbose mode.

Displays additional information, including Randomart.

---

# 🔒 RSA

RSA is a widely supported public-key cryptographic algorithm.

Characteristics:

- Mature
- Highly compatible
- Larger key size
- Slower than modern algorithms

Common key size:

- 3072 bits

---

# ⚡ ED25519

ED25519 is the modern recommended SSH algorithm.

Characteristics:

- Fast
- Small keys
- Strong security
- Efficient
- Recommended by OpenSSH

---

# 📌 RSA vs ED25519

| RSA | ED25519 |
|------|----------|
| Older | Modern |
| Larger keys | Smaller keys |
| Slower | Faster |
| Maximum compatibility | Recommended for new systems |

---

# 🔍 SSH Fingerprint

A fingerprint is a short cryptographic identifier generated from a public key.

Purpose:

- Verify key identity
- Detect key changes
- Prevent Man-in-the-Middle attacks

Common format:

```
SHA256:xxxxxxxxxxxxxxxxxxxx
```

---

# 🎨 Randomart

Randomart is a graphical representation of an SSH fingerprint.

Purpose:

- Makes fingerprints easier for humans to recognize
- Helps notice unexpected key changes

Randomart is **not** a security feature—it is only a visual aid.

---

# 📂 ~/.ssh Directory

The `.ssh` directory stores SSH configuration and key files.

Common files:

- id_rsa
- id_rsa.pub
- id_ed25519
- id_ed25519.pub
- known_hosts
- authorized_keys

---

# 📄 Important SSH Files

## id_rsa

RSA private key.

Never share it.

---

## id_rsa.pub

RSA public key.

Safe to distribute.

---

## id_ed25519

ED25519 private key.

Never share it.

---

## id_ed25519.pub

ED25519 public key.

Safe to distribute.

---

## known_hosts

Stores trusted SSH server identities.

Purpose:

- Verify servers
- Prevent connecting to fake servers

---

## authorized_keys

Stored on the server.

Contains public keys allowed to log in.

---

# 🔄 SSH Authentication Flow

```
Client

↓

Connects to Server

↓

Server sends Host Key

↓

Client checks known_hosts

↓

If trusted

↓

Client proves identity using Private Key

↓

Server checks authorized_keys

↓

Access Granted
```

---

# 💡 Key Takeaways

- SSH provides secure remote communication.
- Public and private keys work together for authentication.
- Private keys must remain secret.
- Public keys are safe to share.
- RSA is widely compatible.
- ED25519 is the recommended modern algorithm.
- Fingerprints uniquely identify SSH keys.
- Randomart visually represents fingerprints.
- `known_hosts` stores trusted server identities.
- `authorized_keys` stores trusted client public keys.

---

# 🎯 Commands Learned

```bash
ssh -V

ssh-keygen

ssh-keygen -t rsa -b 3072

ssh-keygen -t ed25519

ssh-keygen -lf id_rsa.pub

ssh-keygen -lvf id_rsa.pub

ls -la ~/.ssh

cat ~/.ssh/known_hosts
```

---

# 📝 Revision Checklist

- [x] SSH Overview
- [x] SSH Authentication
- [x] Asymmetric Cryptography
- [x] Public & Private Keys
- [x] RSA
- [x] ED25519
- [x] ssh-keygen
- [x] ssh-keygen Options
- [x] Fingerprints
- [x] Randomart
- [x] known_hosts
- [x] authorized_keys
- [x] SSH Authentication Workflow