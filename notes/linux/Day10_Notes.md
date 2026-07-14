# Linux Notes - Day 10

# strings

Purpose:
Extract printable ASCII text from binary or non-text files.

Syntax:

```bash
strings filename
```

Useful when investigating binary files or extracting readable information.

---

# Pipeline

Symbol:

```bash
|
```

Purpose:

Send the output of one command directly into another command.

Example:

```bash
strings data.txt | grep password
```

---

# wc

Purpose:

Count information inside a file.

Syntax:

```bash
wc filename
```

Output order:

Lines
Words
Bytes

Useful options:

```bash
wc -l
wc -w
wc -c
```

---

# Combining Commands

Examples:

```bash
strings file
strings file | grep linux
strings file | wc
strings file | sort
strings file | sort | uniq
```

---

# Key Learning

Small Linux commands become powerful when connected together through pipelines.