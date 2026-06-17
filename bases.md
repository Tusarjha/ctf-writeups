Description: Given string:

bDNhcm5fdGgzX3lwcDM1

The challenge hints that it is encoded using bases.

Solution:

Recognize the string as Base64.

Decode it:

echo bDNhcm5fdGgzX3lwcDM1 | base64 -d

Output:

l3arn_th3_r0p35

Submit:

picoCTF{l3arn_th3_r0p35}

Key Concept: Base64 encoding is commonly used in beginner CTF challenges.
