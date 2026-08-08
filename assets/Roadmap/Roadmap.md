# 🛡️ Ethical Hacker Roadmap — Day 0 → Day 330

> **Purpose:** A 330-day, evidence-driven roadmap for building strong cybersecurity foundations, practical problem-solving ability, ethical-hacking skills, portfolio evidence, research habits, and readiness for competitive cybersecurity assessments.
>
> **Current checkpoint:** Day 35  
> **Learning time:** 82+ hours  
> **Bandit:** Level 21 completed  
> **Current evidence:** 35 journal days, 29 lab/notes cycles, 61 screenshots  
>
> **Important:** This roadmap is a target, not a promise. The order can change when a topic needs more practice. Security work should always be performed on systems you own or are explicitly authorized to test.

---

## 📌 What the target looks like by Day 330

| Area | Target by Day 330 |
|---|---|
| Linux/Bash | Strong practical foundation + automation |
| Python | Practical security scripting and automation |
| Networking | Strong TCP/IP, DNS, HTTP, routing and troubleshooting |
| Web security | Methodology, common vulnerabilities, safe labs |
| API security | REST, authentication, authorization and common API weaknesses |
| Cryptography | Practical foundations + crypto reasoning |
| Reverse engineering | Basic-to-intermediate static/dynamic analysis |
| OSINT | Ethical collection, verification and reporting |
| Digital forensics | Evidence handling, timelines, logs and artifact analysis |
| CTF/Hackathon | Regular timed problem solving |
| Projects | **8–12 substantial projects** + smaller experiments |
| Research | **2–3 research-style reports/papers** |
| Responsible disclosure | **2–5 legitimate reports/attempts**, only where authorized |
| Portfolio | Clean GitHub, journals, labs, writeups and project documentation |
| Communication | Technical explanations understandable to another learner |
| Ethics | Scope, authorization, evidence handling and responsible disclosure |

These are **targets**, not guaranteed outcomes.

---

# 🧭 Reality vs Ideal

## Ideal roadmap

```text
Linux → Bash → Networking → Python
                    ↓
          Web + API Security
                    ↓
       Cryptography + OSINT
                    ↓
 Reverse Engineering + Forensics
                    ↓
       CTFs / Hackathons / Labs
                    ↓
 Projects → Research → Disclosure
                    ↓
      Advanced Security Work
```

## Your actual progress

```text
Day 0
  ↓
Zero/very little technical confidence
  ↓
Linux fundamentals
  ↓
Shell commands + pipelines + redirection
  ↓
Bandit problem solving
  ↓
Bash variables/functions
  ↓
Archives/compression
  ↓
Processes + PID/PPID + pstree
  ↓
Cron / crontab
  ↓
Environment variables
  ↓
Networking basics
  ↓
Bandit 21
  ↓
Day 35
  ↓
NEXT: networking depth + Python + security domains
```

### Honest assessment

**You are not behind on the foundation phase.** You have spent more time consolidating Linux than a purely speed-focused plan would, but that has produced a useful benefit: you are beginning to solve unfamiliar Bandit problems by reasoning from concepts instead of blindly copying commands.

The main risk now is **over-staying in Linux revision**. From the next phase, learning should become broader while Linux remains a recurring revision tool.

---

# 📊 Progress Snapshot

- **Days completed:** 35 / 330
- **Roadmap completion:** ~10.6%
- **Learning hours:** 82+
- **Bandit progress:** Level 21 completed
- **Portfolio evidence:** 61 screenshots
- **Lab/notes cycles:** 29
- **Major security domains started:** foundational Linux/networking only
- **Python:** planned to begin around Days 45–46
- **Major projects:** foundation phase; substantial security projects come later
- **Research:** preparation/documentation phase
- **Responsible disclosure:** intentionally later, after methodology and authorization/scope are understood

---

# 🗓️ Day-by-Day Roadmap

## Phase 0 — Days 0–7: Orientation + Linux

### Day 0
- Cybersecurity overview
- Ethical hacking vs unauthorized activity
- Linux environment setup
- GitHub/journal structure
- Goal setting

### Day 1
- Linux shell
- Terminal
- Filesystem basics
- Absolute vs relative paths

### Day 2
- `pwd`, `cd`, `ls`
- Navigation
- Directory structure

### Day 3
- `cat`, `nano`, `head`, `tail`
- Reading and editing files

### Day 4
- `cp`, `mv`, `rm`
- File management

### Day 5
- `grep`
- Pattern searching
- Pipes

### Day 6
- `find`
- File discovery
- Search reasoning

### Day 7
- Revision + mini Linux challenge
- Documentation review

**Milestone:** Comfortable navigating Linux without constantly relying on a cheat sheet.

---

# Phase 1 — Days 8–20: Command-Line Reasoning + Bandit

### Days 8–10
- `wc`
- `sort`
- `uniq`
- `echo`
- redirection
- pipelines

### Days 11–13
- filenames and special characters
- `grep` combinations
- `find` conditions
- output filtering

### Days 14–16
- permissions
- `chmod`
- ownership concepts
- practical file-access reasoning

### Days 17–20
- Bandit progression
- combining commands
- reading problem statements
- hypothesis → command → output → correction

**Milestone:** Stop thinking “which command solves this?” and start thinking “what evidence do I need?”

---

# Phase 2 — Days 21–35: Bash, Processes, Archives, Cron

### Days 21–24
- shell variables
- `$USER`
- `$HOME`
- `$PATH`
- `$?`
- `$$`
- `$PPID`
- positional parameters

### Days 25–27
- Bash functions
- arguments
- return status
- command substitution
- `&&`
- `;`
- `<`
- `2>`
- `&`

### Days 28–30
- `tar`
- `gzip`
- `gunzip`
- `bzip2`
- `bunzip2`
- archive vs compression

### Days 31–33
- `ps`
- `ps -ef`
- `ps aux`
- PID
- PPID
- process relationships
- `pstree`
- jobs/background processes

### Days 34–35
- cron
- crontab
- environment variables
- `env`
- `printenv`
- `export`
- `unset`
- `ping`
- `ip addr`
- revision of previous concepts
- Bandit reasoning

**Milestone:** Bandit Level 21 completed and Linux troubleshooting mindset developing.

---

# Phase 3 — Days 36–60: Networking + Python Begins

## Days 36–40 — Networking foundation
Learn:
- IP addresses
- IPv4 structure
- localhost
- ports
- TCP vs UDP
- DNS
- routing basics
- `ip addr`
- `ip route`
- `ping`
- `ss`
- `curl`
- `wget`

## Days 41–44 — Networking troubleshooting
- client/server model
- sockets
- listening ports
- connection failures
- HTTP request/response
- status codes
- headers
- DNS resolution
- safe local network experiments

## Days 45–46 — Python begins
- variables
- strings
- numbers
- booleans
- lists
- tuples
- dictionaries
- conditions
- loops

## Days 47–50
- functions
- parameters
- return values
- exceptions
- files
- modules
- basic command-line arguments

## Days 51–55
Security-oriented Python:
- file parsing
- log parsing
- text processing
- regex
- JSON
- CSV
- subprocess basics
- simple automation

## Days 56–60
**Project 1: Linux Security Toolkit**
- system information
- log inspection
- process summary
- file checks
- basic network information
- documented output

---

# Phase 4 — Days 61–90: Web + API Security

### Days 61–65
- HTTP deeply
- methods
- status codes
- headers
- cookies
- sessions

### Days 66–70
- HTML
- JavaScript basics
- browser/server model
- same-origin concepts

### Days 71–75
- authentication
- authorization
- access control
- sessions
- password storage concepts

### Days 76–80
- OWASP-style vulnerability categories
- injection concepts
- XSS concepts
- access-control failures
- security misconfiguration
- safe practice labs

### Days 81–85
API security:
- REST
- JSON
- endpoints
- authentication
- authorization
- tokens
- JWT concepts
- BOLA/IDOR concepts

### Days 86–90
**Project 2: Web/API Security Lab Report**
- authorized test environment
- methodology
- findings
- evidence
- remediation
- final report

---

# Phase 5 — Days 91–120: Cryptography

### Days 91–95
- hexadecimal
- binary
- modular arithmetic
- primes
- GCD
- basic number theory

### Days 96–100
- hashing
- MD5/SHA-2 concepts
- salts
- password storage
- integrity

### Days 101–105
- symmetric cryptography
- AES
- historical DES concepts
- keys
- IV/nonce concepts

### Days 106–110
- asymmetric cryptography
- RSA
- public/private keys
- signatures
- certificates

### Days 111–115
- Diffie–Hellman
- key exchange
- TLS concepts

### Days 116–120
**Project 3: Cryptography Demonstration Toolkit**
- hash comparison
- password-storage demonstration
- symmetric encryption demonstration
- public-key/signature demonstration
- educational documentation

---

# Phase 6 — Days 121–150: OSINT + Security Research

### Days 121–125
- OSINT methodology
- collection
- validation
- source reliability
- separating facts from assumptions

### Days 126–130
- search operators
- public-document discovery
- metadata concepts
- domain information

### Days 131–135
- digital footprints
- public infrastructure information
- ethical boundaries
- privacy

### Days 136–140
- information correlation
- timeline construction
- evidence notes

### Days 141–145
**Project 4: OSINT Investigation Report**
- defined question
- sources
- evidence
- confidence level
- conclusion

### Days 146–150
**Research Paper 1**
- choose a narrow cybersecurity question
- literature review
- methodology
- results
- limitations
- references

---

# Phase 7 — Days 151–190: Reverse Engineering

### Days 151–155
- CPU/register concepts
- memory
- stack/heap
- assembly fundamentals

### Days 156–160
- executable formats
- static analysis concepts
- strings
- imports
- symbols

### Days 161–165
- disassembly
- control flow
- functions
- calling conventions

### Days 166–170
- debugging concepts
- breakpoints
- registers
- memory inspection

### Days 171–175
- basic malware-analysis methodology
- indicators
- behavior vs static evidence
- safe isolated environments

### Days 176–180
**Project 5: Safe Binary Analysis Report**
- analyze an intentionally provided educational binary
- document observations
- explain execution flow

### Days 181–190
- reverse-engineering challenges
- CTF-style binaries
- timed analysis

---

# Phase 8 — Days 191–225: Digital Forensics + Incident Response

### Days 191–195
- evidence
- hashes
- timestamps
- chain of custody concepts

### Days 196–200
- Linux logs
- process evidence
- authentication logs
- filesystem artifacts

### Days 201–205
- Windows artifact concepts
- event logs
- user activity evidence

### Days 206–210
- network evidence
- packet/log interpretation

### Days 211–215
- incident timeline

### Days 216–220
**Project 6: Forensic Investigation**
- evidence
- timeline
- findings
- conclusion
- remediation

### Days 221–225
- incident-response simulation

---

# Phase 9 — Days 226–260: CTF + Hackathon Practice

### Days 226–230
- timed Linux challenges

### Days 231–235
- networking challenges

### Days 236–240
- web challenges

### Days 241–245
- cryptography challenges

### Days 246–250
- OSINT challenges

### Days 251–255
- reverse-engineering challenges

### Days 256–260
**Full simulated cybersecurity assessment**
- multiple domains
- time limit
- evidence-based answers
- post-test review

---

# Phase 10 — Days 261–290: Advanced Integration

### Days 261–270
**Project 7: Security Automation Platform**
- Python
- Linux
- logs
- network information
- reporting

### Days 271–280
**Project 8: Multi-domain Security Lab**
- web
- API
- networking
- authentication
- logging

### Days 281–285
**Research Paper 2**
- focused technical question
- experiments
- analysis
- references

### Days 286–290
- portfolio cleanup
- project documentation
- technical writing

---

# Phase 11 — Days 291–315: Responsible Security + Portfolio

### Days 291–295
- vulnerability lifecycle
- scope
- authorization
- disclosure ethics

### Days 296–300
- writing a professional vulnerability report
- reproduction steps
- impact
- remediation

### Days 301–305
- authorized disclosure practice
- public programs only
- no out-of-scope testing

### Days 306–310
**Project 9: Vulnerability Research Report**
- educational/authorized target
- evidence
- impact
- remediation

### Days 311–315
- GitHub portfolio review
- resume/project evidence
- technical writing

---

# Phase 12 — Days 316–330: Final Assessment

### Days 316–320
- Linux/networking revision
- Python revision
- web/API revision

### Days 321–324
- cryptography/OSINT revision
- reverse engineering/forensics revision

### Days 325–327
- full timed assessment

### Days 328–329
- weak-area repair
- project review

### Day 330
# 🏁 Final Cybersecurity Portfolio Checkpoint

Expected evidence:
- 8–12 substantial projects
- 2–3 research-style papers
- 1 strong GitHub portfolio
- documented CTF/hackathon practice
- multiple lab writeups
- responsible-disclosure experience where legitimately available
- strong Linux/networking/Python foundation
- security methodology
- clear ethical boundaries

---

# 🧩 Skill Map

## Programming languages

### Python — primary
Use for:
- automation
- log analysis
- parsers
- security tooling
- data processing

### Bash
Use for:
- Linux automation
- system administration
- process handling
- security workflows

### HTML/CSS/JavaScript
Use for:
- understanding web applications
- client/server behavior
- web-security testing

### SQL
Use for:
- understanding databases
- application data flows
- injection concepts

### C / C-like concepts
Use for:
- memory
- pointers
- compiled programs
- reverse engineering

### Assembly
Use for:
- binary analysis
- debugging
- understanding low-level execution

---

# 🧰 Core Tool Families

| Family | Examples | Purpose |
|---|---|---|
| Linux | Bash, coreutils | System interaction |
| Networking | `ip`, `ping`, `ss`, `curl`, `wget` | Connectivity and protocols |
| Processes | `ps`, `pstree`, `jobs` | Process analysis |
| Archives | `tar`, `gzip`, `bzip2` | Data packaging |
| Search | `grep`, `find`, `strings` | Evidence discovery |
| Web | Browser/dev tools + authorized labs | Web understanding |
| Python | Python standard library | Automation |
| RE | Disassembler/debugger concepts | Binary analysis |
| Forensics | Logs, hashes, timelines | Investigation |
| Git | Git/GitHub | Evidence and portfolio |

---

# 🔁 Revision System

Every new topic enters three revision cycles:

### R1 — Same day
Understand the concept and perform it once.

### R2 — 3–7 days later
Perform it without copying commands.

### R3 — 21–30 days later
Solve a mixed problem where the concept is not explicitly named.

The goal is not memorizing hundreds of commands.

The goal is:

> **Observe → form hypothesis → choose tool → test → inspect output → revise hypothesis → document.**

---

# 🧠 Current Linux/Bash Revision Reference

## Navigation
- `pwd` — current directory
- `cd` — change directory
- `ls` — list directory contents

## Files
- `cat` — display content
- `head` — beginning
- `tail` — end
- `touch` — create/update file timestamp
- `cp` — copy
- `mv` — move/rename
- `rm` — remove

## Search/filter
- `grep` — search matching text
- `find` — locate files
- `sort` — sort lines
- `uniq` — collapse repeated adjacent lines
- `wc` — count lines/words/bytes
- `cut` — select fields/characters
- `xargs` — turn input into command arguments
- `strings` — extract printable strings
- `tac` — reverse line order

## Redirection
- `>` — overwrite stdout file
- `>>` — append stdout
- `<` — provide stdin from file
- `2>` — redirect stderr
- `&` — background/process control depending on context
- `|` — pipe stdout to another command

## Shell control
- `;` — run commands sequentially
- `&&` — run next command if previous succeeds
- `$?` — previous command exit status
- `$$` — current shell PID
- `$PPID` — parent PID

## Environment
- `env` — show environment
- `printenv` — print environment variables
- `export` — expose variable to child processes
- `unset` — remove shell variable
- `$PATH` — executable search path
- `$HOME` — home directory
- `$USER` — current username

## Processes
- `ps` — process snapshot
- `ps -ef` — detailed process view
- `ps aux` — process view with resource information
- `pstree` — process hierarchy
- `jobs` — shell jobs
- `kill` — send signal to a process

## Scheduling
- `cron` — background scheduler
- `crontab` — user scheduling configuration

## Archives/compression
- `tar` — package files/directories
- `gzip` / `gunzip` — gzip compression/decompression
- `bzip2` / `bunzip2` — bzip2 compression/decompression

## Networking
- `ip addr` — inspect network interfaces/addresses
- `ping` — test reachability using ICMP
- `curl` — make network requests
- `wget` — retrieve resources
- `nc` — network connection utility in authorized labs
- `ssh` — secure remote shell
- `scp` — secure file transfer

---

# 🧪 Project Portfolio Target

| Project | Target phase |
|---|---|
| Linux Security Toolkit | Days 56–60 |
| Web/API Security Report | Days 81–90 |
| Cryptography Toolkit | Days 116–120 |
| OSINT Investigation | Days 141–145 |
| Binary Analysis Report | Days 176–180 |
| Digital Forensics Investigation | Days 216–220 |
| Security Automation Platform | Days 261–270 |
| Multi-domain Security Lab | Days 271–280 |
| Vulnerability Research Report | Days 306–310 |

Small experiments can be added between these projects.

---

# 📚 Research Target

## Paper 1
Days 146–150  
**Goal:** learn the research process.

## Paper 2
Days 281–285  
**Goal:** produce a stronger technical investigation with experiments.

## Optional Paper 3
Days 316–330  
**Goal:** integrate multiple security domains.

A paper is valuable only if it demonstrates:
- a clear question
- reliable sources
- methodology
- evidence
- analysis
- limitations
- references

---

# 🛡️ Responsible Disclosure

This comes **after** security methodology is mature.

Target:
- understand scope
- understand authorization
- reproduce safely
- minimize impact
- collect only necessary evidence
- report professionally
- never test systems without permission

A successful report is useful evidence, but **quality and ethics matter more than the number of reports**.

---

# 🎯 Competitive Cybersecurity Assessment Preparation

The official 2026 undergraduate cybersecurity admissions information published by IIT Kanpur describes prior cybersecurity work as part of shortlisting and an in-person assessment containing a hackathon. The published test areas included **cryptography, web security, API security, network security, reverse engineering and OSINT**, with the assessment emphasizing analytical thinking, curiosity and cybersecurity aptitude. citeturn0search0turn0search27

The official program page also lists coursework such as computing, data engineering, malware analysis, applied cryptography, data structures and algorithms, computer organization, digital forensics and operating systems. citeturn0search0

### Therefore this roadmap deliberately emphasizes:

1. **Analytical thinking**
2. **Linux/OS understanding**
3. **Networking**
4. **Cryptography**
5. **Web security**
6. **API security**
7. **OSINT**
8. **Reverse engineering**
9. **Malware-analysis concepts**
10. **Digital forensics**
11. **Programming**
12. **Timed problem solving**
13. **Evidence of prior work**
14. **Ethical/security judgment**

This is **not a guarantee of admission**. Admission rules and future assessments can change.

---

# 📈 Current vs Ideal

| Area | Ideal by Day 35 | Current |
|---|---|---|
| Linux | Strong beginner | 🟢 Strong beginner |
| Bash | Beginner | 🟢 Beginner |
| Processes | Beginner | 🟢 Beginner |
| Cron | Beginner | 🟢 Beginner |
| Networking | Beginner | 🟡 Early foundation |
| Python | Started | 🔵 Not started yet |
| Web security | Started | 🔴 Not yet |
| API security | Started | 🔴 Not yet |
| Cryptography | Started | 🔴 Not yet |
| OSINT | Started | 🔴 Not yet |
| Reverse engineering | Started | 🔴 Not yet |
| Forensics | Started | 🔴 Not yet |
| CTF/Hackathon | Regular | 🟡 Bandit practice |
| Projects | 1+ | 🟡 Foundation experiments |
| Research | Preparation | 🟡 Documentation/research habits |
| Disclosure | Later | 🔴 Not yet |

### Interpretation

Your **foundation is ahead of the later-domain work because we intentionally spent time making Linux practical**.

That is fine.

The next correction is not “rush through everything.”

It is:

> **Broaden the roadmap while continuing Linux as maintenance practice.**

---

# 🏆 What “Good Ethical Hacker” Means

A good ethical hacker is not someone who knows the most commands.

A strong practitioner can:

1. Understand a system.
2. Identify an interesting security question.
3. Work only within authorization.
4. Gather evidence carefully.
5. Build a hypothesis.
6. Test the hypothesis safely.
7. Understand why the result occurred.
8. Explain the vulnerability or behavior.
9. Suggest remediation.
10. Document the work clearly.
11. Automate repetitive tasks.
12. Know when **not** to test something.

---

# 🔮 Beyond Day 330

After this roadmap, the next stage should become specialization rather than endlessly collecting tools.

Possible tracks:

- Web application security
- API security
- Cloud security
- Reverse engineering
- Malware analysis
- Digital forensics
- Security engineering
- Detection/blue team
- Cryptanalysis
- Security research

The strongest choice should come from the areas where your projects and experiments show the most genuine ability.

---

# 📌 Personal Progress Log

## Day 0
Starting point:
- Little practical cybersecurity knowledge
- Beginning Linux from fundamentals

## Day 1–20
Major development:
- Linux navigation
- files
- search
- pipelines
- redirection
- Bandit reasoning

## Day 21–30
Major development:
- Bash
- variables
- functions
- shell control
- archives/compression
- more Bandit problem solving

## Day 31–35
Major development:
- processes
- PID/PPID
- `ps`
- `pstree`
- cron/crontab
- environment variables
- networking foundations
- Bandit 21
- systematic revision

## Day 35 checkpoint
**82+ hours of learning**

The biggest change is not the number of commands learned.

It is the ability to look at an unfamiliar output and ask:

> **“What is this telling me, and what should I investigate next?”**

---

# 🚀 Operating Rule for the Next 295 Days

Do not optimize for finishing the roadmap.

Optimize for:

**Understand → Practice → Break → Debug → Explain → Document → Reuse.**

That is what turns a collection of tutorials into actual capability.

---

## Repository evidence structure

```text
README.md
roadmap.md

journal/
├── day001.md
├── day002.md
├── ...
└── day330.md

notes/
├── note001.md
├── ...
└── note330.md

labs/
├── lab001.md
├── ...
└── lab330.md

projects/
├── linux-security-toolkit/
├── web-api-security/
├── crypto-toolkit/
├── osint-investigation/
├── binary-analysis/
├── digital-forensics/
└── security-automation/

research/
├── paper01/
├── paper02/
└── paper03/

assets/
└── screenshots/
```

This structure makes the portfolio show **evidence of learning**, rather than only claims about learning.

---

# 📝 Final checkpoint

At Day 35, the mission is **not complete**.

It is:

> **Foundation established → breadth expansion begins → programming becomes a force multiplier → security domains become practical → projects become evidence → research becomes depth → responsible disclosure becomes real-world validation.**

**Next major transition:** networking depth + Python around the planned Day 45–46 window, while Linux/Bandit concepts remain part of revision rather than the entire curriculum.
