# 📘 Notes 025 — Linux Process Management, Monitoring & Shell Control

> Topic: Linux Internals — Processes & Shell Operators
> Day: 031
> Notes No.: 025

---

# 🎯 Learning Objective

Today's focus was understanding how Linux manages running programs internally.

Unlike previous sessions that concentrated mainly on commands, today's concepts explain *why* Linux behaves the way it does.

---

# 📚 Concepts Learned

## 1. Program vs Process

**Program**
- Stored on disk
- Passive
- Does not consume CPU

**Process**
- Running instance of a program
- Stored in RAM
- Uses CPU and memory
- Has a unique Process ID

### Real-life Use

Understanding this distinction helps during malware analysis, incident response, and server troubleshooting because malware always executes as a process.

---

# 2. Process Lifecycle

Typical flow:

Program
→ Running
→ Waiting / Sleeping
→ Running
→ Terminated

Processes continuously move between these states while Linux schedules CPU time.

### Real-life Use

Useful when analysing applications that freeze, hang or consume excessive CPU.

---

# 3. Parent Process

Every Linux process is created by another process.

Example

systemd
└── bash
    └── python

---

# 4. Child Process

Processes created by another process.

Understanding parent-child relationships helps trace malicious execution chains.

---

# 5. PID (Process ID)

Unique number assigned to every running process.

Example

PID 532 → bash

PID 1200 → python

### Real-life Use

Used to monitor or terminate specific processes.

---

# 6. PPID (Parent Process ID)

Stores the PID of the process that created the current process.

### Real-life Use

Essential during malware investigations to identify which application launched a suspicious process.

---

# 7. Process Monitoring

## ps

Displays a snapshot of currently running processes.

---

## ps -ef

Displays detailed information about every running process.

---

## ps aux

Displays:

- CPU usage
- Memory usage
- User
- Process state
- Command

---

## top

Real-time process monitor.

Shows

- CPU utilisation
- Memory usage
- Running processes
- Load Average

---

## htop

Improved version of top.

Provides:

- Colour interface
- Scrolling
- Better readability

(Currently introduced only.)

---

# 8. Foreground Process

Runs directly inside the terminal.

Example

```bash
nano
```

Terminal waits until the process finishes.

---

# 9. Background Process

Runs independently of the terminal.

Example

```bash
sleep 300 &
```

Allows multitasking.

---

# 10. Process Signals

Signals tell processes what action to perform.

Common examples

- Interrupt
- Stop
- Continue
- Terminate

---

# 11. Process Management Commands

## kill

Terminates a process using its PID.

---

## killall

Terminates all processes with the same name.

---

## pkill

Terminates processes matching a pattern.

---

## jobs

Displays background jobs started from the current shell.

---

## fg

Moves a background job to the foreground.

---

## bg

Resumes a stopped job in the background.

---

## nohup

Allows a program to continue running after terminal logout.

### Real-life Use

Commonly used for:

- Servers
- Background automation
- Long-running scripts

---

# 12. /proc Filesystem

A virtual filesystem exposing real-time kernel and process information.

Useful files include:

- status
- cmdline
- environ
- fd

### Real-life Use

Widely used in:

- Malware analysis
- Linux forensics
- Incident response
- Process investigation

---

# 13. Shell Operators

## 2>

Redirects standard error into a file.

Example

```bash
find / -name test 2>errors.txt
```

---

## 2>/dev/null

Discards all error messages.

Very common in penetration testing.

---

## &&

Execute next command only if previous succeeds.

Example

```bash
mkdir test && cd test
```

---

## ||

Execute next command only if previous fails.

Example

```bash
cd folder || echo "Folder missing"
```

---

# 🌍 Real-Life Cybersecurity Applications

Today's concepts are heavily used in:

- Linux Administration
- Server Monitoring
- SOC Operations
- Malware Analysis
- Digital Forensics
- Incident Response
- Privilege Escalation
- Threat Hunting

---

# 🔄 Revision

## File & Directory

| Command | Use |
|----------|-----|
| pwd | Show current directory |
| ls | List files |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| touch | Create file |
| cp | Copy files |
| mv | Move/Rename files |
| rm | Delete files |

---

## File Reading

| Command | Use |
|----------|-----|
| cat | Display file |
| head | Beginning of file |
| tail | End of file |
| less | Interactive reading |
| file | Identify file type |

---

## Text Processing

| Command | Use |
|----------|-----|
| grep | Search text |
| sort | Sort lines |
| uniq | Remove duplicate adjacent lines |
| diff | Compare files |
| cmp | Byte comparison |
| comm | Compare sorted files |
| wc | Count lines/words/bytes |

---

## Searching

| Command | Use |
|----------|-----|
| find | Search files/directories |

---

## Networking

| Command | Use |
|----------|-----|
| ssh | Secure remote login |
| ping | Connectivity testing |
| ss | Display sockets |
| nc | TCP/UDP communication |
| nmap | Network scanner |
| openssl s_client | SSL/TLS testing |
| curl | Transfer data from URLs/APIs |
| wget | Download files |

---

## User Information

| Command | Use |
|----------|-----|
| whoami | Current user |
| id | UID, GID, Groups |
| hostname | Machine hostname |

---

## Permissions

| Command | Use |
|----------|-----|
| chmod | Modify permissions |

---

## Shell Operators

| Operator | Use |
|----------|-----|
| \| | Pipe output |
| > | Overwrite output |
| >> | Append output |
| & | Run in background |
| && | Execute if previous succeeds |
| \|\| | Execute if previous fails |
| 2> | Redirect errors |
| 2>/dev/null | Hide errors |

---

# 👨‍🏫 Professor Questions & Answers

### Q1. Why is PID important?

It uniquely identifies every running process so Linux can manage it individually.

---

### Q2. Why do processes have parents?

Linux creates processes hierarchically, making management and tracing easier.

---

### Q3. Why use top instead of ps?

top provides live monitoring, while ps gives only a snapshot.

---

### Q4. Why is /proc useful?

It exposes runtime process information for monitoring, debugging and security analysis.

---

### Q5. Why should penetration testers use 2>/dev/null?

To remove permission errors and focus only on useful output.

---

### Q6. Why use && in scripts?

It prevents later commands from executing if an earlier step fails.

---

### Q7. Where are today's concepts used professionally?

- SOC Monitoring
- Linux Server Administration
- Malware Analysis
- Threat Hunting
- Cloud Infrastructure
- Incident Response

---

# 📝 Key Takeaways

✔ Linux manages every running program as a process.

✔ Every process has a PID and PPID.

✔ Process monitoring is fundamental for system administration.

✔ `/proc` provides powerful runtime information.

✔ Background jobs improve multitasking.

✔ Shell operators greatly improve scripting and automation.

✔ These concepts form the foundation for advanced Linux security and ethical hacking.