# PW Crack 4 — picoCTF

**Category:** General Skills
**Difficulty:** Medium
**Points:** 100

## Problem
Crack the correct password from 100 possibilities to decrypt 
the flag. The password checker uses MD5 hashing to verify.

## My Approach

### Step 1 — Downloaded the files
```bash
wget [level4.py URL]
wget [level4.flag.txt.enc URL]  
wget [level4.hash.bin URL]
```

### Step 2 — Analyzed the script
Read the checker script using `cat level4.py` and understood:
- It hashes the input password using MD5
- Compares it against stored hash in level4.hash.bin
- If match found, decrypts flag using XOR

### Step 3 — Ran the brute force
The script already contained the 100 possible passwords and 
a for loop to try each one. Ran `python3 level4.py` and pressed 
Enter for blank input — which revealed the brute force output.

**Password found: 973a**

## Unexpected Discovery
Pressing blank Enter bypassed the manual password check, and 
the brute force loop ran automatically — revealing the correct 
password and decrypted flag instantly.

This maps to a real vulnerability called **Empty Password 
Authentication Bypass** — where systems accept blank inputs 
due to developer oversight. Many real routers, databases and 
admin panels have been compromised this way.

## What I Learned
- MD5 hashing and hash comparison for authentication
- Brute force password cracking using Python loops
- XOR decryption technique
- Empty/null password vulnerabilities in real systems
- Reading and understanding existing Python scripts

## Flag
`picoCTF{fl45h_5pr1ng1ng_ae0fb77c}`
