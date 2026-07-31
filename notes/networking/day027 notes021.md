# 📘 Notes 021 — Linux File Comparison, Text Processing & Preparation for OverTheWire Bandit Level 18

**Day:** 027

**Category:** Linux • Text Processing • File Analysis • Ethical Hacking

**Status:** Completed

---

# 📌 Overview

Today's learning focused on one of Linux's greatest strengths—processing data efficiently using small, specialised command-line tools.

Instead of manually reading large files, Linux provides utilities that compare, analyse, transform and organise information automatically. These utilities are widely used by system administrators, cybersecurity professionals, digital forensic investigators and penetration testers.

The practical session also demonstrated that understanding *how* a command works is more valuable than simply memorising its syntax.

---

# 1. Linux Philosophy

One of the core design principles of Linux is:

> **"Do one thing, and do it well."**

Every command has a specific purpose.

Examples:

- `diff` → compare text
- `cmp` → compare bytes
- `sort` → arrange data
- `uniq` → remove consecutive duplicates
- `wc` → count information
- `tr` → transform characters

Complex workflows are created by combining simple commands together.

---

# 2. File Comparison

## Why Compare Files?

Professionals compare files to:

- Detect modifications
- Verify configuration changes
- Identify malware alterations
- Compare log files
- Validate backups
- Track software versions

Reading files manually is inefficient.

Linux comparison utilities identify only the differences.

---

# 3. diff

## Purpose

Performs **line-by-line comparison**.

Syntax

```bash
diff file1 file2
```

Example output

```
3c3
< orange
---
> grapes
```

Interpretation

```
Line 3 changed.
```

Best suited for

- Configuration files
- Source code
- Logs
- Text documents

---

## Advantages

✔ Human-readable

✔ Fast

✔ Shows exactly what changed

---

## Limitations

Not suitable for binary files.

---

# 4. cmp

## Purpose

Compares files **byte-by-byte**.

Syntax

```bash
cmp file1 file2
```

Example

```
byte 14 line 3
```

Meaning

The first difference occurs at byte 14.

---

## Best Used For

- Executables
- Images
- PDFs
- Firmware
- Binary data

---

## Difference Between diff and cmp

| diff | cmp |
|------|------|
| Line comparison | Byte comparison |
| Human readable | Technical |
| Text | Binary |

---

# 5. comm

## Purpose

Compares **sorted** files.

Syntax

```bash
comm file1 file2
```

Produces three columns:

Column 1

Only in file 1.

Column 2

Only in file 2.

Column 3

Present in both files.

---

## Important Rule

Both files **must already be sorted**.

Example

```bash
sort file1 > sorted1

sort file2 > sorted2
```

---

# 6. sort

Purpose

Organises data alphabetically or numerically.

Examples

```bash
sort file.txt

sort -n numbers.txt

sort -r file.txt
```

Uses

- Preparing logs
- Cleaning datasets
- Working with comm
- Duplicate removal

---

# 7. uniq

Purpose

Removes consecutive duplicate entries.

Example

```bash
sort file.txt | uniq
```

---

## Practical Observation

Today's experiment intentionally tested `uniq` before sorting.

Observed:

```
APPLE
BANANA
ORANGE
APPLE
```

Duplicate removal failed because identical entries were not adjacent.

After sorting:

```
APPLE
APPLE
BANANA
ORANGE
```

Then

```bash
uniq
```

produced

```
APPLE
BANANA
ORANGE
```

---

## Lesson Learned

`uniq` removes only **adjacent duplicates**, not every duplicate.

Sorting first is essential.

---

# 8. wc

Purpose

Counts information.

Examples

```bash
wc file.txt

wc -l file.txt

wc -w file.txt

wc -m file.txt
```

Applications

- Log analysis
- Script validation
- File statistics

---

# 9. tr

Purpose

Transforms characters.

Example

```bash
tr a-z A-Z
```

Useful for

- Normalising data
- Formatting output
- Preparing text for analysis

---

# 10. Command Pipelines

Linux commands become much more powerful when chained together.

Example

```bash
sort users.txt | uniq | wc -l
```

Workflow

Sort

↓

Remove duplicates

↓

Count unique entries

This modular design is a defining characteristic of Linux.

---

# 11. Practical Cybersecurity Applications

Today's commands are used extensively in professional environments.

## diff

- Detect modified configuration files
- Compare malware samples
- Verify backups

---

## cmp

- Binary integrity checking
- Firmware verification

---

## sort

- Organising reconnaissance data
- Preparing password lists

---

## uniq

- Removing duplicate log entries
- Cleaning datasets

---

## wc

- Counting requests
- Measuring log growth

---

## tr

- Normalising extracted data
- Formatting reconnaissance results

---

# 12. Practical Lessons From Today's Lab

The most valuable observation was not solving Bandit Level 17.

Instead, it was intentionally testing command behaviour.

Experimentation proved that:

Linux utilities are predictable.

They follow clearly defined rules.

Understanding those rules makes future problem-solving significantly easier.

---

# 13. Preparation for Bandit Level 18

Bandit Level 18 introduces a different challenge.

Expected concepts

- Restricted shell behaviour
- Remote login
- Reading files despite restrictions
- Alternative command execution
- Linux startup behaviour

Commands to remember

```bash
ssh

cat

less

more

bash

sh

echo

pwd

ls
```

Do **not** study solutions in advance.

Focus on understanding Linux itself.

---

# 14. Professor Questions (With Answers)

### Q1

Why is `diff` preferred for text?

**Answer**

Because it compares line-by-line and presents changes in a format humans can easily interpret.

---

### Q2

Why does `cmp` stop after the first difference?

**Answer**

Its purpose is binary verification. Once inequality is confirmed, additional comparison is unnecessary.

---

### Q3

Why does `comm` require sorted files?

**Answer**

Because it compares entries sequentially. Without sorting, matching lines may appear in different positions and cannot be aligned correctly.

---

### Q4

Why didn't `uniq` work before sorting?

**Answer**

Because identical entries were separated by different lines. `uniq` removes only consecutive duplicates.

---

### Q5

What is the benefit of command pipelines?

**Answer**

Pipelines allow multiple specialised commands to work together, creating efficient workflows without intermediate files.

---

### Q6

Why is experimentation important?

**Answer**

Experimentation verifies command behaviour and builds understanding beyond memorisation.

---

### Q7

Which comparison command would you use for executable files?

**Answer**

`cmp`

because executables are binary rather than text.

---

### Q8

Which command would you choose for configuration files?

**Answer**

`diff`

because administrators need to know exactly which lines changed.

---

# 15. Revision Checklist

- [x] diff
- [x] cmp
- [x] comm
- [x] sort
- [x] uniq
- [x] wc
- [x] tr
- [x] Command pipelines
- [x] Linux file comparison
- [x] Practical experimentation
- [x] Bandit Level 17
- [x] Bandit Level 18 preparation

---

# 🏁 Conclusion

Today's learning demonstrated that Linux commands become powerful not because they are individually complex, but because they are predictable, specialised and designed to work together.

By understanding command behaviour through experimentation and applying these concepts within Bandit Level 17, today's session strengthened both technical knowledge and analytical thinking.

These concepts form an essential foundation for future Linux administration, scripting, digital forensics and ethical hacking.