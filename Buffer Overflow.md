picoCTF - Buffer Overflow 0

Category: Binary Exploitation
Difficulty: Medium

Challenge Description

The challenge provides:

A vulnerable binary (vuln)
Source code (vuln.c)
A remote service accessible through netcat

Goal: Trigger the program to print the flag.

Step 1: Inspect the Source Code

After downloading the source code:

wget <source-link>
cat vuln.c

I found the following function:

void vuln(char *input){
    char buf2[16];
    strcpy(buf2, input);
}

Immediately, two things stand out:

Buffer Size
char buf2[16];

The buffer can only hold 16 characters.

Unsafe Copy
strcpy(buf2, input);

strcpy() copies data without checking the size of the destination buffer.

If the input is longer than 16 characters, memory outside the buffer will be overwritten.

This is called a Buffer Overflow.

Step 2: Look for Interesting Behavior

Further inspection revealed:

void sigsegv_handler(int sig) {
    printf("%s\n", flag);
    exit(1);
}

and

signal(SIGSEGV, sigsegv_handler);

The program registers a handler for SIGSEGV (Segmentation Fault).

Normally, a segmentation fault crashes a program.

Here, however, the custom handler prints the flag before exiting.

Therefore:

If I can intentionally crash the program, the flag will be printed.

Step 3: Understand the Vulnerability

Input is taken using:

gets(buf1);

gets() is dangerous because it accepts unlimited input.

Later:

vuln(buf1);

passes the input to:

strcpy(buf2, input);

which copies everything into a 16-byte buffer.

A sufficiently long input will overwrite adjacent memory and eventually crash the program.

Step 4: Connect to the Remote Service
nc saturn.picoctf.net 61055

The service prompts:

Input:
Step 5: Trigger the Overflow

I entered a long string of characters:

AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

(around 50–100 A's works)

The input exceeded the 16-byte buffer size.

This corrupted memory and caused a segmentation fault.

Since the challenge installed a custom SIGSEGV handler, the crash triggered:

sigsegv_handler()

which printed the flag.

Flag
picoCTF{...}
Key Concepts Learned
Buffer

A buffer is a fixed-size memory area used to store data.

Example:

char buf[16];

can store only 16 bytes.

Buffer Overflow

Occurs when more data is written than the buffer can hold.

Example:

char buf[16];
strcpy(buf, "AAAAAAAAAAAAAAAAAAAAAAAAAAAA");

The extra characters overwrite neighboring memory.

gets()
gets(buf);

Dangerous because it does not limit input length.

Modern programs avoid using it.

strcpy()
strcpy(destination, source);

Copies data without checking destination size.

Can cause buffer overflows.

Segmentation Fault (SIGSEGV)

Occurs when a program accesses invalid memory.

Normally:

Segmentation Fault

and the program crashes.

In this challenge:

signal(SIGSEGV, sigsegv_handler);

the crash was intentionally used to print the flag.
