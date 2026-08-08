# 🛡️ Building an Ethical Hacker from Scratch

> **A public, transparent, hands-on cybersecurity learning journey — from Linux fundamentals toward practical ethical hacking, security engineering, research, CTFs, and responsible disclosure.**

![Focus](https://img.shields.io/badge/Focus-Cybersecurity-blue)
![Linux](https://img.shields.io/badge/Linux-WSL-orange)
![Bash](https://img.shields.io/badge/Shell-Bash-green)
![Python](https://img.shields.io/badge/Python-Planned-yellow)
![Bandit](https://img.shields.io/badge/OverTheWire-Bandit%20Level%2021-success)
![Learning](https://img.shields.io/badge/Hands--on%20Learning-82%2B%20hours-purple)
![Days](https://img.shields.io/badge/Learning%20Day-35-informational)
![Status](https://img.shields.io/badge/Status-Actively%20Learning-brightgreen)

---

## 👋 About This Repository

This repository documents my cybersecurity learning journey through structured daily practice.

The objective is **not to collect certificates or memorize security tools**. The objective is to understand how computers, operating systems, networks, applications, and security controls actually work — and then use that understanding to investigate problems responsibly.

The repository records:

- 📓 Daily journals
- 🧪 Practical laboratories
- 📝 Technical revision notes
- 📸 Evidence screenshots
- 🏴 CTF / OverTheWire progress
- 💻 Scripts and future tools
- 🔬 Research ideas and papers
- 🚀 Future cybersecurity projects
- 🧠 Mistakes, debugging, observations, and lessons learned

> **AI is used as a learning assistant for explanations, structure, review, and feedback. Practical execution and verification are performed in my own authorized environment.**

---

# 📊 Current Progress — Day 035

| Metric | Current Status |
|---|---:|
| 📅 Learning Day | **35** |
| ⏱️ Hands-on Learning | **82+ hours** |
| 🧪 Practical Lab | **Lab 029** |
| 📝 Technical Notes | **Notes 029** |
| 📓 Daily Journal | **Day 035** |
| 📸 Latest Screenshot | **SS061** |
| 🏴 OverTheWire Bandit | **Level 21 completed** |
| 💻 GitHub Documentation | **Active / continuously updated** |
| 🐧 Linux Foundation | **Strong beginner → early intermediate** |
| 🌐 Networking Foundation | **Started and actively expanding** |
| 🐚 Bash/Shell | **Core fundamentals practiced** |
| 🐍 Python | **Planned to enter where useful around Day 45–46** |
| 🔐 Cryptography | **Planned phase** |
| 🔎 OSINT | **Planned / upcoming phase** |
| 🌐 Web Security | **Planned after stronger networking foundation** |
| ⚙️ Reverse Engineering | **Planned later with binary/assembly foundations** |
| 🧪 Security Projects | **Planned after foundational modules mature** |

---

# 🎯 Mission

My long-term goal is to become a **competent and ethical cybersecurity practitioner** who can:

1. Understand systems before attacking or testing them.
2. Investigate security problems methodically.
3. Write scripts and small tools instead of depending entirely on existing tools.
4. Understand networks and protocols from the command line.
5. Analyze applications and binaries in authorized environments.
6. Perform security testing responsibly.
7. Document findings professionally.
8. Participate in CTFs and hackathons.
9. Eventually conduct responsible vulnerability research and disclosure.
10. Build original cybersecurity projects that demonstrate understanding rather than copied tutorials.

---

# 🧭 Learning Philosophy

The learning loop used throughout this repository is:

```text
Research
   ↓
Learn the concept
   ↓
Understand why it works
   ↓
Practice manually
   ↓
Break / debug / investigate
   ↓
Apply it to a challenge
   ↓
Document the result
   ↓
Revise later
   ↓
Build something with it
```

The important part is the **debugging stage**.

For example, during the Bandit work, a command not working was not treated as failure. It became a chance to ask:

- What exactly did the program receive?
- Which part of the command was interpreted differently than expected?
- Is the problem a path, permission, shell syntax, command availability, or argument issue?
- What smaller experiment can prove the cause?

That problem-solving habit is more valuable than simply remembering a command.

---

# 🛡️ Ethical Rules

All security learning is restricted to:

- My own systems
- Local/WSL laboratories
- Intentionally vulnerable environments
- CTF platforms
- Systems for which explicit authorization exists

The goal is to learn **defensive and authorized security testing**, not unauthorized access.

Responsible disclosure will be introduced later as a professional workflow: identify → verify safely → document → report through the appropriate channel → avoid unnecessary impact.

---

# 🗺️ Roadmap

## Phase 01 — Linux & System Fundamentals 🟢

### Completed / Practiced

- Linux filesystem
- Shell navigation
- File creation and manipulation
- Permissions
- Ownership
- Users and groups
- Processes
- PID / PPID
- Process trees
- Background jobs
- Environment variables
- Shell variables
- Bash functions
- Pipes
- Redirection
- Standard input/output/error
- SSH
- SCP
- Netcat
- Cron
- Crontab
- Archives and compression
- `/proc`
- Basic system inspection
- Command discovery
- Basic networking commands

### Outcome

I can now work comfortably in a Linux terminal, inspect system state, troubleshoot commands, understand process relationships, and approach CTF problems using shell-based reasoning.

---

## Phase 02 — Networking + Python 🟡

### Networking

Next networking development will include:

- IP addressing
- IPv4 structure
- Subnetting
- MAC addresses
- ARP
- ICMP
- `ping`
- DNS
- TCP
- UDP
- Ports
- Sockets
- Routing
- TCP connection states
- HTTP/HTTPS
- TLS basics
- Packet capture
- Wireshark
- Network troubleshooting

### Python

Python will be introduced around the planned **Day 45–46 window**, earlier if a networking/security task genuinely benefits from it.

Planned Python topics:

- Variables
- Data types
- Conditions
- Loops
- Functions
- Parameters and return values
- Lists / tuples / dictionaries / sets
- Strings
- Files
- Exceptions
- Modules
- `requests`
- Sockets
- JSON
- Regular expressions
- Basic automation
- Small security utilities

### Target

Build small tools such as:

- Port/service learning utilities
- HTTP information collectors for authorized targets
- Log parsers
- File/hash utilities
- Network information scripts
- CTF helper scripts
- Simple automation tools

---

# 🌐 Phase 03 — Web Security

Planned areas:

- HTTP request/response structure
- Methods
- Headers
- Cookies
- Sessions
- Authentication
- Authorization
- Access control
- Input validation
- SQL injection concepts
- XSS
- CSRF
- File upload security
- Security misconfiguration
- API security
- JWT concepts
- BOLA/IDOR concepts
- SSRF concepts
- Business logic testing
- Secure coding

The OWASP Top 10 is a useful awareness baseline, while the OWASP Web Security Testing Guide provides a broader testing methodology. The current OWASP WSTG covers information gathering, configuration, identity, authentication, authorization, session management, input validation, error handling, cryptography, business logic, client-side testing, and API testing. 

---

# 🔎 Phase 04 — OSINT & Reconnaissance

Planned areas:

- Search-engine research
- Search operators
- Public-domain information gathering
- Metadata
- DNS information
- WHOIS concepts
- Certificate transparency
- Public Git repositories
- Historical web information
- Asset discovery
- Information correlation
- Evidence organization

OSINT will be practiced only against public information and authorized targets.

The goal is not simply to find information. It is to learn how to:

```text
Question
  ↓
Search
  ↓
Collect
  ↓
Verify
  ↓
Correlate
  ↓
Document
  ↓
Assess relevance
```

---

# 🔐 Phase 05 — Cryptography

Planned areas:

- Encoding vs encryption vs hashing
- Hex / Base64
- Hashing
- SHA-256
- Password hashing
- Salting
- Symmetric encryption
- AES
- Asymmetric cryptography
- RSA
- Key exchange
- Diffie–Hellman
- Digital signatures
- Certificates
- TLS
- Common implementation mistakes

The focus will be on understanding the mathematics and security properties, not simply running cryptographic tools.

---

# ⚙️ Phase 06 — Reverse Engineering

Planned areas:

- Executable structure
- Binary formats
- x86-64 basics
- Registers
- Stack
- Heap
- Memory
- Calling conventions
- GDB
- Static analysis
- Ghidra
- Disassembly
- Debugging
- Basic patching concepts
- Mobile application analysis in authorized environments

Tools such as APK analysis utilities will only be used for applications and environments where analysis is authorized.

---

# 🧪 Phase 07 — Digital Forensics

Planned areas:

- File metadata
- Hashes
- Logs
- Processes
- File systems
- Timeline analysis
- Memory concepts
- Evidence handling
- Basic incident investigation
- Network evidence

---

# 🏴 Phase 08 — CTF / Hackathon Practice

CTF and hackathon preparation will gradually combine:

- Linux
- Networking
- Web
- Cryptography
- OSINT
- Forensics
- Reverse engineering
- Scripting
- Problem solving

The objective is to stop treating challenges as isolated puzzles and instead develop a repeatable investigation methodology.

---

# 📚 Revision System

Revision is now a permanent part of the roadmap rather than something done only before a challenge.

## Revision Cycle

```text
Daily
  ↓
Weekly
  ↓
Module revision
  ↓
Mixed practical lab
  ↓
CTF application
  ↓
Project application
```

Every revision should answer:

1. What does this command/concept do?
2. What problem does it solve?
3. What happens internally at a basic level?
4. What are its important options?
5. What mistakes can occur?
6. Where would it be useful in cybersecurity?
7. Can I solve a small problem without looking at notes?

---

# 🐧 Linux Command & Shell Revision Reference

## Navigation

| Command | Use | Important memory point |
|---|---|---|
| `pwd` | Shows current directory | Know where you are |
| `cd` | Changes directory | Relative vs absolute paths |
| `ls` | Lists directory contents | `-l`, `-a`, `-la` are important |
| `tree` | Shows directory hierarchy | Useful for visual structure |

---

## Files & Directories

| Command | Use |
|---|---|
| `touch` | Creates an empty file / updates timestamp |
| `mkdir` | Creates a directory |
| `rmdir` | Removes an empty directory |
| `rm` | Removes files/directories |
| `cp` | Copies files/directories |
| `mv` | Moves or renames files |
| `cat` | Reads/concatenates file contents |
| `head` | Shows beginning of file |
| `tail` | Shows end of file |
| `tac` | Shows file in reverse line order |
| `file` | Identifies file type |

### Important

`rm` is destructive. Always verify the path before using it.

---

# 🔍 Searching & Text Processing

| Command | Use |
|---|---|
| `grep` | Searches text using patterns |
| `find` | Searches filesystem objects |
| `wc` | Counts lines/words/bytes |
| `sort` | Sorts lines |
| `uniq` | Removes/counts adjacent duplicates |
| `cut` | Extracts fields/characters |
| `strings` | Extracts printable strings from binary/non-text files |
| `xargs` | Converts input into command arguments |

### Key idea

These tools become much more powerful when combined:

```text
find → filter → extract → sort → count
```

---

# 🔗 Pipes & Redirection

## Pipe `|`

Sends standard output from one command to another command's standard input.

```bash
command1 | command2
```

Example:

```bash
ps -ef | grep bash
```

Useful for narrowing large outputs.

---

## `<`

Uses a file as standard input.

```bash
command < file
```

---

## `>`

Redirects standard output into a file.

```bash
command > output.txt
```

Usually replaces the file contents.

---

## `>>`

Appends standard output.

```bash
command >> output.txt
```

---

## `2>`

Redirects standard error.

```bash
command 2> errors.txt
```

This is important when you want normal output and error output handled separately.

---

## `&`

Runs a command in the background.

```bash
command &
```

Useful for long-running tasks.

---

## `;`

Runs commands sequentially.

```bash
command1 ; command2
```

The second command is attempted regardless of whether the first succeeds.

---

# 🧩 Bash Variables & Functions

## Shell Variable

```bash
NAME="value"
```

Access it with:

```bash
echo "$NAME"
```

---

## `export`

Makes a shell variable available to child processes.

```bash
export NAME="value"
```

Important distinction:

```text
Shell variable
     ↓ export
Environment variable
     ↓
Child process can inherit it
```

---

## `unset`

Removes a variable from the current shell environment.

```bash
unset NAME
```

---

## `env`

Displays environment variables.

```bash
env
```

---

## `printenv`

Displays environment variables and can query a specific variable.

```bash
printenv PATH
```

---

## Bash Function

Basic structure:

```bash
function_name() {
    commands
}
```

Arguments are available through:

```text
$1 $2 $3 ...
```

Useful special variables:

| Variable | Meaning |
|---|---|
| `$0` | Script/function context name |
| `$1` | First argument |
| `$2` | Second argument |
| `$#` | Number of arguments |
| `$@` | All arguments |
| `$?` | Exit status of previous command |
| `$$` | PID of current shell |
| `$PPID` | Parent PID |

### Why functions matter

Functions turn repeated shell operations into reusable building blocks.

They are useful for:

- Automation
- System administration
- Log processing
- Security scripts
- CTF helpers
- Repetitive investigation tasks

---

# ⚙️ Process Management

## `ps`

Shows processes.

```bash
ps
ps -ef
ps aux
```

Important fields:

- PID
- PPID
- USER
- CPU
- Memory
- TTY
- STAT
- COMMAND

---

## PID

**Process ID** — the unique identifier assigned to a running process.

## PPID

**Parent Process ID** — identifies the process that created/launched the current process.

Example:

```text
PID 594
PPID 591
```

means process 591 is the parent of process 594.

---

## `pstree`

Shows processes as a hierarchy.

```bash
pstree
pstree -p
pstree -p -u
```

This is useful when understanding process relationships.

---

## `$?`

Shows the previous command's exit status.

```bash
echo $?
```

Common convention:

```text
0      success
nonzero failure/error
```

---

## `jobs`

Shows jobs started by the current shell.

## `fg`

Brings a background job to the foreground.

## `bg`

Continues a stopped job in the background.

## `kill`

Sends a signal to a process.

Use process control only when you understand which process you are affecting.

---

# ⏰ Cron & Crontab

Cron is a Linux scheduling mechanism for automatically running commands/jobs at specified times.

## `crontab -e`

Edit the current user's scheduled jobs.

## `crontab -l`

List the current user's cron jobs.

## `crontab -r`

Remove the current user's crontab.

Use carefully.

---

## Cron Format

```text
minute hour day-of-month month day-of-week command
```

Example:

```text
*/5 * * * * command
```

means run every five minutes.

### Important security concepts

When investigating scheduled jobs, ask:

- Who owns the job?
- What command runs?
- Which script is executed?
- What permissions does the script have?
- What files does it read/write?
- What environment does it run under?
- Can an unauthorized user modify something the job trusts?

This type of reasoning was directly useful in **Bandit Level 21**.

---

# 📦 Archives & Compression

## `tar`

Creates/extracts archives.

```bash
tar -cvf archive.tar folder/
tar -xvf archive.tar
```

Important flags:

- `c` = create
- `x` = extract
- `v` = verbose
- `f` = file

Compression can be combined with tar:

```bash
tar -czvf archive.tar.gz folder/
tar -xzvf archive.tar.gz
```

---

## `gzip`

Compresses a file.

```bash
gzip file.txt
```

## `gunzip`

Decompresses a gzip file.

```bash
gunzip file.txt.gz
```

## `bzip2`

Compresses using bzip2.

## `bunzip2`

Decompresses bzip2 files.

---

# 🔐 Permissions & Ownership

## `chmod`

Changes permissions.

```bash
chmod 644 file
chmod 755 script.sh
```

Remember:

```text
r = read
w = write
x = execute
```

---

## `chown`

Changes owner/group.

```bash
chown user:group file
```

## `chgrp`

Changes group ownership.

```bash
chgrp group file
```

Security relevance:

Permissions and ownership determine who can read, modify, or execute resources.

---

# 🔑 Identity & Command Discovery

| Command | Use |
|---|---|
| `whoami` | Current username |
| `id` | User/group IDs and memberships |
| `groups` | Groups for a user |
| `which` | Finds executable through PATH |
| `whereis` | Locates binary/source/manual where available |
| `uname` | Kernel/system information |

These commands are useful during system enumeration and troubleshooting.

---

# 🌐 Networking Revision

## `ip addr`

Displays network interfaces and IP addresses.

```bash
ip addr
```

Important things to recognize:

- Interface name
- IPv4 address
- Prefix
- IPv6 address
- Interface state
- Loopback

---

## `ping`

Tests basic IP reachability using ICMP echo requests.

```bash
ping <authorized-host>
```

It helps distinguish:

```text
Can I reach it?
```

from:

```text
Is the application/service working?
```

---

## `curl`

Command-line HTTP/network transfer tool.

Useful for:

- Testing HTTP requests
- Inspecting headers
- Retrieving web content
- Learning request/response behavior

---

## `wget`

Command-line retrieval utility.

Useful for:

- Downloading files
- Reproducing downloads
- Practicing HTTP/file retrieval

---

## `nc` / Netcat

A general network utility useful for learning TCP/UDP communication in controlled environments.

Important concepts learned:

```text
listener
client
port
stdin
stdout
pipe
```

The Bandit Level 20 experience was especially useful because it required thinking about how a program could receive data through a network connection.

---

## `ssh`

Secure remote shell.

Core idea:

```text
local machine
     ↓ encrypted connection
remote machine
```

---

## `scp`

Secure file copy over SSH.

Useful for moving files between authorized systems.

---

# 🧪 Bandit Progress

## Current Achievement

**OverTheWire Bandit Level 21 completed.**

The progression has already demonstrated several important real-world skills:

- Linux navigation
- File permissions
- Search
- Text processing
- Shell pipelines
- Redirection
- Networking
- Netcat
- SSH
- Process reasoning
- Cron
- Scheduled jobs
- Environment inspection
- Debugging

The most important improvement has been moving from:

> "Which command should I type?"

toward:

> "What is the system doing, and what evidence can I inspect to determine the next step?"

That change is one of the strongest outcomes of the first 35 days.

---

# 🧠 What Bandit Level 21 Added

Bandit 21 reinforced the importance of **scheduled execution**.

The useful investigation model was:

```text
Identify scheduled job
        ↓
Read configuration
        ↓
Locate executed script
        ↓
Inspect script
        ↓
Understand permissions / paths
        ↓
Understand output handling
        ↓
Find where the relevant information is produced
        ↓
Retrieve the result safely
```

This is directly transferable to:

- Linux administration
- Incident response
- Security auditing
- CTFs
- Misconfiguration analysis
- Privilege-boundary investigation

---

# 🧩 Skills Learned So Far

## Linux

- Terminal navigation
- Filesystem structure
- Files/directories
- Permissions
- Ownership
- Users/groups
- Processes
- Jobs
- Environment
- `/proc`
- Cron
- Archives
- Compression
- SSH
- SCP

## Shell

- Variables
- Environment variables
- Functions
- Arguments
- Exit status
- Pipelines
- Redirection
- Background processes
- Command chaining
- Text processing

## Networking

- IP addresses
- Interfaces
- Ports
- TCP concepts
- Basic ICMP/ping
- SSH
- HTTP basics
- Curl
- Wget
- Netcat

## Problem Solving

- Read error messages
- Break problems into smaller experiments
- Search system configuration
- Trace dependencies
- Inspect scripts
- Follow process relationships
- Use output as evidence
- Test assumptions rather than guessing

---

# 🧪 Practical Evidence

Latest tracked screenshot:

**SS061 — Environment and environment-variable investigation**

Previous practical evidence continues through the repository's screenshot collection.

Current documentation markers:

```text
Journal : Day 035
Lab     : 029
Notes   : 029
SS      : 061
Bandit  : Level 21
```

---

# 🗂️ Repository Structure

```text
B-Cyber-Portfolio-2027/
│
├── assets/
│
├── journals/
│   ├── day001.md
│   ├── ...
│   └── day035.md
│
├── labs/
│   ├── lab001.md
│   ├── ...
│   └── lab029.md
│
├── notes/
│   ├── note001.md
│   ├── ...
│   └── note029.md
│
├── screenshots/
│   ├── ss001
│   ├── ...
│   └── ss061
│
├── projects/
│
├── scripts/
│
├── ctf/
│
├── research/
│
├── tools/
│
└── README.md
```

---

# 📓 Documentation System

Each learning day follows a consistent structure.

### Journal

```text
Goal
Theory
Practical Work
Problems
Observations
Lessons Learned
Professor Questions
Reflection
Next Goal
```

### Lab

```text
Objective
Environment
Task
Expected Output
Practical Execution
Observations
Mistakes
Questions
Answers
Real-World Application
Improvement
Learning Outcome
```

### Notes

```text
Concept
Definition
Important Commands
Syntax
Examples
Common Mistakes
Security Relevance
Real-World Usage
Revision
Bandit Connection
```

---

# 🧠 How This Learning Has Helped Me

The biggest improvement has not been the number of commands memorized.

It has been the development of **technical investigation habits**.

Earlier, a large terminal output or unfamiliar error could feel confusing.

Now the approach is becoming:

```text
Observe
 ↓
Identify relevant information
 ↓
Ignore noise
 ↓
Form a hypothesis
 ↓
Run a small test
 ↓
Compare result
 ↓
Continue
```

This is useful far beyond Linux.

The same method will later apply to:

- Network troubleshooting
- Web security
- Malware analysis
- Reverse engineering
- Digital forensics
- OSINT
- CTFs
- Bug research
- Incident response

---

# 🚀 Future Projects

Projects will be introduced gradually so that they demonstrate actual understanding.

## Project 01 — Bash System Recon Toolkit

Planned capabilities:

- System information
- User information
- IP/interface information
- Running processes
- Disk information
- Basic network information
- Permission checks
- Clean structured output

---

## Project 02 — Python Network Learning Toolkit

After Python fundamentals:

- IP parsing
- Socket experiments
- Basic service checks in authorized environments
- HTTP requests
- DNS queries
- Logging
- JSON output

---

## Project 03 — Log Analysis Tool

Possible features:

- Read logs
- Extract fields
- Filter suspicious patterns
- Count repeated events
- Produce summaries
- Export structured results

---

## Project 04 — CTF Helper Toolkit

Potential components:

- Encoding/decoding helpers
- Hash utilities
- File analysis
- String extraction
- Pattern searching
- Basic automation

---

## Project 05 — Security Research Lab

A controlled environment for studying:

- Authentication
- Authorization
- Input validation
- Web vulnerabilities
- API behavior
- Logging
- Misconfiguration

---

# 🔬 Research & Research-Paper Direction

Research will become a formal part of the portfolio after the foundational phase.

Planned research themes:

- Linux security and process isolation
- Authentication weaknesses
- Web application security
- API authorization
- Security automation
- OSINT methodology
- Cryptographic implementation mistakes
- Malware/binary analysis
- Secure system design

Useful professional references include:

- **NIST Cybersecurity Framework 2.0**, which provides a high-level framework for managing cybersecurity risk.
- **OWASP Top 10**, a widely used awareness baseline for major web application risks.
- **OWASP Web Security Testing Guide**, a structured resource for web application and API security testing.
- **MITRE ATT&CK**, for understanding and organizing adversary behaviors and techniques.

These references will be used as study frameworks rather than copied into the repository.

---

# 🧪 Responsible Disclosure — Future Stage

Responsible disclosure will be introduced only after stronger foundations in:

```text
Networking
   ↓
HTTP
   ↓
Web applications
   ↓
Authentication
   ↓
Authorization
   ↓
APIs
   ↓
Security testing
   ↓
Reporting
   ↓
Responsible disclosure
```

The eventual workflow will focus on:

1. Confirm authorization/scope.
2. Identify a potential issue.
3. Reproduce safely.
4. Minimize impact.
5. Document evidence.
6. Explain security impact.
7. Suggest remediation.
8. Report through the authorized channel.
9. Respect disclosure timelines.

---

# 🏆 Hackathon Preparation

Hackathon preparation will become more serious after the core foundation is stronger.

The intended skill stack is:

```text
Linux
+
Networking
+
Python
+
Web
+
Cryptography
+
OSINT
+
Reverse Engineering
+
Problem Solving
+
Team Communication
```

The goal is to be able to receive an unfamiliar problem and quickly determine:

- What technology is involved?
- What information is available?
- What can be tested safely?
- What evidence should be collected?
- What tool or script would help?
- What is the simplest experiment that can confirm the hypothesis?

---

# 🌍 Community & Public Learning

Future public contributions may include:

- GitHub technical notes
- CTF write-ups
- Small open-source tools
- Research summaries
- Security diagrams
- Learning resources
- Responsible technical discussions

The emphasis will be on **quality over posting frequency**.

---

# 📈 Current Roadmap Assessment

### Foundation

**Status: On track / slightly ahead in practical consistency.**

The current 35-day period has produced substantial hands-on Linux and CTF exposure, with **82+ hours** invested.

The important correction now is not to rush into advanced hacking topics just to increase the topic count.

The next stage should deliberately add:

- Networking depth
- Python
- Web fundamentals
- Security methodology
- More structured projects

This will prevent the common problem of becoming good at CTF commands without understanding the underlying systems.

---

# 🗓️ Near-Term Plan

## Days 36–44

Strengthen:

- Networking
- Processes
- Shell
- Cron
- Environment
- IP addressing
- DNS
- TCP/UDP
- Ports
- HTTP fundamentals
- Practical troubleshooting
- Bandit progression where useful

## Days 45–46

Begin introducing Python into the roadmap where it provides genuine value.

## After Python Entry

Alternate:

```text
Networking
+
Python
+
Linux
+
CTF
+
Small automation
```

rather than studying Python completely separately from cybersecurity.

---

# 🎯 Long-Term Skill Target

The target is not:

> "Know 500 commands."

The target is:

> **Understand systems well enough to investigate them, automate useful tasks, recognize security weaknesses, explain the evidence, and communicate the result responsibly.**

The eventual skill progression is:

```text
Linux
 ↓
Networking
 ↓
Python
 ↓
Web
 ↓
OSINT
 ↓
Cryptography
 ↓
Forensics
 ↓
Reverse Engineering
 ↓
Security Testing
 ↓
Research
 ↓
Projects
 ↓
Hackathons / CTFs
 ↓
Responsible Disclosure
```

---

# 🧠 Personal Skill-Building Strategy

For every new technology:

### 1. Learn the vocabulary

Understand the names of the components.

### 2. Learn the mechanism

Understand what happens underneath.

### 3. Use the command/tool manually

Avoid hiding the mechanism behind automation too early.

### 4. Break something safely

Use a controlled lab.

### 5. Diagnose the failure

Read the error rather than immediately searching for the answer.

### 6. Automate only after understanding

This is where Bash and Python become powerful.

### 7. Build something

Turn the concept into a small project.

### 8. Document it

Make the work reproducible.

---

# ⭐ Milestones

| Milestone | Status |
|---|:---:|
| Linux terminal fundamentals | ✅ |
| Filesystem navigation | ✅ |
| File manipulation | ✅ |
| Permissions | ✅ |
| Ownership | ✅ |
| Users & groups | ✅ |
| Bash fundamentals | ✅ |
| Shell variables | ✅ |
| Environment variables | ✅ |
| Bash functions | ✅ |
| Pipes & redirection | ✅ |
| Process inspection | ✅ |
| PID / PPID | ✅ |
| Process tree analysis | ✅ |
| Cron / Crontab fundamentals | ✅ |
| Archive/compression tools | ✅ |
| SSH | ✅ |
| SCP | ✅ |
| Netcat fundamentals | ✅ |
| IP/interface inspection | ✅ |
| Ping fundamentals | ✅ |
| Curl / Wget | ✅ |
| OverTheWire Bandit Level 21 | ✅ |
| Networking depth | 🟡 |
| Python | 🟡 Planned |
| Web security | 🟡 Planned |
| OSINT | 🟡 Planned |
| Cryptography | 🟡 Planned |
| Reverse engineering | 🟡 Planned |
| Digital forensics | 🟡 Planned |
| Security projects | 🟡 Planned |
| Research papers | 🟡 Planned |
| Responsible disclosure | 🟡 Future |
| Hackathon preparation | 🟡 Future |

---

# 📚 Recommended Professional References

The roadmap will increasingly use recognized cybersecurity references rather than relying only on ad-hoc tutorials.

- NIST Cybersecurity Framework 2.0
- OWASP Top 10
- OWASP Web Security Testing Guide
- MITRE ATT&CK
- Official Linux documentation and manual pages
- Official Python documentation
- Protocol standards and RFCs where relevant

NIST describes CSF 2.0 as guidance for organizations to manage cybersecurity risk; OWASP describes the Top 10 as an awareness document for major web application risks; and the OWASP WSTG provides a structured testing framework for web applications and services.

---

# 🧾 Current Documentation Snapshot

```text
DAY                : 035
LEARNING HOURS     : 82+ hours
BANDIT             : Level 21 completed
LAB                : 029
NOTES              : 029
LATEST SCREENSHOT  : SS061
JOURNAL            : day035.md
ENVIRONMENT        : Windows + Ubuntu 24.04 LTS (WSL)
SHELL              : Bash
VERSION CONTROL    : Git / GitHub
DOCUMENTATION      : Markdown
EDITOR             : Visual Studio Code
```

---

# 🌱 Final Reflection

35 days ago, the main challenge was simply becoming comfortable in a Linux terminal.

The current challenge is different.

There are now enough concepts that the important skill is **connecting them**.

A process can have a PID and PPID.

A scheduled Cron job can launch a script.

A script can use environment variables.

A command can produce stdout and stderr.

Pipes can move output between programs.

Networking commands can expose interfaces and IP information.

SSH can provide remote access.

Netcat can demonstrate network communication.

Bandit then turns several of these concepts into a single investigation problem.

That is the direction this repository should continue moving toward:

```text
Commands
   ↓
Concepts
   ↓
Systems
   ↓
Relationships
   ↓
Security implications
   ↓
Automation
   ↓
Projects
   ↓
Research
```

> **The objective is not to become someone who can run security tools.  
> The objective is to become someone who understands what the tools are actually showing, why it matters, and what to do with the evidence.**

---

## ⭐ Repository Status

**Actively maintained — Day 035**

**82+ hours of hands-on learning**

**OverTheWire Bandit Level 21 completed**

**Next major focus: deeper networking → Python integration → web security → OSINT → cryptography → reverse engineering → projects → research → responsible disclosure.**
