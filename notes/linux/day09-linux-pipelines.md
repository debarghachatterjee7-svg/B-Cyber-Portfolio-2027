# Linux Pipelines, sort & uniq

## Pipe ( | )

The pipe sends the output of one command directly into another command.

Example

```bash
sort fruits.txt | uniq
```

---

## sort

Sorts text alphabetically.

```bash
sort file.txt
```

Reverse order

```bash
sort -r file.txt
```

---

## uniq

Removes consecutive duplicate lines.

```bash
uniq file.txt
```

---

## uniq -u

Displays only lines appearing exactly once.

```bash
sort file.txt | uniq -u
```

---

## Why use sort before uniq?

uniq compares adjacent lines only.

Sorting places identical lines together, allowing uniq to work correctly.

---

## Key Learning

Small Linux commands become powerful when combined using pipelines.