# 📘 Notes 026 — Linux Revision, Process Management & System Operations

> **Notes Number:** 026  
> **Day:** 032  
> **Topic:** Complete Linux Revision & Process Management

---

# 🎯 Objective

Today's session was dedicated entirely to revising everything learned during the first month of Linux and cybersecurity training.

Instead of introducing many new commands, the goal was to strengthen previously learned concepts so they become natural before progressing further into cybersecurity.

Revision is extremely important because Linux commands are rarely used individually. Real cybersecurity work combines many commands together to solve complex problems.

---

# 📚 Topics Revised

Today's revision included:

- Linux File System
- File Management
- Text Processing
- Searching
- Networking Commands
- Linux Processes
- Shell Operators
- Compression & Archives
- Background Jobs
- Error Handling
- Process Monitoring
- `/proc` Filesystem

---

# 🧠 Concepts Revised

## Linux Processes

A process is simply a running program.

Every running application has:

- PID (Process ID)
- PPID (Parent Process ID)
- Process State
- CPU Usage
- Memory Usage

### Real-Life Use

Understanding processes helps:

- Detect malware.
- Monitor servers.
- Troubleshoot applications.
- Perform incident response.

---

## Parent & Child Processes

Every Linux process starts another process.

Example:

systemd

↓

bash

↓

python

Knowing parent-child relationships helps security analysts determine how suspicious software started.

---

## Process Monitoring

Commands revised:

```bash
ps
ps -ef
ps aux
top
```

### Purpose

Monitor:

- Running programs
- CPU usage
- Memory usage
- User ownership

### Real-Life Use

SOC analysts constantly monitor process activity while investigating compromised systems.

---

## Process Management

Commands revised:

```bash
jobs
bg
fg
kill
killall
pkill
```

### Purpose

- Resume jobs
- Stop processes
- Move jobs
- Manage background programs

### Real-Life Use

Administrators regularly stop, restart and troubleshoot services using these commands.

---

## /proc Filesystem

The `/proc` directory is not a normal folder.

It is created dynamically by the Linux kernel.

Useful information:

- Process Status
- Memory
- Threads
- Open Files

### Real-Life Use

Used extensively during:

- Malware Analysis
- Linux Forensics
- Incident Response
- Debugging

---

## Compression Utilities

Commands revised

```bash
tar
gzip
gunzip
bzip2
bunzip2
```

### Difference

**tar**

Creates an archive.

**gzip**

Compresses one file.

**gunzip**

Extracts gzip files.

**bzip2**

Higher compression.

**bunzip2**

Extracts bzip2 files.

---

### Real-Life Use

Used for:

- Linux backups
- Log archives
- File transfers
- Digital evidence preservation
- Malware packaging

---

## Shell Operators

### >

Overwrite output.

---

### >>

Append output.

---

### |

Pipe output.

---

### &&

Execute next command only if first succeeds.

---

### ||

Execute next command only if first fails.

---

### &

Run process in background.

---

### 2>

Redirect errors.

---

### 2>/dev/null

Hide errors.

### Real-Life Use

Penetration testers commonly use

```bash
find / -name file 2>/dev/null
```

to remove unnecessary permission errors during enumeration.

---

# 🌍 Real-Life Cybersecurity Applications

Today's revision directly applies to

- Linux Administration
- SOC Operations
- Threat Hunting
- Incident Response
- Malware Analysis
- Digital Forensics
- Penetration Testing
- Cloud Security
- DevOps

Almost every Linux security task uses these concepts.

---

# 🔄 Command Revision

## Navigation

| Command | Use |
|----------|-----|
| pwd | Show current directory |
| ls | List files |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |

---

## File Operations

| Command | Use |
|----------|-----|
| touch | Create file |
| cp | Copy |
| mv | Move/Rename |
| rm | Delete |
| cat | Display file |
| head | Beginning of file |
| tail | End of file |
| less | Scroll through file |
| file | Identify file type |

---

## Searching & Text

| Command | Use |
|----------|-----|
| grep | Search text |
| sort | Sort lines |
| uniq | Remove duplicates |
| diff | Compare files |
| cmp | Byte comparison |
| comm | Compare sorted files |
| wc | Count words/lines |
| find | Search filesystem |

---

## User Information

| Command | Use |
|----------|-----|
| whoami | Current username |
| id | User & Groups |
| hostname | Machine name |

---

## Permissions

| Command | Use |
|----------|-----|
| chmod | Change permissions |

---

## Networking

| Command | Use |
|----------|-----|
| ssh | Secure login |
| ping | Connectivity test |
| ss | Socket information |
| nc | TCP/UDP communication |
| nmap | Port scanning |
| curl | Access websites/APIs |
| wget | Download files |
| openssl s_client | Test SSL/TLS |

---

## Compression

| Command | Use |
|----------|-----|
| tar | Archive files |
| gzip | Compress |
| gunzip | Decompress |
| bzip2 | Compress better |
| bunzip2 | Decompress |

---

## Process Commands

| Command | Use |
|----------|-----|
| ps | Process list |
| ps -ef | Detailed process list |
| ps aux | CPU & Memory usage |
| top | Live monitoring |
| jobs | Background jobs |
| bg | Resume background |
| fg | Bring foreground |
| kill | Terminate process |

---

## Shell Operators

| Operator | Use |
|-----------|-----|
| > | Overwrite output |
| >> | Append output |
| \| | Pipe output |
| && | Execute if success |
| \|\| | Execute if failure |
| & | Background process |
| 2> | Redirect errors |
| 2>/dev/null | Hide errors |

---

# 🎯 Bandit Preparation (Level 21)

For tomorrow's Bandit level, make sure you're comfortable with:

✅ File searching

✅ Reading files

✅ Shell navigation

✅ SSH login

✅ Background processes

✅ Process monitoring

✅ Error redirection

No new commands are required beyond what you've already learned.

---

# 👨‍🏫 Mentor Questions (Answered)

### Why should revision be done regularly?

Because Linux commands build upon one another. Regular revision improves speed, confidence and long-term memory.

---

### Why are Linux commands usually combined instead of used individually?

Most real tasks require multiple commands working together through pipes, redirection or shell operators.

---

### Which concept became much clearer today?

Process management.

Initially it felt confusing, but after revision I now understand how Linux keeps track of running programs.

---

### Why is Linux important for cybersecurity?

Most servers, cloud systems and security tools run on Linux. A strong Linux foundation makes advanced cybersecurity topics much easier.

---

### Which command do I think I'll use the most?

`grep`

It quickly finds useful information inside files and command output.

---

### Which command surprised me the most?

`top`

Watching processes update in real time made Linux feel much more alive.

---

### What should I improve before tomorrow?

Become faster with combining commands instead of thinking about each command separately.

---

# 📝 Personal Reflection

Today's revision showed me that I have learned much more than I originally thought.

Commands that felt difficult during the first week now feel familiar.

I also realised that Linux is not about memorising commands. It is about understanding how the operating system works internally.

By revising everything together, I now understand how processes, networking, permissions and shell commands all connect with one another.

This gives me much more confidence before continuing with the next Bandit level and future cybersecurity topics.

---

# ⭐ Key Takeaway

> "Commands solve problems, but understanding Linux explains *why* those solutions work."

A strong Linux foundation today will make penetration testing, reverse engineering, malware analysis and digital forensics significantly easier in the future.