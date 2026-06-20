Magikarp Ground Mission – Writeup

Category: General Skills (Linux)
Difficulty: Easy

Approach

After connecting through SSH using the provided credentials:

ssh ctf-player@wily-courier.picoctf.net -p <port>

I listed the files in the starting directory:

ls

Output:

1of3.flag.txt
instructions-to-2of3.txt

Reading the instruction file:

cat instructions-to-2of3.txt

gave the hint:

Next, go to the root of all things, more succinctly "/"

I moved to the root directory:

cd /

Then listed its contents:

ls

and found:

2of3.flag.txt
instructions-to-3of3.txt

Reading the next instruction file revealed the location of the final flag piece. Following the path and reading the files with cat provided all three flag fragments.

Finally, I combined:

1of3.flag.txt
2of3.flag.txt
3of3.flag.txt

to obtain the complete flag.

Key Learning

This challenge was mainly about:

Connecting to a remote machine using SSH
Navigating directories with cd
Viewing files with cat
Understanding the Linux filesystem, especially the root directory (/)
Following clues through multiple locations to reconstruct a flag
