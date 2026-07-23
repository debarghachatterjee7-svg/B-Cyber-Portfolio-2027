# SSH Public Key Authentication & OpenSSH Fundamentals

> **Category:** Linux • OpenSSH • Authentication  
> **Difficulty:** Intermediate  
> **Related Lab:** Lab013  
> **Related Challenge:** OverTheWire Bandit Level 13

---

# Overview

SSH (Secure Shell) is one of the most widely used secure remote administration protocols.

Unlike password authentication, SSH also supports **Public Key Authentication**, allowing users to authenticate securely without transmitting passwords across the network.

Bandit Level 13 introduces this concept through practical usage of an RSA private key.

---

# SSH Authentication Methods

## Password Authentication

```
Client
   │
Password
   │
Server verifies password
```

Advantages

- Easy to use

Disadvantages

- Password theft
- Brute-force attacks
- Password reuse

---

## Public Key Authentication

```
Private Key
      │
      ▼
Client ─────────► Server
             verifies using
               Public Key
```

Advantages

- Passwordless login
- Strong cryptography
- Resistant to brute-force attacks
- Industry standard

---

# Public Key Cryptography

Every SSH key pair contains:

```
Private Key
```

- Secret
- Never shared
- Stored on client

and

```
Public Key
```

- Shared
- Stored on server
- Used for verification

The server never receives the private key.

---

# Identity Files

The SSH client normally searches for default keys inside:

```
~/.ssh/
```

Examples

```
id_rsa

id_ed25519
```

To explicitly choose a key:

```bash
ssh -i sshkey.private user@host
```

The `-i` option means:

> Identity File

---

# SSH Command Structure

```
ssh [options] user@host
```

Example

```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```

Explanation

```
-i
```

Use specific private key

```
bandit14
```

Target user

```
localhost
```

Target machine

```
-p
```

Port Number

```
2220
```

SSH service port

---

# Why localhost?

Normally SSH connects to another computer.

In Bandit Level 13:

```
bandit13
        │
        ▼
localhost
        │
        ▼
bandit14
```

The SSH connection happens on the **same Linux machine**.

---

# SSH Debugging

Verbose mode helps analyse authentication.

```
-v
```

Basic debugging

```
-vv
```

Detailed debugging

```
-vvv
```

Maximum debugging information

Example

```bash
ssh -vvv -i sshkey.private bandit14@localhost -p 2220
```

---

# Authentication Flow

```
Read configuration

↓

Load identity file

↓

Connect to server

↓

Verify host key

↓

Negotiate encryption

↓

Authenticate

↓

Open shell
```

---

# Linux Permissions

Private keys must remain secret.

Typical permissions

```
600
```

Owner Read + Write

or

```
640
```

Owner Read + Write

Group Read

Permissions should only be modified after understanding the actual issue.

---

# Empty Home Directory

Bandit14 shows:

```
total 0
```

This demonstrates:

An empty home directory does **not** imply an empty Linux system.

Important files often exist elsewhere:

```
/etc

/usr

/var

/proc

/dev
```

---

# Professional Troubleshooting Strategy

Instead of guessing:

```
Observe

↓

Collect Information

↓

Read Logs

↓

Identify Root Cause

↓

Apply Solution

↓

Verify
```

This approach is used by professional security engineers.

---

# Commands Learned

```bash
ssh
```

```bash
ssh -i
```

```bash
ssh -v
```

```bash
ssh -vv
```

```bash
ssh -vvv
```

```bash
cat
```

```bash
chmod
```

```bash
ls
```

```bash
pwd
```

---

# Real World Applications

SSH Public Key Authentication is widely used in:

- Linux Servers
- Cloud Infrastructure
- AWS EC2
- Azure Virtual Machines
- GitHub
- GitLab
- DevOps
- Penetration Testing
- Security Operations
- CTF Competitions

---

# Key Takeaways

✅ SSH supports secure public key authentication.

✅ Private keys remain confidential.

✅ `-i` specifies the identity file.

✅ SSH debugging provides detailed authentication information.

✅ Empty home directories do not imply empty systems.

✅ Professional debugging follows observation before modification.

---

# Related Resources

- OpenSSH Documentation
- Linux Manual Pages (`man ssh`)
- OverTheWire Bandit
- RFC 4252 — SSH Authentication Protocol
