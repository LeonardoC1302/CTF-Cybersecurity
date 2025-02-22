# Challenge: Spooky License

## Description
This challenge involved reverse engineering a license verification system that checked a user-supplied license key. We used symbolic execution with **angr** to generate a valid key.

## Exploitation Process
1. **Analyzing the Binary**:
   - Used `file` to determine it was a **64-bit stripped binary**.
   - Loaded it into **Ghidra** for decompilation.
   - Identified a condition that validated a 32-character license key.

2. **Automating Key Generation with angr**:
   - Created an **angr** project to explore possible inputs.
   - Defined:
     - `exit_point`: Address of successful license validation.
     - `avoid_point`: Address of "Invalid License Format" message.
   - Used **angr** to generate a valid key.

3. **Executing the Exploit**:
   - Ran the script to compute the correct key.
   - Passed the key as an argument to the binary to retrieve the flag.

## Tools Used
- angr
- IPython
- Ghidra

## Vulnerability Classification
- **CWE-327**: Use of a Broken or Risky Cryptographic Algorithm
- **CAPEC-20**: Encryption Brute Forcing

## Flag
`HTB{The_sp0000000key_liC3nC3K3Y}`
