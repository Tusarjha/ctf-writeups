# PW Crack 5 - Writeup

## Challenge

The challenge provided:

* `level5.py`
* `level5.hash.bin`
* `level5.flag.txt.enc`
* `dictionary.txt`

The hints mentioned using the provided dictionary and hashing words after removing whitespace.

## Analysis

Reading `level5.py` showed that the program:

1. Takes a password as input.
2. Computes its MD5 hash.
3. Compares the generated hash with the hash stored in `level5.hash.bin`.

The file `dictionary.txt` contained all possible password candidates (0000–65535).

Since the correct password hash was known, the solution was to perform a dictionary attack.

## Solution

Created a Python script that:

1. Opens `dictionary.txt`.
2. Reads each password candidate.
3. Removes newline characters using `strip()`.
4. Generates its MD5 hash.
5. Compares the generated hash with the target hash from `level5.hash.bin`.
6. Prints the password when a match is found.

After obtaining the correct password, ran:

```bash
python3 level5.py
```

Entered the discovered password and received the flag.

## Concepts Learned

* MD5 hashing
* Dictionary attacks
* Reading files in Python
* Comparing hashes
* Password cracking using a wordlist

## Key Takeaway

Hashes are not reversed directly. Instead, candidate passwords are hashed and compared against the target hash until a match is found.
