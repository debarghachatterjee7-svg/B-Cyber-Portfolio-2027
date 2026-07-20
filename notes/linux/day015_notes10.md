# Day 16 Notes — SSH Fundamentals & Secure Authentication

**Date:** 20 July 2026

**Topic:** Secure Shell (SSH), Public Key Authentication, Linux File Permissions, SSH Directory Structure

---

# 🎯 Learning Objective

The purpose of today's lesson was to build a strong theoretical understanding of Secure Shell (SSH), one of the most important technologies used in Linux administration and cybersecurity.

Instead of learning only commands, today's focus was understanding how SSH works, why it exists, how authentication is performed securely, and how Linux protects authentication credentials.

---

# What is SSH?

SSH (Secure Shell) is a cryptographic network protocol used to securely connect one computer to another over an insecure network.

It provides:

- Secure Remote Login
- Secure Command Execution
- Secure File Transfer
- Encrypted Communication
- Secure System Administration

SSH has become the standard protocol for managing Linux servers, cloud machines, routers, switches, IoT devices, and many other systems.

---

# Why Was SSH Created?

Before SSH, administrators commonly used **Telnet**.

Telnet transmitted all communication in plain text.

This meant that:

- Passwords could be intercepted.
- Commands could be monitored.
- Sensitive information could be stolen.

SSH solved this problem by encrypting all communication between the client and the server.

---

# Client–Server Architecture

SSH follows a Client–Server model.

### SSH Client

The computer initiating the connection.

Examples:

- Personal laptop
- Desktop computer

### SSH Server

The remote machine accepting connections.

Examples:

- Linux Server
- Cloud VPS
- Raspberry Pi
- Remote Workstation

---

# SSH Authentication Methods

SSH supports two primary authentication methods.

## 1. Password Authentication

The client sends a username.

The server requests the password.

The server verifies the password.

If correct, access is granted.

Although secure because the communication is encrypted, passwords can still be guessed, reused, or stolen.

---

## 2. Public Key Authentication

Instead of passwords, SSH uses a pair of mathematically related keys.

These are:

- Public Key
- Private Key

The private key remains only with the user.

The public key is stored on the remote server.

This method is considered more secure than password authentication.

---

# Public Key

The public key is designed to be shared.

It is uploaded to servers where authentication is required.

Sharing the public key does **not** compromise security.

Typical filename:

```text
id_ed25519.pub
```

---

# Private Key

The private key is secret.

It must never be shared.

Anyone possessing the private key can authenticate as its owner.

Typical filename:

```text
id_ed25519
```

---

# SSH Key Pair

An SSH key pair consists of:

1. Public Key
2. Private Key

These two keys are mathematically related.

Data encrypted or verified using one key can only be correctly processed using the corresponding pair.

---

# The `.ssh` Directory

Linux stores SSH configuration files inside:

```text
~/.ssh
```

This directory usually contains:

- id_ed25519
- id_ed25519.pub
- known_hosts
- known_hosts.old
- authorized_keys (on servers)

---

# id_ed25519

Private authentication key.

Characteristics:

- Secret
- Never shared
- Protected by strict permissions

---

# id_ed25519.pub

Public authentication key.

Characteristics:

- Safe to share
- Uploaded to remote servers
- Used during authentication

---

# known_hosts

Stores fingerprints of SSH servers that have previously been trusted.

Its purpose is to prevent Man-in-the-Middle (MITM) attacks.

When connecting to a server for the first time, SSH asks whether the host should be trusted.

If accepted, its fingerprint is stored here.

---

# known_hosts.old

Backup of the previous `known_hosts` file.

Automatically created by SSH in certain situations.

---

# SSH Key Generation

SSH keys are generated using:

```bash
ssh-keygen
```

Modern versions of OpenSSH generate **Ed25519** keys by default.

---

# Ed25519

Ed25519 is a modern public-key algorithm.

Advantages:

- Fast
- Small key size
- Strong security
- Efficient verification
- Recommended by modern OpenSSH

Although RSA is still widely used, Ed25519 is now the default choice for most systems.

---

# Linux File Permissions

Linux protects sensitive files using permissions.

Permissions are divided into:

- Owner
- Group
- Others

Each category can receive:

- Read (r)
- Write (w)
- Execute (x)

---

# SSH File Permissions

Typical permissions:

Private Key:

```text
-rw-------
```

Equivalent numeric permission:

```text
600
```

Meaning:

Owner:

- Read
- Write

Group:

- No access

Others:

- No access

---

Public Key:

```text
-rw-r--r--
```

Equivalent numeric permission:

```text
644
```

Meaning:

Owner:

- Read
- Write

Group:

- Read

Others:

- Read

---

# Why Private Keys Need Permission 600

If other users can read the private key, they could impersonate the owner.

SSH therefore requires restrictive permissions.

If permissions are too open, SSH may refuse to use the key.

---

# Symbolic vs Numeric Permissions

Linux displays permissions in two forms.

### Symbolic

Example:

```text
-rw-------
```

### Numeric

Example:

```text
600
```

Conversion:

- Read = 4
- Write = 2
- Execute = 1

Example:

rw-

4 + 2

=

6

---

# Commands Learned Today

```bash
ssh-keygen

pwd

mkdir

cd

ls -la

ls -l
```

---

# Key Takeaways

- SSH is the standard protocol for secure remote communication.
- SSH replaced insecure protocols like Telnet.
- SSH supports password and public-key authentication.
- Public keys are shared.
- Private keys must remain secret.
- SSH stores configuration files inside the `.ssh` directory.
- Linux protects private keys using restrictive permissions.
- Ed25519 is the default key algorithm in modern OpenSSH.
- Understanding concepts is more valuable than memorizing commands.

---

# Topics Scheduled for Next Session

- SSH Key Fingerprints
- `ssh-keygen -lf`
- `authorized_keys`
- Host Verification
- `known_hosts` in detail
- SSH Authentication Workflow
- Reading SSH Public Keys
- Linux `file` Command
- Preparing for OverTheWire Bandit Level 14

---

# Final Summary

Today's lesson established the theoretical foundation of SSH by explaining why it exists, how secure authentication works, the role of public and private keys, Linux permission models, and the organization of SSH configuration files. Rather than focusing on completing a CTF challenge, today's objective was to understand the principles that make SSH one of the most widely used security technologies in modern computing. These concepts will support future learning in Linux administration, cloud computing, penetration testing, and cybersecurity.