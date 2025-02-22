# Challenge: Behind the Scenes

## Description
This challenge required reverse engineering a binary file to extract a hidden password and use it to reveal the flag.

## Exploitation Process
1. **Analyzing the Binary**:
   - The binary required a password as a command-line argument.
   - Running `strings ./behindthescenes` revealed potential interesting strings.
   - Found references to `strncmp()` and `strlen()`, suggesting string comparisons.

2. **Reverse Engineering**:
   - Used `ltrace` to check function calls but encountered SIGILL (Illegal Instruction).
   - Decompiled the binary using **Ghidra**.
   - Found multiple `strncmp()` calls comparing the input to a hardcoded password.

3. **Extracting the Password**:
   - The password was broken into multiple segments checked with `strncmp()`.
   - Reassembled: `"Itz_0nLy_UD2"`.

4. **Executing the Exploit**:
   - Running `./behindthescenes "Itz_0nLy_UD2"` revealed the flag.

## Tools Used
- Ghidra
- Strings
- Ltrace

## Vulnerability Classification
- **CWE-798**: Use of Hardcoded Credentials
- **CAPEC-191**: Read Sensitive Constants Within an Executable

## Flag
`HTB{Itz_0nLy_UD2}`
