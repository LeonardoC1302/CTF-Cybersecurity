# Challenge: Bypass

## Description
This challenge involved analyzing a Windows executable (`bypass.exe`) using **Wine** and **OllyDbg** to retrieve embedded sensitive data.

## Exploitation Process
1. **Identifying the File Type**:
   - Used `file bypass.exe` to determine it was a 32-bit Windows PE file.
   - Installed Wine and Wine Mono to run and debug it.

2. **Debugging with OllyDbg**:
   - Opened `bypass.exe` in **OllyDbg**.
   - Examined execution flow and memory regions.
   - Located readable strings in the **dump section**.

3. **Extracting the Flag**:
   - The flag was found as a plaintext string stored in memory.

## Tools Used
- Wine
- Wine Mono
- OllyDbg
- Vim (for formatting extracted data)

## Vulnerability Classification
- **CWE-312**: Cleartext Storage of Sensitive Information
- **CAPEC-37**: Retrieve Embedded Sensitive Data

## Flag
`HTB{SuP3rC00lFL4g}`
