# 📘 Notes 023 — Linux User Identity, Environment Variables & SUID Fundamentals

> **Day:** 029
>
> **Topic:** Linux User Identity, Environment Variables & Secure Privilege Delegation
>
> **Status:** ✅ Completed

![Linux](https://img.shields.io/badge/Linux-Bash-FCC624?logo=linux&logoColor=black)
![Security](https://img.shields.io/badge/Cybersecurity-Linux-blue)
![Notes](https://img.shields.io/badge/Notes-023-success)

---

# 📚 Today's Concepts

---

# 1️⃣ Linux User Identity

Linux is a **multi-user operating system**, meaning multiple users can exist on the same machine while maintaining separate permissions, files, and execution privileges.

Each user is internally identified using:

- Username
- UID (User ID)
- GID (Group ID)
- Group Membership

Although users remember usernames, Linux primarily trusts the **UID** when enforcing permissions.

---

## Why is this Important?

Understanding user identity is essential because every permission decision inside Linux depends on **who** is executing a command.

Without user identification:

- File permissions could not be enforced.
- System resources could not be protected.
- Multi-user environments would not be secure.

---

## Real-World Applications

- Linux System Administration
- Enterprise Servers
- Cloud Infrastructure
- Docker Containers
- Cybersecurity Assessments
- Digital Forensics
- Privilege Escalation Analysis

---

# 2️⃣ UID (User ID)

A **UID** is a unique numerical identifier assigned to every Linux user.

Linux checks the UID whenever a process attempts to access a file or resource.

Example:

```
uid=1000(user)
```

Even if a username changes, the UID remains the true system identity.

---

# 3️⃣ GID (Group ID)

Every Linux user belongs to one or more groups.

Groups simplify permission management.

Instead of granting permissions individually, administrators grant permissions to entire groups.

---

## Real-World Applications

Used extensively in:

- Corporate Networks
- Shared Development Servers
- University Computer Labs
- Cloud Virtual Machines

---

# 4️⃣ Environment Variables

Environment variables store information required by programs during execution.

Examples include:

- Current user
- Home directory
- Current shell
- Executable search paths

Every program launched from the shell inherits these values.

---

## Why are Environment Variables Important?

They allow software to:

- Locate executables
- Store configuration
- Find user directories
- Determine execution behaviour

Without environment variables, software portability would be significantly reduced.

---

## Real-World Applications

- Docker Containers
- GitHub Actions
- CI/CD Pipelines
- Python Development
- Cloud Deployments
- Secret Management
- Configuration Automation

---

# 5️⃣ PATH Variable

The PATH variable tells Linux where to search for executable programs.

When a command such as:

```
ls
```

is executed, Linux searches every directory listed inside PATH until it finds the executable.

---

## Importance

Incorrect PATH configuration may:

- Prevent commands from executing.
- Execute malicious programs before legitimate ones.
- Cause deployment failures.

---

## Real-World Applications

- DevOps
- Software Development
- Linux Administration
- Penetration Testing

---

# 6️⃣ SUID (Set User ID)

SUID allows an executable to temporarily run with the permissions of its owner instead of the user executing it.

This mechanism enables controlled privilege delegation.

Today's Bandit challenge demonstrated this behaviour through the executable:

```
bandit20-do
```

Rather than changing users, the executable temporarily gained the permissions of **bandit20**, allowing controlled access to protected resources.

---

## Why Does Linux Use SUID?

Certain administrative operations require elevated privileges while still allowing ordinary users to execute them safely.

Examples include:

- Password management
- User authentication
- Controlled system utilities

---

## Cybersecurity Relevance

Misconfigured SUID binaries are one of the most common privilege escalation vectors during Linux penetration testing.

Understanding SUID behaviour is therefore an essential cybersecurity skill.

---

# 🌍 Practical Applications

Today's concepts are directly applicable to:

- Linux Administration
- SOC Operations
- Digital Forensics
- Privilege Escalation Audits
- Penetration Testing
- Cloud Security
- Server Hardening
- Secure Software Development

---

# 🔄 Command Revision

| Command | Purpose |
|----------|---------|
| `pwd` | Display current working directory. |
| `ls` | List directory contents. |
| `cd` | Change working directory. |
| `cat` | Display file contents. |
| `head` | View first lines of a file. |
| `tail` | View last lines of a file. |
| `grep` | Search text using patterns. |
| `find` | Search files and directories. |
| `sort` | Sort text alphabetically. |
| `uniq` | Remove adjacent duplicate lines. |
| `diff` | Compare two files line by line. |
| `cmp` | Compare two files byte by byte. |
| `comm` | Compare two sorted files. |
| `wc` | Count lines, words and bytes. |
| `tr` | Translate or replace characters. |
| `ssh` | Secure remote login and command execution. |
| `openssl s_client` | Test SSL/TLS services. |
| `nmap` | Network discovery and port scanning. |
| `whoami` | Display current username. |
| `id` | Display UID, GID and group information. |
| `env` | Display all environment variables. |
| `printenv` | Display environment variables or a specific variable. |
| `echo` | Print text or variable values. |
| `file` | Identify the type of a file or executable. |

---

# 🎯 Preparation for Bandit Level 20

Before attempting Level 20, ensure you understand:

- SSH login
- User identity
- UID & GID
- Linux permissions
- SUID concept
- Environment variables
- PATH
- File inspection
- Executable identification using `file`

No additional commands are required beyond your current knowledge.

---

# 👨‍🏫 Professor Questions & Answers

## Q1. Why is UID more important than the username?

Linux internally trusts the UID for permission checks because usernames can be changed while UIDs remain unique.

---

## Q2. Why is PATH important?

PATH determines where Linux searches for executable programs.

---

## Q3. Why are Linux groups used?

Groups simplify permission management by allowing permissions to be assigned collectively.

---

## Q4. Why should administrators audit SUID programs?

Misconfigured SUID executables may unintentionally allow privilege escalation.

---

## Q5. Why should cybersecurity professionals inspect environment variables?

Environment variables reveal execution context, user information, software configuration, and potential security weaknesses.

---

# 💡 Key Takeaway

Today's learning was less about memorising commands and more about understanding **how Linux identifies users, configures execution environments, and securely delegates privileges**.

This knowledge forms the foundation for future topics including privilege escalation, process security, Linux internals, and advanced penetration testing.