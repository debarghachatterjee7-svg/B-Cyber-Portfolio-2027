# Day 11 Notes — Base64, tr & Linux Text Processing

# Base64

Base64 is an encoding technique used to convert binary or special data into readable ASCII text.

It is **NOT encryption**.

Anyone can decode Base64 data.

Example:

Original

```
Hello
```

Encoded

```
SGVsbG8=
```

Decode

```
Hello
```

---

# Encoding vs Encryption

Encoding

- Easily reversible
- Used for data transfer
- No secret key

Encryption

- Protects confidentiality
- Requires a key
- Used for secure communication

---

# Base64 Commands

Encode

```bash
base64 file.txt
```

Decode

```bash
base64 -d file.txt
```

Help

```bash
base64 --help
```

---

# tr Command

Translate characters.

Uppercase

```bash
echo "linux" | tr a-z A-Z
```

Lowercase

```bash
echo "HELLO" | tr A-Z a-z
```

Delete characters

```bash
echo "banana" | tr -d a
```

Replace spaces

```bash
echo "Linux is Awesome" | tr " " "-"
```

---

# cut Revision

Extract first column

```bash
cut -d "," -f1 employees.csv
```

Extract fourth column

```bash
cut -d "," -f4 employees.csv
```

Extract multiple columns

```bash
cut -d "," -f2,3 employees.csv
```

---

# Pipelines

Examples

```bash
cat employees.csv | cut -d "," -f3 | sort | uniq
```

```bash
strings message.txt | grep Linux
```

---

# Key Takeaways

- Base64 is encoding, not encryption.
- Linux command syntax is extremely important.
- Pipelines combine simple commands into powerful workflows.
- Reading terminal errors carefully often leads directly to the solution.