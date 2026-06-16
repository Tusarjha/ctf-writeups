# Undo — picoCTF

**Category:** General Skills  
**Difficulty:** Easy  
**Points:** 100

## Challenge Description
Reverse a series of Linux text transformations to recover the original flag.

## My Approach

### Step 1 - Base64 Decoding
The hint said Base64 was applied. I reversed it using:
`echo "encoded text" | base64 -d`

### Step 2 - Reversed Text
The text was reversed. Used `rev` to fix it.

### Step 3 - Character Replacement
Dashes replaced underscores. Used `tr '-' '_'`

### Step 4 - Curly Braces
Parentheses replaced curly braces. Used `tr '()' '{}'`

### Step 5 - ROT13
ROT13 was applied. Reversed using:
`tr 'A-Za-z' 'N-ZA-Mn-za-m'`

## Flag
`picoCTF{your_flag_here}`

## What I learned
- How Base64 encoding/decoding works
- The `tr` command for character replacement
- ROT13 cipher and how to reverse it
- How attackers use obfuscation to hide data
