# Challenge: Jscalc

## Description
This challenge involved exploiting a web application that evaluated user input using JavaScript's `eval()` function. By injecting Node.js commands, we were able to read `flag.txt`.

## Exploitation Process
1. **Identifying the Vulnerability**:
   - The application was built with **Next.js** and had an input field for calculations.
   - A hint on the page mentioned `eval()`, which indicated a possible **Code Injection** vulnerability.

2. **Constructing the Exploit**:
   - JavaScript allows file system access in Node.js using `require('fs').readFileSync('/flag.txt')`.
   - This payload was inserted into the request body.

3. **Executing the Exploit**:
   - Used Burp Suite to capture and modify the request.
   - Sent a `POST` request with the crafted payload.
   - The flag appeared in the server response.

## Tools Used
- Burp Suite
- Python (`requests` module)

## Vulnerability Classification
- **CWE-94**: Improper Control of Generation of Code (Code Injection)
- **CAPEC-242**: Code Injection

## Flag
`HTB{c4lcul4t3d_my_w4y_thr0ugh_rc3}`
