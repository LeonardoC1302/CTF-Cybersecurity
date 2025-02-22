# Challenge: Execute

## Description
This challenge involved exploiting a buffer overflow vulnerability to execute arbitrary shellcode, bypassing a blacklist of restricted bytes.

## Exploitation Process
1. **Analyzing the Binary**:
   - The provided source code showed a function that received user input and executed it.
   - **NX (No-Execute) was disabled**, allowing execution of shellcode on the stack.

2. **Crafting the Exploit**:
   - The input was filtered against a **blacklist** of restricted bytes.
   - Created a shellcode payload that avoided these bytes using:
     - **XOR encoding** to bypass bad characters.
     - **Stack manipulation** (`push`/`pop`) instead of direct null-byte assignments.
     - **Incrementing register values** instead of direct assignments.

3. **Executing the Exploit**:
   - Connected to the remote server.
   - Sent the shellcode payload.
   - Spawned a shell and read the flag using `cat flag.txt`.

## Tools Used
- PWNTools (Python)
- Assembly (x86-64)
- GDB for debugging

## Vulnerability Classification
- **CWE-119**: Improper Restriction of Operations within the Bounds of a Memory Buffer
- **CAPEC-100**: Overflow Buffers

## Flag
`HTB{wr1t1ng_sh3llc0d3_1s_s0_c00l}`
