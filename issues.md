# Lab 5: Static Code Analysis — Issue Log

## Project
Ticket Booking System

## Tools Used
- Pylint
- Bandit
- Flake8

## Issues Identified and Fixes

| Issue | Type | Line(s) in Original File | Description | Fix Approach |
|---|---|---:|---|---|
| Mutable default argument | Code quality / correctness | 15 | The default list could be shared between function calls. | Changed the default to None and initialized a new list inside the function. |
| Bare exception | Error handling | 23–27 | A bare except hides unexpected errors. | Checked whether the seat exists before attempting cancellation. |
| Unsafe eval() | Security | 40–43 | Evaluating a string can execute arbitrary Python expressions. | Replaced eval() with a validated numeric discount rate. |
| Weak MD5 hash | Security | 46–47 | MD5 is unsuitable for security-sensitive hashing. | Replaced MD5 with SHA-256. |
| Insecure random PIN | Security | 50–51 | The standard random generator is not intended for security-sensitive values. | Used secrets.randbelow() to generate a four-digit PIN. |
| Shell command execution | Security | 54–58 | os.system() invokes a shell unnecessarily and can introduce command-injection risk. | Removed shell execution and printed the confirmation directly. |
| Hardcoded secret printed | Security | 69–79 | A hardcoded box-office token was exposed in program output. | Removed the hardcoded token and its output. |
| Unused import | Code quality | 6 | The math import was not used. | Removed the unused import. |
| Unused variables | Code quality | 31, 41, 63 | Variables were assigned but not used meaningfully. | Removed unnecessary variables or used the base price in the discount calculation. |
| Naming and missing docstrings | Maintainability | 15, 23, 30, 40, 46, 50, 54, 61, 69 | Function names and documentation did not follow consistent conventions. | Applied snake_case naming and added docstrings. |
| File handling and encoding | Reliability | 54–58 | The file was manually closed and no encoding was specified. | Used a with statement and explicit UTF-8 encoding. |
| Formatting violations | Style | 19, 26, 82 | Long lines, a bare exception, and a missing final newline were reported. | Corrected line lengths, exception handling, and the final newline. |
| Seating summary readability | Maintainability | 61–66 | The sold-seat count used a manual loop. | Simplified the count using sum(). |

## Verification Results

| Tool | Before | After |
|---|---|---|
| Pylint | 5.37/10 | 10.00/10 |
| Bandit | 5 findings | 0 findings |
| Flake8 | 7 findings | 0 findings |

The original line numbers refer to the assigned source file before modifications. See the reports/ directory for the recorded before-and-after analysis outputs.
