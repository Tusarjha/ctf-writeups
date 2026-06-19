# Big Zip Files - Writeup

## Challenge

A ZIP file named `big-zip-files.zip` was provided. The goal was to find the hidden flag inside a large directory structure.

## Initial Mistake

Tried searching directly inside the ZIP file:

```bash
grep picoCTF big-zip-files.zip
grep -r picoCTF big-zip-files.zip
```

This did not work because a ZIP file is a compressed archive, not a normal directory or text file.

## Solution

First create a directory for extraction:

```bash
mkdir extracted
```

Extract the ZIP file:

```bash
unzip big-zip-files.zip -d extracted
```

Now search recursively through all extracted files:

```bash
grep -r "picoCTF" extracted
```

The recursive search traversed all nested directories and located the file containing the flag.

## Commands Learned

Create directory:

```bash
mkdir extracted
```

Extract ZIP into a directory:

```bash
unzip file.zip -d extracted
```

Recursive grep search:

```bash
grep -r "text" extracted
```

List all files recursively:

```bash
find extracted
```

## Key Takeaway

`grep` cannot search inside a compressed ZIP archive directly.

Correct workflow:

```text
ZIP File
   ↓
Unzip
   ↓
Directory Structure
   ↓
grep -r
   ↓
Find Flag
```
