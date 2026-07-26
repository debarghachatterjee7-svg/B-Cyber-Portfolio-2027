# 📖 Notes 016 – Netcat (nc), Client–Server Communication & Network Services

**Day:** 022

---

# 🎯 Learning Objectives

After completing these notes, I should be able to:

- Explain what Netcat is.
- Understand client–server communication.
- Identify the purpose of network services.
- Understand ports and localhost.
- Differentiate SSH and Netcat.
- Use basic Netcat commands confidently.
- Understand the networking concepts behind OverTheWire Bandit Level 14.

---

# 🌐 What is Netcat?

**Netcat (nc)** is a command-line networking utility used to create TCP or UDP connections between computers.

It allows a client to send and receive raw data from a network service.

Netcat is commonly called:

> **The Swiss Army Knife of Networking**

because it supports many different networking tasks.

---

# 🖥️ Client–Server Model

Most network communication follows this model.

```text
Client
   │
   │ Request
   ▼
Server

Server
   │
   │ Response
   ▼
Client
```

### Client

A client starts the communication.

Examples:

- Browser
- SSH
- Netcat

---

### Server

A server waits for incoming connections and provides a service.

Examples:

- Web Server
- SSH Server
- DNS Server
- FTP Server

---

# 📡 Network Service

A network service is a program listening on a specific port waiting for clients.

Examples:

| Service | Port |
|----------|-----:|
| SSH | 22 |
| HTTP | 80 |
| HTTPS | 443 |
| DNS | 53 |

Bandit Level 14 runs a service on:

```text
localhost:30000
```

---

# 🏠 localhost

`localhost`

always refers to the current machine.

Equivalent IP:

```text
127.0.0.1
```

It allows communication with services running on the same computer.

---

# 🔢 Ports

Ports identify different network services.

Example:

```text
localhost:22
```

means

SSH running locally.

---

## Privileged Ports

Ports

```text
0–1023
```

are called **privileged ports**.

Only the root user can open services on these ports.

Examples:

- 22
- 53
- 80

Attempting to listen on these ports as a normal user results in:

```text
Permission denied
```

---

# 🔧 Basic Netcat Syntax

```bash
nc HOST PORT
```

Example:

```bash
nc localhost 30000
```

Meaning:

- Start Netcat.
- Connect to localhost.
- Connect to port 30000.

---

# 📋 Useful Netcat Commands

### Help

```bash
nc -h
```

Displays all available options.

---

### Verbose

```bash
nc -v HOST PORT
```

Shows additional connection information.

---

### Listen

```bash
nc -l PORT
```

Starts Netcat as a server listening on the specified port.

---

### Numeric Mode

```bash
nc -n HOST PORT
```

Avoids DNS name resolution.

---

# ⚖️ SSH vs Netcat

| SSH | Netcat |
|------|---------|
| Opens a Linux shell | Does not open a shell |
| Executes Linux commands | Sends raw network data |
| Used for remote administration | Used for network communication |
| Requires authentication | Depends on the service |

---

# 🏴 OverTheWire Bandit Level 14

Official objective:

> Submit the current level password to the service listening on **localhost port 30000**.

This challenge demonstrates:

- TCP communication
- Client–server interaction
- Service authentication

---

# 🐞 Common Mistakes

### Missing space

Incorrect:

```bash
cat/etc/bandit_pass/bandit14
```

Correct:

```bash
cat /etc/bandit_pass/bandit14
```

---

### Confusing `authorized_keys`

`authorized_keys`

contains **public SSH keys**.

It does **not** store account passwords.

---

### Typing after Netcat exits

If the Netcat connection closes, typing text is interpreted by Bash.

Example:

```text
hello
```

becomes

```text
command not found
```

because the shell is active again.

---

# 💡 Key Takeaways

- Netcat is a networking utility, not a shell.
- A client connects to a server.
- Services listen on ports.
- `localhost` refers to the current machine.
- Privileged ports require root privileges.
- Never assume—always verify through experimentation.

---

# 🧠 Revision Questions

1. What is Netcat?
2. Why is Netcat called the Swiss Army Knife of Networking?
3. What is a network service?
4. What is localhost?
5. What is the difference between SSH and Netcat?
6. Why can't normal users listen on port 80?
7. What does `nc localhost 30000` do?
8. What does `authorized_keys` store?
9. Why did Bash return `command not found` after typing `hello`?
10. What networking concept does Bandit Level 14 teach?

---

# 📌 Summary

Today's learning focused on understanding networking beyond commands.

The key lesson was that Netcat enables direct communication with network services, helping build a strong foundation in TCP networking, client–server communication, and practical cybersecurity concepts.