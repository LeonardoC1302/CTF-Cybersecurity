# Challenge: Neonify

## Description
This challenge involved exploiting an input field that reflected user input into the HTML page. By injecting Ruby code within ERB tags, we were able to read the contents of `flag.txt`.

## Exploitation Process
1. **Analyzing the Input Field**:
   - The input field directly reflected user input into the HTML output.
   - Suspected vulnerability: **Server-Side Template Injection (SSTI)**.

2. **Crafting the Payload**:
   - Attempted `<%= File.open('flag.txt').read %>`, which is an ERB injection.
   - The payload had to be URL-encoded to bypass input validation.

3. **Sending the Exploit**:
   - Used Python's `requests` library to send the payload in the `POST` request.
   - Retrieved the flag from the response.

## Tools Used
- Burp Suite
- Python (`requests` module)

## Vulnerability Classification
- **CWE-79**: Improper Neutralization of Input During Web Page Generation (Cross-Site Scripting - XSS)
- **CAPEC-63**: Cross-Site Scripting (XSS)

## Flag
`HTB{r3pl4c3m3n7_s3cur1ty}`
