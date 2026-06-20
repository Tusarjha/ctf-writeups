# Static ain't always noise — picoCTF Writeup

**Category:** General Skills  
**Difficulty:** Easy  
**Author:** syreal

---

## Challenge Description

> Can you look at the data in this binary? The bash script might help!

Two files are provided: `static` (a binary) and `ltdis.sh` (a bash script that disassembles it).

---

## Solution

Binaries often contain embedded readable strings — things like error messages, URLs, and sometimes even flags. The `strings` command extracts all human-readable text from a binary file.

Since we're looking for the picoCTF flag, we can pipe the output directly into `grep`:

```bash
strings static | grep "picoCTF"
```

This instantly reveals the flag embedded in the binary.

---

## Flag

```
picoCTF{d15a5m_t34s3r_20335e41}
```

---

## Key Takeaway

Not all "static" is noise — binaries frequently contain plaintext strings that can be extracted without any disassembly or reverse engineering. `strings` is one of the first tools to reach for when analyzing an unknown binary.
