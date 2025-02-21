# Project 2 - Capture The Flag (CTF) - Hack The Box

This repository contains documentation and exploits developed for solving various security challenges on the Hack The Box platform. These challenges were tackled as part of the Software Security - IC8071 course at the Costa Rica Institute of Technology.

## Team Members
- **Leonardo Céspedes Tenorio**
- **Kevin Chang Chang*

## Description
The project's objective is to apply cybersecurity knowledge to analyze, exploit, and document vulnerabilities in different scenarios, categorized into the following areas:
- **Pwn** (Binary exploitation)
- **Web** (Web application vulnerabilities)
- **Reverse** (Reverse engineering of executables)

Each challenge includes:
- A script with the solution (`.py` or `.sh` as appropriate)
- A `README.md` file documenting the procedure, tools used, exploited vulnerabilities (CWE), attack patterns (CAPEC), and the obtained flag.

## Challenges
| Challenge              | Category | Points |
|-----------------------|-----------|--------|
| You know 0xDiablos   | Pwn       | 20     |
| Neonify              | Web       | 20     |
| Jscalc               | Web       | 20     |
| Behind the Scenes    | Reverse   | 10     |
| Bypass               | Reverse   | 20     |
| Spooky License       | Reverse   | 20     |
| PDFy                 | Web       | 30     |
| Execute              | Pwn       | 20     |

## Repository Structure
```
📂 Project2-CTF
├── 📂 challenges
│   ├── 📂 You_know_0xDiablos
│   │   ├── exploit.py
│   │   ├── README.md
│   ├── 📂 Neonify
│   │   ├── exploit.py
│   │   ├── README.md
│   ├── 📂 Jscalc
│   │   ├── exploit.py
│   │   ├── README.md
│   ├── 📂 Behind_the_Scenes
│   │   ├── exploit.sh
│   │   ├── README.md
│   ├── 📂 Bypass
│   │   ├── exploit.sh
│   │   ├── README.md
│   ├── 📂 Spooky_License
│   │   ├── exploit.py
│   │   ├── README.md
│   ├── 📂 PDFy
│   │   ├── exploit.php
│   │   ├── README.md
│   ├── 📂 Execute
│   │   ├── exploit.py
│   │   ├── README.md
└── README.md (this file)
```

Each directory within `challenges/` contains the exploitation code and its respective documentation.

## Tools Used
- **GDB, PWNTools, Netcat** (Binary exploitation)
- **Burp Suite** (Web traffic analysis and manipulation)
- **Ghidra, Ltrace, Strings** (Reverse engineering)
- **PHP, SSH** (Web server and traffic redirection)

## How to Use the Exploits
Each `README.md` in the challenge directories contains detailed instructions on how to execute the exploit. Generally, execution follows this format:
```sh
python3 exploit.py
```
Or for Bash scripts:
```sh
./exploit.sh
```

For the PDFy challenge, a local PHP server is required:
```sh
php -S 127.0.0.1:3000
```
