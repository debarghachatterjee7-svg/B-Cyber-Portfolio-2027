# 📖 Cybersecurity Notes — Notes023

> **Notes ID:** Notes023  
> **Day:** 030  
> **Topic:** Local Client–Server Communication, SUID Networking & Bandit Level 20  
> **Status:** ✅ Completed Successfully

![Linux](https://img.shields.io/badge/Linux-Bash-FCC624?logo=linux&logoColor=black)
![Networking](https://img.shields.io/badge/Networking-TCP-blue)
![OverTheWire](https://img.shields.io/badge/OverTheWire-Bandit-success)
![Notes](https://img.shields.io/badge/Notes-023-orange)

---

# 🎯 Learning Objective

Today's objective was not to learn many new Linux commands, but to understand **how different Linux concepts work together** to solve a practical networking problem.

This challenge combined:

- Localhost communication
- TCP networking
- SUID privilege delegation
- Netcat
- Shell pipelines
- Background execution
- Logical problem solving

Rather than introducing completely new commands, today's lesson emphasized applying previously learned concepts in the correct sequence.

---

# 📚 Today's Theory

## 1. Client–Server Communication

Every TCP communication consists of two roles.

### Server

The server waits for incoming connections.

It listens on a specific port.

Example

```bash
nc -l 12543
```

---

### Client

The client actively connects to the server.

Today's SUID executable (`suconnect`) behaved as the client.

This was the most important observation of today's challenge.

---

## 2. Localhost

```
127.0.0.1
```

or

```
localhost
```

always refers to the current computer.

Traffic never leaves the machine.

This makes localhost useful for

- Local APIs
- Databases
- Internal services
- Testing
- Authentication

---

## 3. TCP Port

A port identifies which application should receive incoming data.

Example

```
22
SSH

80
HTTP

443
HTTPS

12543
Temporary listener (today)
```

---

## 4. SUID Executable

Today's executable

```
suconnect
```

was marked as SUID.

Meaning

It temporarily executed with **Bandit21's privileges** rather than Bandit20's.

This is an example of controlled privilege delegation.

---

# 🔧 Today's Commands

---

## echo

### Function

Prints text or variables to standard output.

Syntax

```bash
echo "Hello"
```

Today's use

```bash
echo "password"
```

Purpose

Automatically provide the required password instead of typing it manually.

---

## |

### Pipe Operator

Function

Transfers the output of one command directly into another command.

General syntax

```bash
command1 | command2
```

Today's use

```bash
echo "password" | nc -l 12543
```

Flow

```
echo
↓

Pipe

↓

Netcat

↓

TCP Connection
```

Real-life use

- Data processing
- Automation
- Log filtering
- File parsing
- Network communication

---

## nc

Netcat

Function

Creates TCP or UDP connections.

Can work as

- Server
- Client

Today's listener

```bash
nc -l 12543
```

Meaning

```
-l

Listen

12543

Port Number
```

Real-life use

- Debugging servers
- Network testing
- File transfer
- Reverse shells
- Penetration testing

---

## &

### Background Operator

Function

Runs a command in the background.

Syntax

```bash
command &
```

Today's use

```bash
echo "password" | nc -l 12543 &
```

Meaning

Start the Netcat listener but immediately return control to the terminal so another command can be executed.

Without `&`

The terminal would wait forever because Netcat would keep listening.

Real-life use

- Run long tasks
- Run listeners
- Start services
- Execute multiple commands simultaneously

---

## suconnect

Purpose

A SUID executable supplied by Bandit.

Behaviour

1. Connects to localhost.
2. Reads one line.
3. Verifies it.
4. Sends Bandit21 password.

---

# 🧩 Problem Solving Process

Initially I misunderstood the challenge.

I assumed I had to provide commands directly to the executable.

This caused several failed attempts.

I also accidentally typed

```
nc-l
```

instead of

```
nc -l
```

Linux immediately reported

```
Command not found
```

Instead of repeating the same mistake, I carefully read the error message.

After re-reading the challenge statement I realised

> The executable itself is the client.

Therefore

I must become the server.

That completely changed my approach.

---

# ✅ Final Solution Logic

The workflow became

```
Create Listener

↓

Provide Password

↓

Run Listener in Background

↓

Execute suconnect

↓

Connection Established

↓

Password Verified

↓

Bandit21 Password Received
```

No guessing was involved after understanding the architecture.

---

# 🌍 Real-Life Application

Today's concepts are used in

### Authentication Services

Internal programs communicate using localhost instead of exposing services publicly.

---

### Databases

Applications connect to local databases through TCP sockets.

---

### Web Servers

Applications communicate with backend services internally.

---

### Linux Administration

Many management utilities communicate locally using sockets.

---

### Penetration Testing

Netcat is one of the most common tools for

- Enumeration
- Testing
- File transfer
- Reverse shells
- Debugging

---

### Secure Software Design

Privilege separation through SUID helps avoid giving users permanent elevated permissions.

---

# ❌ Mistakes Made Today

## Mistake 1

Misunderstood who should initiate the connection.

Correction

Read the challenge again and identified the executable as the client.

---

## Mistake 2

Typed

```
nc-l
```

instead of

```
nc -l
```

Lesson

Linux commands are extremely syntax-sensitive.

A missing space completely changes command interpretation.

---

## Mistake 3

Initially tried solving mechanically.

Correction

Stopped guessing.

Analysed the communication model.

Solved logically.

---

# 💡 Lessons Learned

Today's biggest lesson

> Understanding system behaviour is far more valuable than memorising commands.

Cybersecurity professionals rarely know every command.

Instead they understand

- how systems communicate
- how privileges work
- how data flows

The commands naturally follow.

---

# 👨‍🏫 Professor Questions & Answers

### Why did `suconnect` connect instead of listening?

Because it acts as the client.

---

### Why must Netcat start first?

Clients cannot connect until a server is already waiting.

---

### Why use localhost?

Communication stays entirely inside the same computer.

---

### Why use a pipeline?

To automatically provide input without manual typing.

---

### Why use background execution?

To free the terminal for executing another command.

---

### Why was SUID required?

To temporarily execute with Bandit21 privileges.

---

### Why is this more secure than giving Bandit20 direct access?

Privilege is delegated only for one controlled executable instead of permanently elevating the user's permissions.

---

# 🔄 Revision (Bandit Level 1–20)

| Command | Purpose |
|----------|---------|
| pwd | Current directory |
| ls | List files |
| cd | Change directory |
| cat | Display file |
| head | Beginning of file |
| tail | End of file |
| grep | Search text |
| find | Locate files |
| sort | Sort data |
| uniq | Remove adjacent duplicates |
| diff | Compare files line-by-line |
| cmp | Compare files byte-by-byte |
| comm | Compare sorted files |
| wc | Count lines/words/bytes |
| tr | Character translation |
| file | Identify file type |
| whoami | Current user |
| id | User & group IDs |
| env | Display environment variables |
| printenv | Print specific environment variables |
| echo | Print text or variables |
| ssh | Secure remote login |
| openssl s_client | Test SSL/TLS services |
| ping | Connectivity test |
| ss | Display socket information |
| nmap | Port scanning |
| nc | TCP/UDP communication |
| `|` | Send output of one command into another |
| `&` | Run command in background |

---

# 📖 Preparation for Bandit Level 21

Required knowledge

- Background jobs
- Shell execution flow
- Basic scripting mindset
- File permissions
- Temporary files
- Reading challenge statements carefully

No new Linux commands are required beyond what has already been learned.

The primary focus should be **understanding the challenge before typing commands**.

---

# 🏁 Key Takeaway

Today's challenge demonstrated that cybersecurity is not about collecting commands.

It is about recognising:

- Who is the client?
- Who is the server?
- Who owns the privilege?
- How does data flow?
- Which tool fits the communication model?

Once those questions are answered, the solution becomes straightforward.

---

**Status:** ✅ Notes023 Completed  
**Bandit Progress:** Level 20 Cleared → Ready for Level 21