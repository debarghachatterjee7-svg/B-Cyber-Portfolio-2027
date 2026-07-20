# Day 16 Lab — SSH Key Generation & Linux File Permission Investigation

**Lab Number:** 10

**Date:** 20 July 2026

**Topic:** SSH Key Generation, SSH Directory Structure, Linux File Permissions, Secure Authentication Foundations

---

# 🎯 Lab Objective

The objective of today's lab was to gain practical experience with Secure Shell (SSH) by generating a new SSH key pair, understanding the purpose of the `.ssh` directory, investigating generated files, analysing Linux file permissions, and understanding why private keys require strict protection.

Instead of simply generating keys, the lab focused on understanding how Linux stores authentication credentials and how secure authentication is implemented at the operating system level.

---

# 📚 Theory Before Practical

SSH (Secure Shell) is the standard protocol used to securely connect to remote Linux systems.

Unlike Telnet, SSH encrypts all communication between the client and the server.

SSH supports two authentication methods:

- Password Authentication
- Public Key Authentication

Today's lab focused entirely on Public Key Authentication.

---

# 🧪 Lab Environment

Operating System:

Ubuntu (WSL)

Terminal:

Bash

Working Directory:

```bash
cd ~
```

Lab Directory:

```bash
mkdir ssh_lab_day16
cd ssh_lab_day16
```

---

# Practical 1 — Verify Current Working Directory

Command:

```bash
pwd
```

Purpose:

Verify the current working directory before creating SSH files.

Observation:

Linux displayed the absolute path of the current directory.

---

# Practical 2 — Explore the SSH Configuration Directory

Command:

```bash
ls -la ~/.ssh
```

Purpose:

Inspect the SSH configuration directory and identify existing SSH-related files.

Observation:

Existing files included:

- known_hosts
- known_hosts.old

Understanding:

The `.ssh` directory stores SSH configuration files, authentication keys, and trusted host information.

---

# Practical 3 — Generate a New SSH Key Pair

Command:

```bash
ssh-keygen
```

Observation:

Linux generated an Ed25519 SSH key pair.

Important observations:

- Default algorithm was Ed25519.
- Linux suggested a default save location.
- A private key was generated.
- A public key was generated.
- A fingerprint was displayed.
- A randomart image was generated.

Understanding:

The private key remains with the client.

The public key is shared with remote servers.

---

# Practical 4 — Verify Generated Files

Command:

```bash
ls -la ~/.ssh
```

Observation:

New files appeared:

- id_ed25519
- id_ed25519.pub

Understanding:

The private key and public key were successfully created.

---

# Practical 5 — Investigate Linux Permissions

Command:

```bash
ls -l ~/.ssh
```

Observation:

The private key displayed:

```text
-rw-------
```

The public key displayed:

```text
-rw-r--r--
```

Understanding:

Linux protects private keys by allowing access only to the owner.

Public keys can safely be shared.

---

# Practical 6 — Decode Symbolic Permissions

Observation:

Private key:

```text
rw-------
```

Equivalent:

Owner:

Read

Write

Group:

No permissions

Others:

No permissions

Numeric equivalent:

600

---

Public key:

```text
rw-r--r--
```

Equivalent:

Owner:

Read

Write

Group:

Read

Others:

Read

Numeric equivalent:

644

---

# Practical 7 — Understanding the .ssh Directory

Files investigated:

- id_ed25519
- id_ed25519.pub
- known_hosts
- known_hosts.old

Understanding:

id_ed25519

Private authentication key.

Never shared.

---

id_ed25519.pub

Public authentication key.

Shared with servers.

---

known_hosts

Stores fingerprints of trusted SSH servers.

---

known_hosts.old

Backup created automatically by SSH.

---

# Mistakes Encountered

Initially, a custom filename was provided while generating the SSH key.

As a result:

The key was saved in the current directory instead of the default `.ssh` directory.

This caused confusion when searching for `id_rsa`.

Correction:

Generated a new key pair using the default location.

Lesson learned:

Accept the default save location unless there is a specific reason to use another path.

---

# Key Observations

Linux automatically generated an Ed25519 key pair.

Private keys must never be shared.

Public keys are designed to be distributed.

SSH automatically protects private keys using restrictive permissions.

Linux represents permissions symbolically, which can be converted into numeric notation.

The `.ssh` directory acts as the central storage location for SSH authentication files.

---

# Commands Practised Today

```bash
pwd

mkdir

cd

ls -la

ls -l

ssh-keygen
```

---

# Skills Developed

✅ Creating SSH Key Pairs

✅ Exploring the SSH Directory

✅ Understanding Public vs Private Keys

✅ Reading Linux File Permissions

✅ Converting Symbolic Permissions to Numeric Permissions

✅ Understanding Secure Authentication Storage

---

# Conclusion

Today's lab established the practical foundation required for SSH authentication. Instead of simply generating a key pair, the exercises focused on understanding where SSH stores authentication data, why Linux protects private keys using strict permissions, and how the `.ssh` directory is organised.

The knowledge gained today forms the basis for upcoming topics including key fingerprints, `authorized_keys`, host verification, and complete SSH authentication workflows.