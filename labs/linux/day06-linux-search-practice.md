# Day 6 Lab - Linux Search Practice

## Objective

Practice searching files and text using Linux commands.

---

## Commands Practiced

```bash
grep Linux linux.txt
grep -i linux notes.txt
grep -n linux notes.txt

wc linux.txt
wc -l linux.txt
wc -w linux.txt
wc -c linux.txt

find . -name "*.txt"

ls *.txt
```

---

## Practical Tasks

- Created multiple text files
- Searched text inside files
- Counted lines, words and bytes
- Used wildcard matching
- Searched files recursively
- Completed OverTheWire Bandit Level 5

---

## Mistakes Encountered

### Mistake 1

```bash
grep linux.txt
```

Forgot the search pattern.

Correct

```bash
grep Linux linux.txt
```

---

### Mistake 2

```bash
find . -name*.txt
```

Forgot space.

Correct

```bash
find . -name "*.txt"
```

---

## Result

Successfully completed all Linux practice exercises and solved OverTheWire Bandit Level 5.