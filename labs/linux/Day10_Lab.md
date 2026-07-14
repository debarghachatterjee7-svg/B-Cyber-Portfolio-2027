# Linux Lab - Day 10

## Objective

Practice extracting readable text and combining Linux commands using pipelines.

---

## Experiments Performed

### Experiment 1

Extract readable strings.

```bash
strings notes.txt
```

---

### Experiment 2

Search extracted text.

```bash
strings notes.txt | grep linux
```

---

### Experiment 3

Count output.

```bash
strings notes.txt | wc
```

---

### Experiment 4

Sort extracted text.

```bash
strings notes.txt | sort
```

---

### Experiment 5

Sort and remove duplicate lines.

```bash
strings notes.txt | sort | uniq
```

---

## Mistakes

Typed:

```bash
strings notes.txt | ec
```

Result:

```
command not found
```

Correction:

Used the correct Linux command and continued the experiment.

---

## Conclusion

Today's laboratory demonstrated how Linux pipelines allow multiple commands to work together efficiently for text processing.