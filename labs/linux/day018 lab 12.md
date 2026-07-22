# 🧪 Lab 012 — SSH Key Generation, Fingerprint Verification & Linux SSH Directory Exploration

**Day:** 018  
**Date:** 22 July 2026  
**Status:** ✅ Completed

---

# 🎯 Objective

The objective of this lab was to understand how SSH generates cryptographic key pairs, how fingerprints uniquely identify keys, how Randomart provides a visual representation of fingerprints, and how Linux stores SSH-related files inside the `.ssh` directory.

---

# Environment

Operating System:
Ubuntu 24.04 (WSL)

Shell:
Bash

Tool Used:
OpenSSH

---

# Practical Tasks Performed

## Task 1 — Verify OpenSSH Installation

Command

```bash
ssh -V
```

Result

Verified that OpenSSH was successfully installed and operational.

---

## Task 2 — Create Day018 Workspace

Commands

```bash
mkdir day018
cd day018
pwd
```

Result

Created a dedicated working directory for today's practical exercises.

---

## Task 3 — Explore Home Directory

Command

```bash
ls -la
```

Observation

Verified the presence of the hidden `.ssh` directory.

---

## Task 4 — Navigate to SSH Directory

Command

```bash
cd ~/.ssh
ls -la
```

Observation

Observed the existing SSH files including previously generated keys and trusted host records.

---

## Task 5 — Generate RSA Key Pair

Command

```bash
ssh-keygen -t rsa -b 3072
```

Observation

Successfully generated a new RSA 3072-bit key pair.

Generated files:

- id_rsa
- id_rsa.pub

---

## Task 6 — Verify RSA Fingerprint

Command

```bash
ssh-keygen -lf id_rsa.pub
```

Observation

Displayed:

- Key size
- SHA256 fingerprint
- RSA algorithm

---

## Task 7 — Display RSA Randomart

Command

```bash
ssh-keygen -lvf id_rsa.pub
```

Observation

Displayed the graphical Randomart representation corresponding to the RSA fingerprint.

---

## Task 8 — Generate ED25519 Key Pair

Command

```bash
ssh-keygen -t ed25519
```

Saved as

```text
id_ed25519
```

Generated files

- id_ed25519
- id_ed25519.pub

---

## Task 9 — Verify ED25519 Fingerprint

Command

```bash
ssh-keygen -lf id_ed25519.pub
```

Observation

Displayed the SHA256 fingerprint for the generated ED25519 key.

---

## Task 10 — Display ED25519 Randomart

Command

```bash
ssh-keygen -lvf id_ed25519.pub
```

Observation

Displayed the Randomart associated with the ED25519 fingerprint.

---

## Task 11 — Inspect SSH Directory

Command

```bash
ls -la
```

Observation

Verified the presence of:

- id_rsa
- id_rsa.pub
- id_ed25519
- id_ed25519.pub
- known_hosts

---

## Task 12 — Examine known_hosts

Command

```bash
cat ~/.ssh/known_hosts
```

Observation

Viewed stored host keys representing previously trusted SSH servers.

---

# Skills Practiced

- OpenSSH verification
- Linux directory navigation
- SSH key generation
- RSA cryptography
- ED25519 cryptography
- Fingerprint verification
- Randomart visualization
- SSH directory inspection
- Host key verification

---

# Files Generated

| File | Purpose |
|------|---------|
| id_rsa | RSA Private Key |
| id_rsa.pub | RSA Public Key |
| id_ed25519 | ED25519 Private Key |
| id_ed25519.pub | ED25519 Public Key |
| known_hosts | Stores trusted SSH server identities |

---

# Commands Practiced

```bash
ssh -V
mkdir
cd
pwd
ls -la
ssh-keygen -t rsa -b 3072
ssh-keygen -t ed25519
ssh-keygen -lf
ssh-keygen -lvf
cat
```

---

# Key Learning Outcomes

- Successfully generated two different SSH key types.
- Learned the practical difference between RSA and ED25519.
- Understood how SSH fingerprints uniquely identify keys.
- Visualized fingerprints using Randomart.
- Explored the Linux SSH configuration directory.
- Identified the purpose of trusted host records.

---

# Conclusion

This lab provided hands-on experience with modern SSH authentication mechanisms by generating RSA and ED25519 key pairs, verifying their identities through fingerprints and Randomart, and examining how Linux organizes SSH-related files. The practical exercises strengthened the understanding of asymmetric cryptography, secure authentication, and SSH key management, providing a solid foundation for future Linux administration and cybersecurity tasks.