# 📘 Notes 022 — Restricted Shells, SSH Remote Command Execution & Bandit Level 18

> **Module:** Linux Shell Internals & SSH
>
> **Focus:** Understanding Linux behaviour instead of memorising commands.

![Linux](https://img.shields.io/badge/Linux-Bash-FCC624?logo=linux&logoColor=black)
![SSH](https://img.shields.io/badge/OpenSSH-Remote%20Execution-green)
![Bandit](https://img.shields.io/badge/OverTheWire-Level%2018-blue)
![Notes](https://img.shields.io/badge/Notes-022-orange)

---

# 🎯 Learning Objectives

Today focused on understanding **how Linux behaves internally** rather than learning new commands.

The primary concepts included:

- Restricted shell environments
- Interactive vs non-interactive shell sessions
- SSH remote command execution
- Bash startup files
- Linux environment variables
- Practical application through Bandit Level 18

---

# 📚 New Concepts Learned

---

## 1️⃣ Restricted Shell

A restricted shell limits the operations a user can perform while still allowing controlled access to specific resources.

### Purpose

- Prevent accidental modifications
- Limit user privileges
- Reduce attack surface
- Enforce least privilege

---

## 2️⃣ Interactive vs Non-Interactive Shell

### Interactive Shell

Created when a user logs into a system normally.

Examples:

```bash
ssh user@host
```

Loads startup files such as:

- `.bashrc`
- `.profile`
- `.bash_profile`

---

### Non-Interactive Shell

Runs a command directly without creating a normal shell session.

Example:

```bash
ssh user@host "command"
```

Useful for:

- Automation
- Remote administration
- Scheduled tasks
- Bypassing interactive shell restrictions

---

## 3️⃣ Bash Startup Files

### `.bashrc`

Executed whenever an interactive Bash shell starts.

Common uses:

- Aliases
- Environment variables
- Prompt customization
- Shell configuration

---

## 4️⃣ SSH Remote Command Execution

SSH is capable of executing a command immediately after successful authentication.

General syntax:

```bash
ssh username@host "command"
```

This avoids creating a fully interactive shell.

---

## 5️⃣ Environment Variables

Environment variables provide configuration information for Linux processes.

Examples:

| Variable | Purpose |
|----------|----------|
| HOME | User home directory |
| USER | Current username |
| SHELL | Default login shell |
| PATH | Directories searched for executable commands |
| PWD | Current working directory |

---

# 🌍 Real World Applications

---

## System Administration

Administrators remotely execute commands on thousands of servers without opening interactive sessions.

Example:

- Restart services
- Read log files
- Deploy updates

---

## DevOps

Automation pipelines execute commands remotely over SSH.

Examples:

- CI/CD deployments
- Configuration management
- Automated backups

---

## Ethical Hacking

Penetration testers often gain limited shell access.

Understanding shell behaviour helps determine:

- Login restrictions
- Available execution methods
- Environment configuration
- Privilege escalation opportunities

---

## Incident Response

Security teams frequently connect remotely to compromised systems using single SSH commands to collect forensic evidence without disturbing running processes.

---

# 🔁 Revision Commands (Bandit Level 19 Preparation)

| Command | Purpose |
|---------|----------|
| `ssh` | Secure remote login and remote command execution |
| `cat` | Display file contents |
| `ls` | List directory contents |
| `pwd` | Show current directory |
| `echo` | Print variables or text |
| `whoami` | Display current username |
| `chmod` | Modify file permissions |
| `file` | Identify file type |
| `find` | Search for files/directories |
| `grep` | Search text using patterns |
| `sort` | Arrange text alphabetically |
| `uniq` | Remove adjacent duplicate lines |
| `diff` | Compare text files line-by-line |
| `cmp` | Compare files byte-by-byte |
| `comm` | Compare sorted files |
| `wc` | Count lines, words and bytes |
| `tr` | Translate or replace characters |

---

# 👨‍🏫 Professor Questions & Answers

---

## Q1. Why are restricted shells used?

**Answer**

Restricted shells enforce security by limiting user capabilities. They reduce the risk of unauthorized actions and follow the Principle of Least Privilege.

---

## Q2. Why did remote command execution work even though `.bashrc` was modified?

**Answer**

Because SSH executed the requested command directly after authentication without creating a normal interactive Bash session. Since `.bashrc` is loaded during interactive shell startup, it never had the opportunity to terminate the session.

---

## Q3. Why are shell startup files important?

**Answer**

They define the behaviour of user login sessions, including aliases, environment variables, prompts, PATH configuration and startup scripts.

---

## Q4. Why is understanding Linux behaviour more important than memorising commands?

**Answer**

Commands only solve known problems. Understanding system behaviour allows a security professional to analyse unfamiliar situations and develop logical solutions.

---

## Q5. What was the real lesson behind Bandit Level 18?

**Answer**

The challenge tested conceptual understanding of Linux shell initialization rather than command knowledge. The solution came from analysing how SSH behaves instead of searching for a bypass.

---

# ⭐ Key Takeaways

- Linux behaviour is often more important than Linux commands.
- SSH supports both interactive and non-interactive execution.
- `.bashrc` only affects interactive Bash sessions.
- Understanding system architecture leads to better problem-solving.
- Cybersecurity requires analysing system behaviour, not simply remembering syntax.

---

# 🚀 Next Focus

Prepare for **Bandit Level 19** by strengthening understanding of:

- Linux permissions
- Executable files
- User identity
- SSH execution flow
- File ownership concepts
- Restricted execution environments

---

> **"Commands can be memorised. System behaviour must be understood."**