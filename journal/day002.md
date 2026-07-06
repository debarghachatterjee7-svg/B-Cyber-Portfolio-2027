# Day 2 – Linux Navigation & Understanding the Linux File System

**Date:** 06 July 2026  
**Time Invested:** 2 Hours

---

# 🎯 Goal

Today's objective was to understand how Linux organizes files and directories, become comfortable navigating through the terminal, learn the difference between the Root and Home directories, practice basic file management commands, and complete OverTheWire Bandit Level 2 by understanding how Linux interprets filenames.

---

# 📚 Theory Learned

Today I learned that Linux is much more than just a command-line interface. It is an operating system that organizes every file and directory in a tree-like structure.

Unlike Windows, where we usually think in terms of different drives (C:, D:, etc.), Linux starts everything from a single directory called the **Root Directory (`/`)**. Every file, folder, application, and user exists somewhere under this root.

I also learned that every user has their own **Home Directory**, which acts as their personal workspace. My home directory is:

```
/home/sonu
```

This is where I normally create files, folders, and projects.

I understood the purpose of several important system directories:

| Directory | Purpose |
|------------|---------|
| `/` | Root Directory (starting point of the Linux file system) |
| `/home` | Stores users' personal directories |
| `/etc` | Stores system configuration files |
| `/usr` | Contains installed applications and libraries |
| `/var` | Stores variable data such as logs |
| `/tmp` | Stores temporary files |

Although I still need practice remembering `/etc`, `/usr`, `/var`, and `/tmp`, I now understand why they exist.

---

# 💻 Commands Learned

| Command | Purpose |
|---------|---------|
| `pwd` | Displays the current working directory |
| `ls` | Lists files and folders in the current directory |
| `ls -a` | Displays all files, including hidden files |
| `ls -la` | Displays detailed information about all files |
| `cd` | Changes the current directory |
| `mkdir` | Creates a new directory |
| `touch` | Creates an empty file |
| `cat` | Displays the contents of a file |
| `cp` | Creates a copy of a file |
| `mv` | Moves or renames a file |
| `rm` | Deletes a file |

---

# 🧪 Practical Work

Today I created my own Linux practice environment.

```
CyberLab
│
├── Notes
├── Practice
├── note.txt
└── password.txt
```

During practice I:

- Created directories using `mkdir`
- Created empty files using `touch`
- Navigated between directories using `cd`
- Verified my location using `pwd`
- Viewed directory contents using `ls`
- Copied files using `cp`
- Renamed files using `mv`
- Deleted files using `rm`
- Learned how `cat` displays the contents of a file

This practical session helped me understand that Linux commands become much easier once I understand how the file system is organized.

---

# 🚩 Bandit Progress

### Completed

✅ Bandit Level 1

✅ Bandit Level 2

Bandit Level 2 was significantly more challenging than Level 1.

Initially, I didn't understand why:

```bash
cat -
```

did not work.

Later, I learned that Linux interprets `-` as a special argument rather than a filename.

Using:

```bash
cat ./-
```

worked because `./` explicitly tells Linux to look for the file named `-` inside the current directory.

This was my first experience of understanding how Linux interprets command-line arguments instead of simply executing commands.

---

# 🔬 Experiments

## Experiment 1 — Root Directory

### Commands

```bash
cd /
pwd
```

### Prediction

I expected Linux to move me to the Root Directory.

### Observation

Output:

```
/
```

### Conclusion

The Root Directory (`/`) is the highest level of the Linux file system.

---

## Experiment 2 — Home Directory

### Commands

```bash
cd ~
pwd
```

### Prediction

I expected Linux to return to my Home Directory.

### Observation

Output:

```
/home/sonu
```

### Conclusion

The `~` symbol is a shortcut that always points to the current user's Home Directory.

---

## Experiment 3 — Parent Directory

### Commands

```bash
cd ..
pwd
```

### Prediction

I expected Linux to move one level upward.

### Observation

Output:

```
/home
```

### Conclusion

`..` always represents the parent directory.

---

## Experiment 4 — Command Syntax

I intentionally tried several incorrect commands.

```bash
cd/pwd
```

```bash
cd /pwd
```

```bash
cd ~pwd
```

```bash
cd ~ pwd
```

### Observation

Linux returned errors such as:

- No such file or directory
- too many arguments

The commands worked correctly only when written separately:

```bash
cd /
pwd
```

### Conclusion

I learned that spaces are extremely important in Linux. Every command and every argument must be separated correctly. Even a small syntax mistake completely changes how Linux interprets the command.

---

# 🌟 Biggest Learning

Today I realized that Linux is not about memorizing commands.

Every command interacts with the Linux file system, and understanding concepts like the Root Directory, Home Directory, current directory, and file paths makes the commands much easier to remember.

I also learned that Linux interprets symbols like `.`, `..`, `~`, and `-` differently depending on the context.

---

# 😵 Biggest Confusion

The most difficult part of today's session was solving OverTheWire Bandit Level 2.

I also found it difficult to remember the purposes of system directories such as:

- `/etc`
- `/usr`
- `/var`
- `/tmp`

Since they all seemed similar initially, I will need more practice before they become familiar.

---

# ❓ Questions I Still Have

- Why does Linux treat `-` as a special symbol?
- Why are configuration files stored inside `/etc`?
- How does Linux know where every file is located?
- Why doesn't Linux display my password while typing?

---

# 🎓 Professor Questions

After today's lesson I should be able to answer:

1. What is the difference between the Root Directory and the Home Directory?

2. What is the purpose of `pwd`?

3. What is the difference between `pwd` and `ls`?

4. Why are hidden files hidden?

5. What does the `cat` command do?

6. Why did `cat ./-` work while `cat -` behaved differently?

7. What is the purpose of `mkdir`, `touch`, `cp`, `mv`, and `rm`?

8. Why is correct spacing important in Linux commands?

---

# 💭 Reflection

Today's session felt much more practical than Day 1.

Instead of simply typing commands, I spent time understanding why each command exists and how Linux interprets them.

The most valuable lesson today was realizing that Linux is very strict about syntax. Missing spaces or incorrect paths completely change the meaning of a command.

Bandit Level 2 was frustrating at first, but solving it helped me understand that Linux doesn't just execute commands—it interprets every argument according to predefined rules.

Although remembering the purposes of `/etc`, `/usr`, `/var`, and `/tmp` is still challenging, I now have a much clearer picture of how the Linux file system is organized.

I feel significantly more comfortable using the terminal than I did yesterday.

---

# 📊 Knowledge Score (Self Assessment)

| Topic | Rating |
|--------|--------|
| Linux File System | ⭐⭐⭐⭐☆ |
| Terminal Navigation | ⭐⭐⭐⭐☆ |
| Linux Commands | ⭐⭐⭐☆☆ |
| Understanding Paths | ⭐⭐⭐⭐☆ |
| OverTheWire | ⭐⭐⭐☆☆ |
| Git & GitHub | ⭐⭐☆☆☆ |
| Overall Confidence | ⭐⭐⭐☆☆ |

---

# 🎯 Tomorrow's Goal

- Become faster with today's commands without referring to notes.
- Learn additional Linux file management commands.
- Understand how Linux reads and writes file contents.
- Complete the next OverTheWire Bandit level.
- Make fewer syntax mistakes while using the terminal.