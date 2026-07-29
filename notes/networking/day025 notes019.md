# 📝 Notes 019 — Nmap Fundamentals, Port Enumeration & Network Reconnaissance

**Day:** 025  
**Module:** 06  
**Topic:** Network Reconnaissance using Nmap  
**Category:** Cybersecurity Fundamentals  
**Status:** Completed

---

# 📖 Introduction

Network reconnaissance is the first practical phase of ethical hacking. Before interacting with a target system, an ethical hacker first gathers information to understand what services are available, which ports are exposed, and how the target communicates over a network.

One of the most widely used tools for this purpose is **Nmap (Network Mapper)**. Nmap allows security professionals to identify active hosts, discover open ports, detect running services, and perform basic service enumeration. Rather than attacking a system immediately, reconnaissance focuses on building an accurate understanding of the environment.

---

# 🎯 Learning Objectives

By completing today's study, I aimed to:

- Understand the purpose of reconnaissance.
- Learn how Nmap performs network scanning.
- Differentiate between hosts, ports, and services.
- Interpret Nmap scan results correctly.
- Understand service version detection.
- Learn how professional penetration testers document scan results.

---

# 🌐 What is Network Reconnaissance?

Network reconnaissance is the process of collecting information about a target system before attempting any interaction.

Its purpose is to answer questions such as:

- Is the target online?
- Which ports are accessible?
- Which services are running?
- What software is providing those services?
- Which communication protocols are being used?

Reconnaissance reduces assumptions and enables informed decision-making throughout a security assessment.

---

# 🔍 What is Nmap?

Nmap (Network Mapper) is an open-source network scanning tool used for discovering hosts and services on a computer network.

Common uses include:

- Host discovery
- Port scanning
- Service detection
- Service version detection
- Network inventory
- Security auditing
- Penetration testing reconnaissance

---

# 🖥 Host vs Port vs Service

## Host

A host is any device connected to a network.

Examples:

- Laptop
- Server
- Router
- Raspberry Pi
- Virtual Machine

A host is identified using an IP address.

---

## Port

A port is a logical communication endpoint used by applications.

Ports allow multiple network applications to communicate simultaneously using a single IP address.

Example:

```
192.168.1.10
│
├── Port 22 → SSH
├── Port 80 → HTTP
├── Port 443 → HTTPS
└── Port 3306 → MySQL
```

---

## Service

A service is the application listening on a port.

Examples:

| Port | Service |
|------|----------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 53 | DNS |
| 25 | SMTP |

---

# 📊 Port States

Nmap commonly reports three important states.

## Open

A service is actively listening on the port.

The port accepts network connections.

---

## Closed

No service is currently listening.

The host is reachable but nothing accepts connections on that port.

---

## Filtered

A firewall or filtering device prevents Nmap from determining the actual state of the port.

---

# 🧪 Commands Practiced

## Verify Installation

```bash
nmap --version
```

Purpose:

- Verify installation
- Check software version

---

## Basic Scan

```bash
nmap localhost
```

Purpose:

- Discover open ports
- Identify available services

---

## Scan Specific Port Range

```bash
nmap -p 1-1024 localhost
```

Purpose:

- Limit scanning to selected ports

---

## Service Version Detection

```bash
nmap -sV localhost
```

Purpose:

- Attempt to identify service versions

---

# 📋 Understanding Scan Output

Typical Nmap output contains several important sections.

## Host Status

Example

```
Host is up
```

Indicates that the target machine responded successfully.

---

## Port State

Example

```
22/tcp open ssh
```

Meaning:

- Port Number
- Protocol
- Current State
- Service Name

---

## Closed Ports

Example

```
Not shown: 1000 closed tcp ports
```

Indicates that the scanned ports responded but had no active services.

---

## Scan Summary

Example

```
Nmap done:
```

Provides:

- Number of hosts scanned
- Scan duration
- Completion status

---

# 🔎 Service Detection

Using

```bash
nmap -sV
```

Nmap attempts to identify:

- Application name
- Software version
- Service banner (when available)

This information is useful for understanding the target environment and planning further investigation.

---

# 📈 Why Reconnaissance Matters

Reconnaissance provides the information needed before interacting with a target.

Professional workflow:

```
Target

↓

Host Discovery

↓

Port Scan

↓

Service Detection

↓

Information Analysis

↓

Security Testing
```

Skipping reconnaissance often leads to inefficient or incorrect testing.

---

# 💾 Documenting Results

Professional assessments require proper documentation.

Common reasons to save scan reports:

- Record evidence
- Compare future scans
- Include findings in reports
- Share results with team members
- Maintain assessment history

---

# 📚 Key Concepts Learned

- Network Reconnaissance
- Host Discovery
- Port Enumeration
- Service Enumeration
- Open vs Closed Ports
- Service Detection
- Information Gathering
- Reconnaissance Workflow
- Documentation Best Practices

---

# ⭐ Key Takeaways

- Ethical hacking begins with information gathering.
- Nmap is one of the most important reconnaissance tools.
- Ports identify communication endpoints.
- Services run on ports.
- Closed ports are still valuable information.
- Service detection provides deeper insight than port scanning alone.
- Proper documentation is an essential professional habit.
---

# 📌 Preparation for OverTheWire Bandit Level 16

Bandit Level 16 combines everything learned so far in Linux networking and secure communication. Unlike previous levels where the required port was already known, this challenge requires performing reconnaissance before interacting with the correct service.

The objective is not to guess the correct port but to **discover it systematically**.

---

# 🧠 Concepts Required

Before attempting Bandit Level 16, I should understand:

- Network reconnaissance
- Port scanning
- Service enumeration
- TCP communication
- SSL/TLS communication
- Difference between Netcat and OpenSSL
- Reading Nmap output
- Identifying open ports
- Selecting the correct communication tool

---

# 🔧 Linux Commands to Remember

## Display Nmap Version

```bash
nmap --version
```

Purpose:

Verify that Nmap is installed correctly.

---

## Basic Scan

```bash
nmap localhost
```

Purpose:

Perform a basic scan to identify open ports.

---

## Scan Specific Port Range

```bash
nmap -p 31000-32000 localhost
```

Purpose:

Scan only the required port range.

---

## Service Detection

```bash
nmap -sV localhost
```

Purpose:

Attempt to identify services and versions running on open ports.

---

## Service Detection Within Port Range

```bash
nmap -sV -p 31000-32000 localhost
```

Purpose:

Detect service information only within the required range.

---

# 🔐 Secure Communication Commands

## Netcat

```bash
nc hostname port
```

Purpose:

Used for plain TCP communication.

When to use:

Only if the service does **not** require SSL/TLS.

---

## OpenSSL Client

```bash
openssl s_client -connect hostname:port
```

Purpose:

Establishes a secure TLS connection.

When to use:

When the discovered service speaks SSL/TLS.

---

# 📊 Nmap Output Interpretation

Example

```
PORT     STATE    SERVICE

31518    open     ssl

31519    closed

31520    open     unknown
```

Interpretation

- Open → Service is accepting connections.
- Closed → No service listening.
- Filtered → Firewall or filtering prevents determination.
- Service column provides clues about the protocol.

---

# 🔍 Reconnaissance Workflow

Professional workflow:

```
Target

↓

Scan Host

↓

Identify Open Ports

↓

Identify Running Services

↓

Determine Communication Protocol

↓

Select Appropriate Tool

↓

Connect

↓

Authenticate
```

This workflow avoids unnecessary guessing and reflects real-world penetration testing methodology.

---

# ⚠ Netcat vs OpenSSL

| Netcat | OpenSSL |
|---------|----------|
| Plain TCP | SSL/TLS |
| No encryption | Encrypted communication |
| No handshake | TLS handshake required |
| Used for standard services | Used for secure services |

Choosing the wrong tool often results in failed communication.

---

# 📁 Nmap Report Generation

Save normal report

```bash
nmap localhost -oN report.txt
```

Save XML report

```bash
nmap localhost -oX report.xml
```

Save all formats

```bash
nmap localhost -oA report
```

Professional penetration testers always save reconnaissance results for later analysis and documentation.

---

# 📚 Important Nmap Options

| Option | Purpose |
|---------|----------|
| `-p` | Scan selected ports |
| `-sV` | Detect service versions |
| `-v` | Verbose output |
| `-vv` | Extra verbose output |
| `-T4` | Faster scan |
| `-oN` | Save normal report |
| `-oX` | Save XML report |
| `-oA` | Save all report formats |

---

# 💡 Key Revision Points

- An IP identifies a host.
- A port identifies a communication endpoint.
- A service listens on a port.
- Open does **not** mean vulnerable.
- Reconnaissance always comes before exploitation.
- Service detection provides additional intelligence.
- SSL/TLS services require OpenSSL.
- Plain TCP services can use Netcat.
- Always interpret scan results before attempting connections.

---

# 🎯 Tomorrow's Mission

Bandit Level 16 will test my ability to:

- Perform reconnaissance independently.
- Interpret Nmap results correctly.
- Distinguish between TCP and SSL/TLS services.
- Select the appropriate communication tool.
- Apply reconnaissance methodology instead of guessing.

The goal is to think like an ethical hacker: **discover → analyze → interact**, rather than **guess → connect**.

---

# 🔄 Revision Checklist

- [x] Understand reconnaissance
- [x] Understand Nmap
- [x] Know host vs port vs service
- [x] Identify port states
- [x] Perform basic scan
- [x] Scan selected ports
- [x] Perform service detection
- [x] Interpret Nmap output
- [x] Understand professional documentation

---

# 🏁 Conclusion

Today's learning established a strong foundation in network reconnaissance. Rather than focusing on exploitation, the emphasis was placed on understanding how security professionals first discover and analyze network services before making any security decisions.

Mastering these fundamentals will support future learning in networking, penetration testing, CTF competitions, and advanced ethical hacking techniques.
