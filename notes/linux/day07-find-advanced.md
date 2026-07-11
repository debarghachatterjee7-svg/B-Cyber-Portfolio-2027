# notes/day07-find-advanced.md

# 📚 Day 7 Notes – Advanced Linux File Searching

## Topics Covered

- Searching by owner
- Searching by group
- Searching by size
- Searching by permissions
- Searching by type
- Combining search filters
- Output Redirection
- Standard Output vs Standard Error
- `/dev/null`

---

# File Searching

Search by owner

```bash
find . -user username
```

Search by group

```bash
find . -group groupname
```

Search by size

```bash
find . -size 33c
```

Search by permissions

```bash
find . -perm 644
```

Search by file type

```bash
find . -type f
```

---

# Combining Conditions

Linux allows combining multiple filters together.

Example

```bash
find . -user bandit7 -group bandit6 -size 33c
```

Each additional filter reduces the number of matching files.

---

# Output Redirection

Linux has three standard streams.

| Stream | Number |
|---------|--------|
| Standard Input | 0 |
| Standard Output | 1 |
| Standard Error | 2 |

Redirect errors

```bash
2>/dev/null
```

Purpose

Hide error messages while displaying only useful output.

---

# Key Learning

Good Linux users solve problems by combining simple commands rather than memorizing complicated ones.