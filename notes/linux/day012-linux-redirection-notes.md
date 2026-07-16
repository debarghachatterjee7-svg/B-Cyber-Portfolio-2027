# Linux Standard Streams

Linux programs communicate using three standard streams.

## stdin (0)

Input provided to a program.

Usually the keyboard.

---

## stdout (1)

Normal output.

Example:

```bash
echo Hello
```

Prints:

```
Hello
```

---

## stderr (2)

Error output.

Example:

```bash
cat abc.txt
```

If the file does not exist:

```
No such file or directory
```

This message is sent through stderr.

---

# Redirection

## >

Redirect stdout.

```bash
echo Hello > file.txt
```

---

## 2>

Redirect stderr.

```bash
cat abc.txt 2> errors.txt
```

---

## Why This Matters

Separating output from errors makes debugging easier and is widely used in shell scripting, automation, and cybersecurity workflows.