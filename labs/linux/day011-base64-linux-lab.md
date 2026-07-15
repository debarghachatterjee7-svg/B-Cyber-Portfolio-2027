# Day 11 Lab — Base64 Encoding, Character Translation & Linux Text Processing

## Objective

Practice Linux text-processing commands, Base64 encoding/decoding, character translation, CSV field extraction, and command pipelines.

---

# Files Created

```
employees.csv
cities.txt
message.txt
```

---

# Commands Practiced

## Base64

```bash
base64 file.txt
```

```bash
base64 -d file.txt
```

---

## tr

```bash
echo "linux" | tr a-z A-Z
```

```bash
echo "HELLO" | tr A-Z a-z
```

```bash
echo "banana" | tr -d a
```

```bash
echo "Linux is Awesome" | tr " " "-"
```

---

## cut

```bash
cut -d "," -f1 employees.csv
```

```bash
cut -d "," -f4 employees.csv
```

```bash
cut -d "," -f2,3 employees.csv
```

---

## strings

```bash
strings message.txt
```

---

## Pipelines

```bash
cat employees.csv | cut -d "," -f3 | sort | uniq
```

```bash
cat employees.csv | cut -d "," -f4
```

---

# Observations

- Base64 decoding requires correct command syntax (`-d`).
- `tr` performs character-by-character translation.
- `cut` extracts specific fields from structured text.
- Pipelines allow commands to work together efficiently.
- Linux error messages are useful for debugging syntax mistakes.

---

# Result

Successfully completed all planned Linux exercises and OverTheWire Bandit Level 10 while improving confidence with Linux text-processing commands.