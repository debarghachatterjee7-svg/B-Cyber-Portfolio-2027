# Day 13 Notes – Hexadecimal Processing & Linux Archive Utilities

## Overview

Today I learned how Linux represents binary data using hexadecimal and how different archive formats are handled. I also learned that Linux does not simply trust file extensions. Instead, it checks the internal file signature to determine the actual file type. This concept is very important in Linux administration, cybersecurity and digital forensics.

---

## Hexadecimal

Hexadecimal (Hex) is a base-16 numbering system that is commonly used to represent binary data in a shorter and more readable form.

Example:

HELLO

becomes

48 45 4C 4C 4F

Every hexadecimal digit represents 4 binary bits, meaning one byte is represented by two hexadecimal digits.

---

## xxd Command

The `xxd` command is used to display the hexadecimal representation of a file.

Syntax

```bash
xxd filename
```

Example

```bash
xxd hello.txt
```

It can also reverse hexadecimal back into binary.

```bash
xxd -r input.txt output
```

The `-r` option means reverse.

---

## file Command

The `file` command determines the real type of a file.

Syntax

```bash
file filename
```

Example

```bash
file data
```

Possible outputs:

- ASCII text
- gzip compressed data
- bzip2 compressed data
- POSIX tar archive
- executable

---

## Linux Compression Utilities

### gzip

Compresses files.

```bash
gzip filename
```

Extract

```bash
gunzip filename.gz
```

---

### bzip2

Compress

```bash
bzip2 filename
```

Extract

```bash
bunzip2 filename.bz2
```

---

### tar

Create archive

```bash
tar -cf archive.tar folder/
```

Extract archive

```bash
tar -xf archive.tar
```

---

## Workflow Learned

Unknown File

↓

file

↓

Identify format

↓

Rename if necessary

↓

Extract

↓

Repeat until plain text

---

## Commands Learned Today

- xxd
- file
- gzip
- gunzip
- bzip2
- bunzip2
- tar
- mv
- ls
- cat

---

## Important Learning

Today I learned that Linux utilities work together rather than independently. Instead of guessing the next command, the correct approach is to first identify the file type and then use the appropriate extraction utility. This systematic workflow is commonly used in cybersecurity investigations and makes handling unknown files much easier.

---

## Summary

Today's lesson connected hexadecimal processing with Linux archive handling. I learned how binary files can be represented as hexadecimal, converted back into their original form, identified correctly using the `file` command and extracted layer by layer until the original text is obtained.