# Secure Shell — picoCTF
# Category: General Skills
# Difficulty: Easy

# Challenge Description
Connect to a remote server using SSH with a provided username, password, and port number to retrieve the flag.

# My Approach
Step 1 - Launch the Instance
Clicked Launch Instance on the challenge page and noted the credentials — hostname, port, username, and password.
Step 2 - Connect via SSH
Used the user@host format with -p to specify the non-default port:

ssh ctf-player@titan.picoctf.net -p <port>
Step 3 - Enter the Password
When prompted, typed the password. The input stayed invisible — that's normal shell behavior for passwords.
Step 4 - Retrieve the Flag
The flag was either printed automatically on login or read from a file using:

cat flag.txt

# Flag
Not recorded

# What I learned

How to connect to a remote machine using SSH
Using -p flag to specify a custom port
Passwords typed in a shell are hidden but still being registered
Basic user@hostname syntax for remote login
