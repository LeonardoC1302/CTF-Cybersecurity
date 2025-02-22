# Challenge: PDFy

## Description
This challenge involved exploiting a **Server-Side Request Forgery (SSRF)** vulnerability that allowed us to access system files by tricking the web application into making an internal request.

## Exploitation Process
1. **Identifying the Vulnerability**:
   - The website allowed users to input URLs and generated a PDF preview.
   - The challenge hinted at leaking `/etc/passwd`, suggesting **SSRF**.

2. **Setting Up the Exploit**:
   - Created a PHP script that redirects requests to `file:///etc/passwd`.
   - Hosted the script on a local web server (`php -S`).
   - Used SSH tunneling to expose the server to the internet.

3. **Executing the Exploit**:
   - Submitted the public URL of our hosted script to the PDFy website.
   - The server fetched and included `/etc/passwd` in the generated PDF.
   - Opened the generated PDF to extract the flag.

## Tools Used
- PHP
- SSH Tunneling
- Web Hosting

## Vulnerability Classification
- **CWE-918**: Server-Side Request Forgery (SSRF)
- **CAPEC-664**: Server-Side Request Forgery

## Flag
`HTB{pdF_g3n3r4t1on_g03s_brrr!}`
