# Day 13 Lab – Hexadecimal Reconstruction & Archive Extraction

## Objective

The objective of today's practical session was to convert hexadecimal data back into binary format, identify unknown files using Linux utilities and extract multiple layers of compressed archives. The practical also improved my confidence with Linux command-line tools and file processing.

---

## Practical Work

Created sample text files and viewed their hexadecimal representation using the `xxd` command.

Practiced converting hexadecimal data back into binary using the reverse option.

Used the `file` command repeatedly to determine the actual type of unknown files.

Worked with multiple Linux archive formats including gzip, bzip2 and tar.

Repeated the identification and extraction process several times until the final ASCII text containing the password was recovered.

---

## Commands Practiced

```bash
xxd
file
mv
ls
cat
gzip
gunzip
bzip2
bunzip2
tar
```

---

## Observations

The archive extraction process followed a logical sequence. Each extracted file revealed another archive or compressed format, requiring another round of identification before extraction. This showed the importance of using the `file` command rather than relying only on file extensions.

---

## Mistakes Faced

Initially there was confusion while deciding which extraction utility should be used next because multiple archive formats were nested together. Some files also needed to be renamed before Linux utilities could recognize them properly.

---

## Learning Outcome

By the end of the lab I understood how hexadecimal files can be reconstructed into binary, how Linux identifies unknown files and how several archive utilities work together to extract nested compressed data. This practical also introduced a workflow commonly used in digital forensics and cybersecurity investigations.

---

## Skills Developed

- Hexadecimal processing
- Binary reconstruction
- File identification
- Archive extraction
- Linux command-line usage
- Logical troubleshooting
- Digital forensics workflow

---

## Conclusion

Today's lab combined several Linux concepts into a single workflow. Instead of using isolated commands, I learned how different Linux utilities work together to solve a real-world problem. Successfully completing the extraction process strengthened my understanding of file handling and archive management in Linux.