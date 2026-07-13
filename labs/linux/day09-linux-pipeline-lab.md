# Linux Pipeline Lab

## Objective

Practice combining Linux commands using pipelines.

---

## Commands Used

```bash
sort fruits.txt

sort -r fruits.txt

uniq fruits.txt

sort fruits.txt | uniq

sort fruits.txt | uniq -u
```

---

## Experiment

Created a text file containing duplicate entries.

Observed the difference between:

- uniq
- sort | uniq
- sort | uniq -u

---

## Observation

sort prepares the data.

uniq filters duplicates.

Pipelines combine both commands into a single workflow.

---

## Conclusion

Linux pipelines simplify complex tasks by connecting specialized commands together.