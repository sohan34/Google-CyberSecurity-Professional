# Module 4 Notes – Automating Tasks, Files, Parsing & Debugging in Python

# 📘 Module 4 Index

- [1. Automating Security in CI/CD with Python (DevSecOps)](#1-automating-security-in-cicd-with-python-devsecops)
  - [What is DevSecOps?](#what-is-devsecops)
  - [Why Automate Security?](#why-automate-security)
  - [Security Tasks Python Can Automate](#security-tasks-python-can-automate)
    - [Security Testing (SAST, DAST, SCA)](#security-testing)
    - [Vulnerability Scanning](#vulnerability-scanning)
    - [Compliance Checks](#compliance-checks)
    - [Secrets Management](#secrets-management)
    - [Policy Enforcement](#policy-enforcement)
  - [Python Integration with CI/CD Tools](#python-integration-with-cicd-tools)
  - [Other CI/CD Tasks](#other-cicd-tasks)
  - [Key Takeaway](#key-takeaway)

- [2. Python Automation Basics](#2-python-automation-basics)
  - [Variables](#variables)
  - [Conditional Statements](#conditional-statements)
  - [Iterative Statements (Loops)](#iterative-statements-loops)
    - [for Loop](#for-loop)
    - [while Loop](#while-loop)
  - [Functions](#functions)
  - [Working with Strings](#working-with-strings)
  - [Working with Lists](#working-with-lists)
  - [Example Automation](#example-automation)

- [3. Working with Files](#3-working-with-files)
  - [Opening Files](#opening-files)
    - [with](#with)
    - [open()](#open)
    - [as](#as)
  - [Reading Files](#reading-files)
  - [Writing Files](#writing-files)
  - [File Paths](#file-paths)

- [4. Parsing Data](#4-parsing-data)
  - [.split()](#split)
  - [Applying .split() to Files](#applying-split-to-files)
  - [.join()](#join)
  - [Writing Parsed Data Back](#writing-parsed-data-back)

- [5. Debugging Python](#5-debugging-python)
  - [Syntax Errors](#syntax-errors)
  - [IndentationError](#indentationerror)
  - [Logic Errors](#logic-errors)
  - [Exceptions](#exceptions)
    - [NameError](#nameerror)
    - [IndexError](#indexerror)
    - [TypeError](#typeerror)
    - [FileNotFoundError](#filenotfounderror)

- [6. Debugging Strategies](#6-debugging-strategies)
  - [Read Error Messages](#read-error-messages)
  - [Use a Debugger](#use-a-debugger)
  - [Gemini Code Assist](#gemini-code-assist)
  - [Print Statements](#print-statements)

- [Important File Functions](#important-file-functions)
- [Important File Modes](#important-file-modes)
- [Important Automation Components](#important-automation-components)
- [Important Terms](#important-terms)
- [Quick Revision](#quick-revision)

## 1. Automating Security in CI/CD with Python (DevSecOps)

### What is DevSecOps?
DevSecOps = **Development + Security + Operations**

Security is integrated into every stage of the CI/CD pipeline instead of being added at the end.

Python is commonly used to automate these security tasks.

### Why automate security?

- Faster software releases
- Finds vulnerabilities early
- Consistent security checks
- Reduces manual work
- Supports DevSecOps culture

### Security tasks Python can automate

#### Security Testing

**SAST (Static Application Security Testing)**
- Scans source code before build
- Finds security weaknesses
- Can automatically fail builds

**DAST (Dynamic Application Security Testing)**
- Tests running applications
- Performs automated security testing
- Reports vulnerabilities

**SCA (Software Composition Analysis)**
- Scans third-party dependencies
- Detects vulnerable libraries
- Reports dependency risks

---

#### Vulnerability Scanning

Python can automate scans for:

- Container images
- Infrastructure
- CI/CD pipelines

It can:
- Schedule scans
- Collect reports
- Send alerts

---

#### Compliance Checks

Python scripts can verify:

- Secure coding standards
- Infrastructure policies
- Security guidelines

They can also generate compliance reports.

---

#### Secrets Management

Python helps:

- Detect hardcoded passwords
- Prevent API keys in source code
- Retrieve secrets from tools like HashiCorp Vault

---

#### Policy Enforcement

Python supports **Policy as Code**.

It can:

- Check security policies
- Verify pipeline rules
- Block releases when policies fail

---

### Python integration with CI/CD tools

Python works well with:

- Jenkins
- GitLab CI
- CircleCI

Python can:

- Run scripts
- Call APIs
- Start scans
- Fetch reports
- Control build pipelines

---

### Other CI/CD tasks Python automates

- Environment setup
- Secure staging environments
- Code quality checks (Linters)
- Secure software deployment
- Secure production releases

---

## Key Takeaway

Python automates security throughout CI/CD pipelines, making software releases faster, safer, and more reliable.

---

# 2. Python Automation Basics

Automation = Using technology to reduce repetitive manual work.

Security analysts commonly automate:

- Login investigations
- User management
- Device updates
- Log analysis

---

## Variables

A variable stores data.

Example

```python
username = "elarson"
```

Benefits

- Reuse data
- Avoid rewriting values

---

## Conditional Statements

Execute code only if a condition is true.

Example

```python
if login_attempts > 5:
    print("Account locked")
```

Benefits

- Decision making
- Reduces manual checking

---

## Iterative Statements (Loops)

Repeat actions automatically.

### for loop

Repeats over a sequence.

```python
for user in users:
    print(user)
```

---

### while loop

Repeats while a condition is true.

```python
while attempts < 5:
    attempts += 1
```

---

## Functions

Reusable blocks of code.

```python
def greet():
    print("Hello")
```

Benefits

- Reusable
- Cleaner programs
- Less duplicated code

---

## Working with Strings

Useful techniques:

- Bracket notation
- str()
- len()
- .index()

---

## Working with Lists

Useful methods:

- .append()
- .insert()
- .remove()
- .index()

---

## Example Automation

Count how many times a flagged user logged in.

Needed:

- Variable (counter)
- for loop
- if statement
- Function (optional)

---

# 3. Working with Files

Security analysts frequently work with log files.

Common formats:

- .txt
- .csv

Logs contain records of system events.

---

## Opening Files

Syntax

```python
with open("update_log.txt", "r") as file:
```

---

### with

Automatically closes files.

Preferred over manually opening files.

---

### open()

Opens a file.

Parameters

```python
open(filename, mode)
```

Modes

| Mode | Meaning |
|------|---------|
| "r" | Read |
| "w" | Write (overwrite/create) |
| "a" | Append |

---

### as

Assigns the opened file to a variable.

```python
with open("file.txt","r") as file:
```

---

## Reading Files

```python
with open("update_log.txt","r") as file:
    updates = file.read()

print(updates)
```

`.read()` converts the file into a string.

Once stored in a string, you can use:

- len()
- .index()
- slicing
- loops

---

## Writing Files

Overwrite a file

```python
with open("update_log.txt","w") as file:
    file.write("Updated")
```

---

Append to a file

```python
with open("update_log.txt","a") as file:
    file.write("New line")
```

`.write()` only writes strings.

---

## File Paths

A file path is the location of a file.

### Same directory

```python
open("update_log.txt")
```

### Different directory

```python
open("/home/analyst/logs/access_log.txt")
```

---

# 4. Parsing Data

Parsing = Converting data into a more readable or usable format.

Two important methods:

- .split()
- .join()

---

## .split()

Converts a string into a list.

Syntax

```python
string.split(separator)
```

Example

```python
users = "alice,bob,charlie"
users = users.split(",")
```

Output

```python
['alice', 'bob', 'charlie']
```

---

### Default split

```python
text.split()
```

Splits using whitespace.

---

### Applying .split() to Files

```python
with open("update_log.txt","r") as file:
    updates = file.read()

updates = updates.split()
```

Useful because lists are easier to iterate through.

---

## .join()

Converts a list into a string.

Syntax

```python
separator.join(list)
```

Example

```python
users = ["alice","bob","charlie"]

result = ",".join(users)
```

Output

```python
alice,bob,charlie
```

---

### Newline Join

```python
"\n".join(users)
```

Places each element on a new line.

---

### Writing Parsed Data Back

```python
updates = " ".join(updates)

with open("update_log.txt","w") as file:
    file.write(updates)
```

---

# 5. Debugging Python

Debugging = Finding and fixing errors.

Three main error types:

1. Syntax Errors
2. Logic Errors
3. Exceptions

---

## Syntax Errors

Invalid Python syntax.

Examples

- Missing quotes
- Missing colon
- Missing brackets

Example

```python
message = "Hello
```

Produces

```
SyntaxError
```

---

### IndentationError

A subtype of SyntaxError caused by incorrect indentation.

---

## Logic Errors

Program runs but produces incorrect results.

Example

```python
if attempts >= 5:
    print("User has NOT reached maximum")
```

Output is incorrect because the condition is wrong.

Logic errors do not produce error messages.

---

## Exceptions

Program is syntactically correct but cannot execute.

---

### NameError

Variable not defined.

```python
print(total)
```

if `total` does not exist.

---

### IndexError

Invalid index.

```python
users[5]
```

when list has only 3 elements.

---

### TypeError

Wrong data types.

```python
"10" + 5
```

---

### FileNotFoundError

Trying to open a file that doesn't exist.

```python
open("missing.txt")
```

---

# 6. Debugging Strategies

## Read Error Messages

Python reports:

- Line number
- Error type
- Description

Always fix the first reported error first.

---

## Use a Debugger

A debugger helps:

- Locate errors
- Inspect variables
- Use breakpoints
- Execute code step-by-step

Popular IDEs

- Visual Studio Code
- PyCharm
- JetBrains IDEs

---

## Gemini Code Assist

AI coding assistant integrated into IDEs.

Can:

- Explain code
- Suggest fixes
- Detect errors
- Generate code

Always verify AI-generated code before using it.

---

## Print Statements

Useful for finding logic errors.

Example

```python
print("Reached loop")
print(variable)
```

Temporary print statements help identify where incorrect behavior occurs.

---

# Important File Functions

```python
open()

read()

write()

split()

join()

len()

index()
```

---

# Important File Modes

| Mode | Purpose |
|------|---------|
| "r" | Read |
| "w" | Write (overwrite/create) |
| "a" | Append |

---

# Important Automation Components

- Variables
- Conditional statements
- for loops
- while loops
- Functions
- Strings
- Lists
- Files

---

# Important Terms

**Automation** – Using technology to reduce repetitive manual work.

**Variable** – Stores data.

**Conditional Statement** – Executes code based on conditions.

**Iterative Statement** – Repeats instructions.

**Function** – Reusable block of code.

**Log** – Record of system events.

**File Path** – Location of a file.

**Parsing** – Converting data into a readable format.

**Debugger** – Tool that helps locate program errors.

**Syntax Error** – Invalid Python syntax.

**Logic Error** – Program runs but gives incorrect output.

**Exception** – Runtime error in syntactically correct code.

**IDE (Integrated Development Environment)** – Software used for writing and debugging code.

---

# Quick Revision

### CI/CD Security
- DevSecOps
- SAST
- DAST
- SCA
- Vulnerability scanning
- Compliance
- Secrets management
- Policy enforcement

### Automation
- Variables
- if
- for
- while
- Functions

### Files
- open()
- read()
- write()
- with
- file paths

### Parsing
- split() → String → List
- join() → List → String

### Errors
- Syntax Error
- Logic Error
- Exception

### Debugging
- Read error messages
- Debugger
- Breakpoints
- Print statements
- Gemini Code Assist
