# 📘 Day 035 — Linux Process Management, Cron & Environment Revision

**Notes / GitHub Note No.: 029**  
**Day:** 035  
**Focus:** Processes, PID/PPID, `ps`, `pstree`, Cron, Crontab, environment variables, exit status, and revision.

---

## 📝 Description

Today's session focused on understanding how Linux runs and organizes processes instead of simply memorizing commands.

The main practical concepts were:

- Environment variables with `env`
- Sorting command output with `sort`
- Exit status with `$?`
- Process IDs (PID)
- Parent Process IDs (PPID)
- `ps`, `ps -aux`, `ps -ef`
- `pstree`, `pstree -p`
- Filtering output using `grep`
- Cron
- Crontab
- `crontab -l`
- `crontab -e`
- Cron schedule fields
- Process investigation mindset

The session was also a revision session so that earlier Linux concepts remain comfortable before moving further into Bandit and Bash automation.

---

# 1. Today's Concepts — Brief Explanation

## `env`

Displays environment variables available to the current shell.

```bash
env
```

Examples:

```bash
echo $USER
echo $HOME
echo $PATH
echo $SHELL
```

### Real-life use

Environment variables are used for application configuration, paths, credentials/configuration values, containers, automation and deployment systems.

---

## `env | sort`

Today we also practiced sorting the environment-variable output:

```bash
env | sort
```

The pipeline means:

```text
env
 ↓
sort
```

`env` produces the information and `sort` arranges the lines alphabetically.

This is a good example of combining small Linux tools rather than trying to find one command that does everything.

---

## `$?`

```bash
echo $?
```

Shows the exit status of the previous command.

```text
0     → normally successful
non-0 → error/failure status
```

### Real-life use

Bash scripts use exit statuses to decide whether the next operation should continue.

---

# 2. Process Concepts

## PID — Process ID

Every running process has a PID.

Example:

```text
PID 594
```

This identifies a particular running process.

### Use

Useful for monitoring, troubleshooting and managing processes.

---

## PPID — Parent Process ID

PPID identifies the process that created/launched another process.

Conceptually:

```text
bash
 └── command
      └── child process
```

This creates a process hierarchy.

### Real-life use

PPID is useful when investigating:

- how a process started
- which program launched it
- suspicious process relationships
- service dependencies
- incident-response investigations

---

# 3. Process Commands

| Command | Main use |
|---|---|
| `ps` | Basic process snapshot |
| `ps -aux` | Detailed process/resource view |
| `ps -ef` | Detailed process view including PPID |
| `pstree` | Display process hierarchy |
| `pstree -p` | Process hierarchy including PIDs |
| `grep` | Filter/search command output |
| `ps -ef \| grep cron` | Search for Cron-related processes |
| `ps -ef \| grep bash` | Search for Bash processes |

---

# 4. Understanding `ps -ef`

Important columns include:

```text
UID
PID
PPID
C
STIME
TTY
TIME
CMD
```

The most important relationship for today's lesson is:

```text
PID  = identity of this process
PPID = identity of its parent
```

This lets us move from:

> "A process exists."

to:

> "I can investigate where that process came from."

---

# 5. `pstree`

```bash
pstree
```

Shows processes as a hierarchy.

With PIDs:

```bash
pstree -p
```

This is especially useful when a flat `ps` output is difficult to understand.

---

# 6. Cron & Crontab

## Cron

Cron is the Linux scheduling mechanism/service used to run commands or scripts automatically.

Examples of real-world jobs:

- scheduled backups
- log cleanup
- system maintenance
- automated reports
- monitoring scripts
- temporary-file cleanup

## Crontab

A user's scheduled Cron jobs are stored/configured through their crontab.

```bash
crontab -l
```

Lists the current user's Cron jobs.

```bash
crontab -e
```

Edits the current user's Cron jobs.

### Cron timing structure

```text
* * * * * command
│ │ │ │ │
│ │ │ │ └─ weekday
│ │ │ └─── month
│ │ └───── day of month
│ └─────── hour
└───────── minute
```

Common symbols:

```text
*   any value
,   multiple values
-   range
/   step
```

---

# 7. Today's Cybersecurity Value

Today's concepts matter because a security analyst often needs to answer:

```text
What is running?
Who started it?
Which user owns it?
What is its PID?
What is its PPID?
Is it expected?
Is it scheduled?
What command launched it?
```

A process tree can reveal relationships that are difficult to see from a simple process list.

This becomes useful later in:

- Linux security
- incident response
- digital forensics
- malware analysis
- CTFs
- security monitoring
- Bash security automation

---

# 8. Revision — Previous Linux Knowledge

Today's revision should keep the following comfortable before moving ahead.

## File & Directory Navigation

```text
pwd      → current directory
cd       → change directory
ls       → list files
ls -l    → detailed listing
mkdir    → create directory
rm       → remove
cp       → copy
mv       → move/rename
touch    → create/update file timestamp
```

## Reading & Searching

```text
cat      → display file
head     → beginning of file
tail     → end of file
grep     → search/filter text
find     → locate files/directories
wc       → count lines/words/bytes
sort     → sort lines
uniq     → remove adjacent duplicate lines
strings  → extract printable strings
cut      → extract fields/columns
```

## Text & Output Control

```text
echo     → print text/value
>        → redirect output and overwrite
>>       → redirect output and append
2>       → redirect stderr
|        → pipe output to another command
;        → run commands sequentially
&        → run a command in the background
```

## Compression & Archives

```text
gzip     → compress with gzip
gunzip   → decompress gzip
bzip2    → compress with bzip2
bunzip2  → decompress bzip2
tar      → create/extract archives
```

Important distinction:

```text
tar  → archive
gzip → compression
```

They are often combined:

```bash
tar -czvf backup.tar.gz folder
```

---

# 9. Shell & Environment Revision

```text
env       → show environment
printenv  → show environment variables
export    → create/export shell variable
unset     → remove shell variable
echo      → display variable/value
which     → locate executable
whereis   → locate binary/source/manual information
uname     → system/kernel information
```

Examples:

```bash
echo $PATH
printenv HOME
export NAME="test"
unset NAME
which ls
uname -a
```

---

# 10. Networking Revision

Previously learned networking basics should remain comfortable:

```text
ip addr    → inspect network interfaces/IP addresses
ping       → test basic reachability
```

The important idea is:

```text
ip addr → "What network identity/interfaces does this machine have?"
ping   → "Can I reach another host?"
```

These concepts will connect later to:

- network enumeration
- service discovery
- web security
- OSINT
- CTFs
- network troubleshooting

---

# 11. Permissions & Remote Operations Revision

Previously covered concepts include:

```text
chmod  → change permissions
chown  → change owner
chgrp  → change group
scp    → securely copy files over SSH
```

These are important because cybersecurity work frequently involves understanding:

```text
who owns a file?
who can read it?
who can execute it?
can it be transferred securely?
```

---

# 12. Pipelines & Command Combination

One of the most important Linux skills is combining simple commands.

Example:

```bash
env | sort
```

or:

```bash
ps -ef | grep cron
```

Instead of memorizing hundreds of specialized commands, the better skill is learning to construct a solution:

```text
produce information
      ↓
filter it
      ↓
sort/process it
      ↓
save or use the result
```

This way of thinking becomes extremely valuable in Bash scripting.

---

# 13. What I Learned From Today's Practical Work

The biggest lesson was that Linux commands describe a larger system.

For example:

```text
Bash
 ↓
launches command
 ↓
Linux creates process
 ↓
process receives PID
 ↓
process has PPID
 ↓
process appears in ps/pstree
 ↓
Cron can automatically launch commands
```

This connects shell usage, process management and automation.

---

# 14. Questions to Check My Understanding

### Q1. Why is PPID more useful than only knowing PID?

Because PPID lets me investigate the parent-child relationship and understand where a process came from.

### Q2. Why is `pstree` useful if `ps` already exists?

`ps` gives a list, while `pstree` makes process relationships visually easier to understand.

### Q3. Why combine `ps` and `grep`?

Because `ps` produces process information and `grep` quickly filters it to the process I am interested in.

### Q4. Why is Cron important for cybersecurity?

Because scheduled tasks can be legitimate automation, but during investigation scheduled jobs may also need to be checked to understand what runs automatically.

### Q5. Why is `$?` important for future Bash projects?

It lets a script determine whether a command succeeded before continuing.

---

# 15. What I Need for the Next Bandit

Before the next Bandit level, I should be comfortable with:

- reading files
- searching files
- `grep`
- `find`
- pipelines
- redirection
- permissions
- SSH basics
- environment variables
- process inspection
- PID/PPID
- Cron/crontab concepts
- command exit status
- combining commands

The key is not to memorize every option.

I should be able to investigate the environment and reason about what the level is asking me to discover.

---

# 16. How Today's Learning Will Be Used Later

### Bash Project

These concepts will directly support scripts that:

```text
check a process
find PID
check whether it is running
record results
handle errors
run automatically
```

### Cybersecurity Labs

Process and Cron knowledge will help with:

```text
system enumeration
process investigation
persistence analysis
incident response
CTF challenges
```

### Future Networking

The same investigation mindset will later be applied to:

```text
interfaces
IP addresses
ports
services
connections
DNS
HTTP
```

### Future Python

Python will eventually automate many of the tasks currently being performed manually in Bash.

---

# 17. Mentor Revision Strategy

Do not treat revision as rereading everything.

Use this pattern:

```text
Concept
  ↓
Can I explain it?
  ↓
Can I use the command?
  ↓
Can I combine it with another command?
  ↓
Can I recognize when it is useful?
```

If all four are true, the concept is becoming practical knowledge.

---

# 18. GitHub Showcase

This note demonstrates progression from basic Linux navigation toward system-level understanding.

It shows that the learning path is moving through:

```text
Linux basics
→ file/text processing
→ permissions
→ networking basics
→ processes
→ environment
→ scheduling
→ Bash automation
→ cybersecurity labs
```

The important progression is **problem-solving ability**, not the number of commands memorized.

---

# 19. Final Takeaway

Today's main concepts were:

```text
env
env | sort
$?
PID
PPID
ps
ps -aux
ps -ef
pstree
pstree -p
grep with ps
Cron
crontab -l
crontab -e
```

The most important mental model is:

> **Linux is a collection of small tools that can be combined to investigate and automate a system.**

That mindset is more valuable than simply remembering command syntax.
