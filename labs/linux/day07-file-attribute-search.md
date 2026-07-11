# labs/day07-file-attribute-search.md

# 🧪 Day 7 Lab – Advanced File Search Practice

## Objective

Practice advanced Linux searching using file attributes and complete OverTheWire Bandit Level 6.

---

# Lab 1

Created test files and directories.

Practiced

- file type search
- owner search
- group search
- size search

---

# Lab 2

Combined multiple search conditions.

Example

```bash
find . -type f -size 33c
```

Observation

Combining filters significantly reduces unnecessary search results.

---

# Lab 3

Practiced output redirection.

Example

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

Observation

Permission denied messages disappeared while valid search results remained visible.

---

# Lab 4

Completed OverTheWire Bandit Level 6.

Challenge

Locate a file matching multiple conditions across the filesystem.

Result

Successfully identified the correct file and retrieved the password for the next level.

---

# Problems Faced

- Initially searched only the current directory.
- Forgot the space after the `cat` command.
- Did not understand `2>/dev/null`.

---

# Solution

- Read the challenge carefully.
- Understood filesystem-wide searching.
- Learned Linux output redirection.
- Corrected command syntax.

---

# Skills Gained

- Advanced `find`
- File attribute searching
- Error redirection
- Reading challenge requirements carefully
- Linux troubleshooting

---

# Conclusion

Today's lab demonstrated how Linux administrators and cybersecurity professionals efficiently locate files across large systems using multiple search conditions while filtering unnecessary output.