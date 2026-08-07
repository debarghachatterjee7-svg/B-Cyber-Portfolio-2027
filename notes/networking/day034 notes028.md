# 📘 Notes 028
# Linux Process Management, Cron & Linux Internals

**Day:** 034  
**Notes No.:** 028

---

# 🎯 Purpose of Today's Learning

Today's session focused on understanding **how Linux works internally** rather than learning many new commands.

Until now, we learned how to use Linux.

Today, we learned **how Linux thinks**.

This knowledge becomes extremely important for:

- Ethical Hacking
- Linux Administration
- Malware Analysis
- Digital Forensics
- Privilege Escalation
- Reverse Engineering
- Incident Response

---

# 🧠 Process Management

A **process** is simply a running program.

Whenever you execute a command like

```bash
ls
```

Linux creates

```
Program
↓

Process
↓

Execution
↓

Termination
```

Every running process receives a unique number.

---

# 🆔 PID (Process ID)

PID means

**Process Identifier**

Every running process gets a unique number.

Example

```
bash
PID 594
```

Linux uses this number to

- schedule CPU
- allocate memory
- stop process
- monitor process

---

## Real Life

Task Manager in Windows also displays Process IDs.

Linux servers containing thousands of processes identify each one using PID.

---

# 👨‍👦 PPID (Parent Process ID)

Every process starts from another process.

Example

```
bash
 └── python
      └── ps
```

python

Parent = bash

bash

Parent = init/systemd

---

## Why Important?

Many malware processes create child processes.

Incident responders inspect PPID to determine

"Who launched this process?"

---

# 🌳 Process Tree

Linux stores processes like a family tree.

```
systemd
 ├── sshd
 ├── cron
 ├── bash
 │     ├── python
 │     └── ps
```

Commands

```
pstree

ps --forest
```

display this visually.

---

## Real Life

Used during

- Malware Investigation
- Reverse Shell Detection
- Privilege Escalation
- Threat Hunting

---

# 👻 Daemon

Daemon

=

Background service

Examples

```
cron

sshd

apache

mysql

systemd
```

Runs continuously.

No user interaction required.

---

# ⏰ Cron

Cron

=

Linux Task Scheduler

Runs commands automatically.

Example

Every day

```
Backup

Log Cleanup

Updates

Monitoring
```

---

## Real Life

System Administrators automate

- backups
- reports
- monitoring
- software updates

Attackers also abuse Cron

for persistence.

---

# 🖥 Process Monitoring

Linux provides tools to inspect running programs.

Examples

```
ps

pstree

ps -ef

ps -aux
```

These help answer

"What is running?"

---

# 🌍 Why This Matters

Suppose a server becomes compromised.

The first thing analysts check is

```
Running Processes
```

They identify

- Unknown process
- Parent process
- CPU usage
- Memory usage

This often reveals malware immediately.

---

# 🔐 Cybersecurity Applications

Today's concepts are heavily used in

✔ SOC

✔ Malware Analysis

✔ Incident Response

✔ Linux Administration

✔ Threat Hunting

✔ Privilege Escalation

✔ Digital Forensics

✔ Cloud Security

✔ Server Monitoring

---

# 🧠 What I Learned from OverTheWire Level 21

The challenge taught me that Linux automation can reveal sensitive information.

Instead of trying random commands, I investigated:

- Cron configuration
- Scheduled jobs
- Executed scripts
- Temporary output files

By reading the Cron job and following the script, I found where the password was written and successfully retrieved it.

The biggest lesson was:

> Always inspect how the system is designed before trying to break it.

Understanding automation is often more powerful than brute force.

---

# ⚠ Common Mistake

Earlier I focused mainly on commands.

Today I realized that commands are only tools.

The real skill is understanding

how Linux behaves internally.

---

# 💡 Lesson Learned

Linux is process-oriented.

Every service,

every command,

every program

is simply another process managed by the kernel.

Understanding this makes future Linux learning much easier.

---

# 🧑‍🏫 Professor Questions (Answered)

### Why does Linux use PID?

To uniquely identify every running process so the kernel can manage it.

---

### Why is PPID important?

It tells which process created the current process.

---

### Why inspect process trees?

Because malware often creates suspicious child processes.

---

### Why is Cron dangerous if misconfigured?

Because attackers can schedule malicious commands to execute automatically.

---

### Why should security analysts monitor running processes?

To quickly identify malicious software, persistence, or unauthorized activity.

---

# 📚 Complete Revision (Day 001 → Day 034)

---

## 📂 Navigation

| Command | Purpose |
|---------|---------|
| pwd | Show current directory |
| ls | List files |
| ls -a | Show hidden files |
| ls -l | Detailed listing |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |

---

## 📄 File Management

| Command | Purpose |
|---------|---------|
| touch | Create file |
| cp | Copy |
| mv | Move/Rename |
| rm | Delete |
| cat | Display file |
| nano | Edit file |

---

## 🔎 Searching

| Command | Purpose |
|---------|---------|
| find | Search files |
| grep | Search text |
| which | Locate executable |
| whereis | Locate executable, source & man page |

---

## 📊 File Information

| Command | Purpose |
|---------|---------|
| wc | Count lines/words |
| head | First lines |
| tail | Last lines |
| file | Identify file type |
| stat | File metadata |
| strings | Extract printable text |
| cut | Extract selected fields |

---

## 🔄 Sorting

| Command | Purpose |
|---------|---------|
| sort | Sort lines |
| uniq | Remove adjacent duplicates |
| diff | Compare files |
| cmp | Byte comparison |
| comm | Compare sorted files |

---

## 🔀 Pipes & Redirection

| Symbol | Purpose |
|---------|---------|
| \| | Send output to another command |
| > | Overwrite output |
| >> | Append output |
| < | Read input from file |
| 2> | Redirect errors |
| ; | Execute sequential commands |
| & | Run command in background |

---

## 🔐 Permissions

| Command | Purpose |
|---------|---------|
| chmod | Modify permissions |
| chown | Change owner |
| chgrp | Change group |

---

## 🌐 Networking

| Command | Purpose |
|---------|---------|
| ssh | Remote login |
| scp | Secure file copy |
| curl | Fetch web resources |
| wget | Download files |
| ping | Connectivity test |
| ip addr | Display IP configuration |
| ss | View sockets |
| nc | Network debugging |
| nmap | Port scanning |
| openssl | SSL/TLS & crypto testing |

---

## 🌍 Environment Variables

| Command | Purpose |
|---------|---------|
| env | Show environment |
| printenv | Print variables |
| echo $VAR | Show variable |
| export | Create variable |
| unset | Remove variable |

---

## ⚙ Archives & Compression

| Command | Purpose |
|---------|---------|
| tar | Archive |
| gzip | Compress |
| gunzip | Decompress |
| bzip2 | Compress (bzip2) |
| bunzip2 | Decompress (bzip2) |

---

## 🖥 Process Management

| Command | Purpose |
|---------|---------|
| echo $$ | Current shell PID |
| ps | Current processes |
| ps -ef | Full process list |
| ps -aux | Detailed resource view |
| pstree | Process hierarchy |
| ps --forest | Tree process view |
| jobs | Background jobs |
| bg | Resume background |
| fg | Foreground job |
| kill | Stop process |
| sleep | Pause execution |

---

## ⏰ Scheduling

| Concept | Purpose |
|---------|---------|
| Cron | Task scheduler |
| Crontab | Schedule configuration |
| Daemon | Background service |

---

# 🚀 Preparation for Tomorrow

Tomorrow's learning will build directly upon today's understanding of Linux processes by exploring scheduled task execution and advanced Cron behavior. The process hierarchy concepts learned today will make those topics much easier to understand.

---

# 📝 Final Reflection

Today's revision strengthened my understanding of everything learned so far while also giving me a much deeper appreciation of Linux internals. I no longer see Linux as just a collection of commands—I now understand how processes, services, and scheduling work together behind the scenes. This foundation will make future cybersecurity topics much easier to grasp and apply in real-world scenarios.