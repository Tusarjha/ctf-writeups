# Secure Shell (SSH) — picoCTF

**Category:** General Skills  
**Difficulty:** Easy  
**Points:** 100

## Problem
Connect to a remote server using SSH as user `ctf-player` 
on a specific port to retrieve the flag.

## Solution
Launched the instance to get connection details, then ran:

```bash
ssh ctf-player@titan.picoctf.net -p 58229
```
Accepted the fingerprint by typing `yes`.
Entered password `1db87a14` when prompted.
Flag appeared directly in the terminal.

## What I learned
- SSH (Secure Shell) is used to remotely access computers securely
- `-p` flag specifies a custom port
- Passwords are hidden while typing in terminal — that's normal
- SSH runs on port 22 by default but can use any port
