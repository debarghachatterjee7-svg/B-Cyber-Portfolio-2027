# 📘 Notes 08

**Title:** Introduction to SSH Authentication, Linux File Permissions & Secure Remote Access

**Description:**  
These notes summarize the concepts introduced during Day 14 of my cybersecurity learning journey. Today's focus was on Linux file permissions, SSH authentication, private key management, and understanding why secure authentication is used instead of passwords in modern systems. While working through OverTheWire Bandit Level 13, I realized that understanding concepts is more important than simply completing challenges. These notes document today's learning and also identify the concepts that require deeper study before moving forward.

---

# 📅 Date

**18 July 2026**

---

# 🎯 Learning Objective

The objective of today's learning session was to understand the role of Linux file permissions in securing sensitive files while gaining an introductory understanding of SSH authentication. Rather than memorizing commands, today's focus was on understanding the purpose behind Linux security mechanisms and identifying the topics that require deeper theoretical knowledge before continuing practical cybersecurity exercises.

---

# 📖 What is SSH?

SSH stands for **Secure Shell**.

It is a secure network protocol used to remotely connect to another computer through an encrypted communication channel.

Unlike older protocols such as Telnet, SSH encrypts all communication between the client and server, protecting usernames, passwords, commands, and transferred files from attackers.

SSH is widely used by:

- Linux System Administrators
- Cloud Engineers
- Cybersecurity Professionals
- Ethical Hackers
- DevOps Engineers

SSH is one of the most important tools in Linux administration.

---

# 🔑 Password Authentication vs Key Authentication

SSH supports multiple authentication methods.

The two most common methods are:

### Password Authentication

- User enters username.
- User enters password.
- Server verifies password.
- Access is granted.

Advantages:

- Simple
- Easy to use

Disadvantages:

- Passwords can be guessed.
- Passwords can be stolen.
- Vulnerable to brute-force attacks.

---

### Public Key Authentication

Instead of using passwords, SSH can verify the user's identity using a pair of cryptographic keys.

These are:

- Public Key
- Private Key

Advantages:

- Much more secure.
- Difficult to crack.
- Commonly used in professional environments.
- Eliminates password guessing attacks.

---

# 🔐 Linux File Permissions

Linux protects files using permission bits.

Every file has permissions assigned to:

- Owner
- Group
- Others

Permission types include:

- Read (r)
- Write (w)
- Execute (x)

These permissions determine who can access or modify a file.

---

# 📌 Why Private Keys Need Secure Permissions

A private key proves the identity of the user.

If another person gains access to the private key, they may be able to log in as that user.

For this reason, Linux requires private keys to have restrictive permissions.

Example:

```bash
chmod 600 private_key
```

Permission 600 means:

- Owner → Read & Write
- Group → No Access
- Others → No Access

This helps prevent unauthorized access to sensitive credentials.

---

# 🖥️ Linux Commands Learned Today

```bash
chmod
ls -l
ssh
file
cat
mv
rm
```

These commands helped manage files, inspect permissions, and investigate SSH authentication.

---

# 🌍 Real World Applications

Today's concepts are widely used in real-world cybersecurity and system administration.

Examples include:

- Logging into cloud servers.
- Managing Linux servers remotely.
- Secure software deployment.
- Remote server administration.
- Secure file transfer.
- Infrastructure management.
- Penetration testing.
- Capture The Flag (CTF) competitions.

Every cybersecurity professional works with SSH regularly.

---

# 🧠 Important Observations

During today's practical work, I realised that simply copying Linux commands is not enough.

Although I successfully executed several commands, I did not completely understand how SSH internally authenticates users or why certain options are required.

This highlighted an important weakness in my learning approach.

Instead of progressing through OverTheWire quickly, I need to build a strong conceptual foundation first.

---

# ⚠️ Topics Requiring Further Study

The following concepts will be studied in detail before attempting the next OverTheWire level:

- SSH Architecture
- Client and Server Communication
- RSA Cryptography
- Public and Private Keys
- SCP
- SSH Configuration Files
- known_hosts
- authorized_keys
- SSH Authentication Flow
- SSH Options
- Host Verification
- Key Fingerprints

These topics will become the foundation for future Linux and cybersecurity learning.

---

# 💡 Key Learning

Today's biggest learning was that cybersecurity is based on understanding concepts rather than memorizing commands.

A command such as:

```bash
chmod 600 private_key
```

is not important because of its syntax.

It is important because it protects sensitive credentials and prevents unauthorized users from accessing authentication keys.

Understanding **why** Linux behaves this way is more valuable than simply remembering the command.

---

# 📌 Summary

Today's session introduced Linux file permissions and SSH authentication while highlighting the importance of conceptual understanding before solving practical cybersecurity challenges.

Although I have not yet mastered SSH, today's learning helped me identify the exact topics that require deeper study. From tomorrow onwards, every OverTheWire challenge will only be attempted after learning and practicing all of the required concepts in detail.

---

# 🚀 Next Learning Plan

Tomorrow's session will focus on:

- Complete SSH Fundamentals
- Public vs Private Keys
- RSA Basics
- SCP
- SSH Configuration Files
- Linux Permission Management
- Local Ubuntu Practical Experiments
- Revision Quiz
- OverTheWire Bandit only after mastering all concepts

---

# 🏁 Conclusion

Day 14 reinforced one of the most valuable lessons of my cybersecurity journey: **CTFs are not the place to learn concepts—they are the place to apply concepts.** My primary objective is not to complete OverTheWire quickly but to build strong Linux and cybersecurity fundamentals that will help me succeed in the IIT Kanpur BCYBER program and future real-world cybersecurity challenges. By focusing on deep understanding, consistent practice, and thorough documentation, I am building a stronger foundation for long-term success.