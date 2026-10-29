# Lab 5: Static Code Analysis — Reflection

## 1. What is static code analysis?

Static code analysis examines source code without executing the program. It helps identify potential bugs, insecure coding patterns, maintainability problems, and style violations early in development.

## 2. What is the difference between Pylint, Bandit, and Flake8?

Pylint checks code quality, naming, documentation, unused variables, and other programming practices.

Bandit examines Python source code for common security weaknesses, such as unsafe expression evaluation, weak hashing, and risky shell execution.

Flake8 checks Python code for style violations, whitespace problems, line-length issues, and selected programming errors.

## 3. What issues were found in this program?

The original program had five Bandit findings, including high-severity findings involving weak MD5 hashing and shell command execution. It also used eval(), a bare exception, a mutable default argument, unused variables, and inconsistent formatting.

## 4. How were the issues fixed?

The discount calculation was changed to use a validated numeric discount rate. MD5 was replaced with SHA-256, the PIN generator was changed to use Python's secrets module, shell execution was removed, and the cancellation function was changed to handle missing seats explicitly. Naming, documentation, unused code, file handling, and formatting were also improved.

## 5. What were the final analysis results?

Pylint reported a score of 10.00/10. Bandit reported no issues, and Flake8 produced no violations.

## 6. What did you learn?

The lab demonstrated that a program can run successfully while still containing security and maintainability issues. Static analysis tools identify different classes of problems, so using multiple tools provides broader coverage. Re-running the tools after making changes helps verify that the reported issues have been addressed.

## 7. What are the limitations of static analysis?

Static analysis does not prove that a program is completely secure or functionally correct. It may miss runtime problems and application-specific weaknesses. Testing, code review, and appropriate security controls are still necessary.
