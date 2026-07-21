# Day 17 Lab – Exploring SSH Fundamentals, Keys, Known Hosts & File Identification

## Date
21 July 2026

---

# Objective

The objective of today's lab was to understand the SSH environment already present on my Linux system. Instead of modifying SSH configurations, I explored the existing SSH files and related them to the theoretical concepts learned during today's lesson.

---

# Environment

Operating System:
Ubuntu 24.04 LTS (WSL)

Terminal:
Bash

Commands Used:

- ssh-keygen
- ls
- cat
- file

---

# Experiment 1 – Exploring the SSH Directory

## Command

```bash
ls -la ~/.ssh
```

### Purpose

Display every file present inside the hidden SSH directory.

### Observation

The directory contained:

- id_ed25519
- id_ed25519.pub
- known_hosts
- known_hosts.old

The `authorized_keys` file was not present because this machine has not been configured as an SSH server.

---

# Experiment 2 – Viewing the Public Key

## Command

```bash
cat ~/.ssh/id_ed25519.pub
```

### Purpose

Display the public key stored on the system.

### Observation

The key started with:

```
ssh-ed25519
```

followed by a long Base64 encoded string and finally my username and hostname.

### Answers

**1. Why is this key safe to share?**

Because it is the public key. It is designed to be copied to servers for authentication.

**2. Which algorithm is being used?**

ED25519

**3. Why is the file readable?**

Because a public key is stored in text format.

---

# Experiment 3 – Exploring known_hosts

## Command

```bash
cat ~/.ssh/known_hosts
```

### Purpose

Observe trusted server information stored by SSH.

### Observation

The file contained multiple entries representing servers that my computer has previously connected to.

These entries were completely different from my public key.

### Answers

**1. Who created this file?**

SSH automatically created and updated it.

**2. What information does it contain?**

Public host keys (fingerprints) of trusted servers.

**3. Why does SSH maintain this file?**

To verify the identity of servers during future connections and prevent man-in-the-middle attacks.

---

# Experiment 4 – Identifying the Private Key

## Command

```bash
file ~/.ssh/id_ed25519
```

### Purpose

Identify the actual type of the private key.

### Observation

Linux identified the file as:

```
OpenSSH private key
```

### Answers

**1. Is this recognised as an OpenSSH private key?**

Yes.

**2. Why should this file never be shared?**

Because anyone possessing the private key can authenticate as me if the corresponding public key is authorized.

---

# Experiment 5 – Identifying the Public Key

## Command

```bash
file ~/.ssh/id_ed25519.pub
```

### Purpose

Identify the public key.

### Observation

Linux recognised it as:

```
OpenSSH ED25519 public key
```

### Answers

**1. Why are the outputs different?**

One file is a private key while the other is a public key.

**2. Which file should be copied to a server?**

The public key (`id_ed25519.pub`).

---

# Experiment 6 – Identifying known_hosts

## Command

```bash
file ~/.ssh/known_hosts
```

### Purpose

Understand how Linux identifies the known_hosts file.

### Observation

Linux recognised it as:

```
ASCII text
```

### Answers

**1. Why is this file stored as plain text?**

Because SSH only needs to read server information stored inside it.

**2. What kind of information is saved inside it?**

Public host keys and fingerprints of trusted remote servers.

---

# Theory Reinforcement

## Question 1

Difference between Public Key and Private Key.

**Answer**

The public key is shared with servers and is used for verification. The private key remains secret on the user's machine and is used to prove identity during authentication.

---

## Question 2

Difference between authorized_keys and known_hosts.

**Answer**

`authorized_keys` stores public keys of users allowed to access a server.

`known_hosts` stores fingerprints of servers trusted by the client.

---

## Question 3

Explain the SSH authentication flow.

**Answer**

The client requests access to a server. The server sends a challenge. The client signs the challenge using its private key. The server verifies the signature using the stored public key. If verification succeeds, access is granted.

---

## Question 4

What is an SSH fingerprint?

**Answer**

A fingerprint is a short cryptographic identifier generated from an SSH key. It allows users to compare keys easily instead of comparing the complete key.

---

## Question 5

Why are fingerprints generated instead of comparing complete keys?

**Answer**

Complete keys are very long. Fingerprints are much shorter and easier to compare while still uniquely representing the original key.

---

## Question 6

Explain the purpose of SHA-256 in SSH.

**Answer**

SHA-256 generates a secure fingerprint from the SSH key. It allows quick and reliable verification of key identity.

---

## Question 7

What is RandomArt?

**Answer**

RandomArt is an ASCII visual representation of an SSH fingerprint. It helps humans visually compare keys.

---

## Question 8

Why does Linux identify files using the file command instead of relying only on extensions?

**Answer**

Linux checks the actual contents of a file rather than its extension, making file identification more reliable and secure.

---

# Skills Practised

- Explored the hidden SSH directory.
- Examined SSH key files.
- Distinguished between public and private keys.
- Observed trusted server records.
- Used the `file` command to identify file types.
- Connected practical observations with SSH theory.

---

# Challenges Faced

- Initially confused the private key with the public key.
- Accidentally attempted to read the `.ssh` directory instead of the files inside it.
- Understood that Linux paths must point to files rather than directories when using `cat`.

---

# Key Learnings

- SSH stores important authentication information inside the hidden `.ssh` directory.
- Public keys can be shared safely, but private keys must remain secret.
- `known_hosts` stores trusted server identities.
- The `file` command identifies files based on their content rather than extensions.
- SSH authentication depends on cryptography rather than simple passwords.

---

# Reflection

Today's practical session focused on observation rather than configuration. I explored the existing SSH environment and verified the concepts learned during today's theory class. I now understand where SSH stores keys, how Linux identifies these files, and the difference between trusting users and trusting servers. This practical has prepared me to learn advanced `ssh-keygen` options and continue with the next stage of the roadmap.