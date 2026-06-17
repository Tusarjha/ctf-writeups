Cryptography (Easy) – picoCTF Writeup

The challenge provided a values.txt file and hinted at ROT13 encryption.

ROT13 shifts each letter by 13 positions in the alphabet. I opened the file and decoded the text using a ROT13 decoder (or the command below):

cat values.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

The decoded output revealed the flag.

Key Concept: ROT13 is a simple substitution cipher where applying the cipher twice returns the original text.
