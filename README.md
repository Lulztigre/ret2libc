# ret2libc
Pwn all the Things.
======================

This repository showcases two classic buffer overflow exploitation techniques: ret2win and ret2libc.

ret2win: In this exploit, the goal is to overwrite the return address on the stack with the address of a specific function, win(), which executes the desired payload. This approach avoids the need for any external libraries, making it simple and direct.

ret2libc: In contrast, the ret2libc exploit leverages functions from the C standard library (libc) to bypass protections like non-executable stacks. Instead of jumping directly to a specific function, the exploit leaks the address of puts() from the Global Offset Table (GOT), calculates the base address of libc, and redirects execution to system("/bin/sh") by leveraging known libc offsets. This is a more advanced technique and is often used when the target binary does not have a straightforward "win" function.
