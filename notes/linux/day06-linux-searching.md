# Day 6 Notes - Linux File Searching

## grep

`grep` searches for specific text inside one or more files.

### Syntax

```bash
grep <pattern> <filename>
```

### Examples

```bash
grep Linux notes.txt
grep -i linux notes.txt
grep -n linux notes.txt
```

### Options

| Option | Meaning |
|---------|---------|
| -i | Ignore uppercase/lowercase |
| -n | Show line numbers |

---

## wc

The `wc` command counts information about files.

### Syntax

```bash
wc filename
```

### Options

```bash
wc -l filename
```

Count lines.

```bash
wc -w filename
```

Count words.

```bash
wc -c filename
```

Count bytes.

---

## find

Searches files and directories recursively.

### Syntax

```bash
find . -name "*.txt"
```

Meaning:

- `.` → Current directory
- `-name` → Search by filename
- `"*.txt"` → Every text file

---

## Wildcards

`*`

Means "anything".

Examples

```bash
*.txt
```

All text files.

```bash
Linux*
```

Everything beginning with Linux.

```bash
*report*
```

Everything containing report.

---

## Important Difference

`find`

Searches files.

`grep`

Searches inside files.

---

## Biggest Lesson

Linux commands are extremely sensitive to spacing.

Example

Incorrect

```bash
find . -name*.txt
```

Correct

```bash
find . -name "*.txt"
```