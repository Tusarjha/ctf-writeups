Secure Shell — picoCTF
Category: General Skills

Difficulty: Easy

# What the challenge said
Connect to a remote server at titan.picoctf.net using SSH with a given username, port, and password.

# How I solved it
Launched the instance, noted the credentials, then ran:
bash
'ssh ctf-player@titan.picoctf.net -p 58229'
Entered the password when prompted (hidden input) and the flag was printed on login.

# Flag
Not recorded

# What I learned
SSH lets you log into remote machines using user@host -p port syntax; passwords typed into the shell are invisible by design.
