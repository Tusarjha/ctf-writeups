# PW Crack 4 — picoCTF

**Category:** General Skills  
**Difficulty:** Medium  
**Points:** 100

## Problem
Crack the correct password from 100 possibilities to decrypt 
the flag using MD5 hashing.

## My Approach

### Step 1 — Downloaded all three files
```bash
wget [level4.py URL]
wget [level4.flag.txt.enc URL]
wget [level4.hash.bin URL]
```

### Step 2 — Analyzed the script
Used `cat level4.py` to read the checker. Understood:
- Password is hashed using MD5
- Hash compared against stored hash in level4.hash.bin
- 100 possible passwords already listed in the script
- Brute force loop already written at the bottom

### Step 3 — Ran the script
```bash
python3 level4.py
```
Entered any wrong password → script automatically ran the 
brute force loop through all 100 passwords → found match.

**Correct password: 973a**

## What I Learned
- MD5 password hashing and verification
- Brute force cracking using Python for loops
- XOR decryption
- How to read and understand existing Python scripts
- Hash comparison for authentication systems

## Flag
`picoCTF{fl45h_5pr1ng1ng_ae0fb77c}`
