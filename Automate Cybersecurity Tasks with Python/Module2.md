# Course 7 - Module 2 Notes

## Index
- [Functions](#functions)
- [Parameters, Arguments & Return](#parameters-arguments--return)
- [Global vs Local Variables](#global-vs-local-variables)
- [Built-in Functions](#built-in-functions)
- [Modules & Libraries](#modules--libraries)
- [Comments, Indentation & PEP 8](#comments-indentation--pep-8)
- [Key Terms](#key-terms)

---

# Functions

## Function
- A reusable section of code.
- Helps automate repetitive tasks.
- Widely used in cybersecurity (e.g., processing multiple security logs).

---

## Defining a Function

Function syntax:

```python
def display_investigation_message():
    print("investigate activity")
```

Components:
- `def` keyword
- Function name
- Parentheses `()`
- Colon `:`
- Indented function body

Best practice:
- Give functions descriptive names.

---

## Calling a Function

```python
display_investigation_message()
```

Functions can be called multiple times.

Example:

```python
def display_investigation_message():
    print("investigate activity")

application_status = "potential concern"
email_status = "okay"

if application_status == "potential concern":
    print("application_log:")
    display_investigation_message()
```

---

## Infinite Recursion

Avoid calling a function inside itself unless there is a stopping condition.

Example:

```python
def func1():
    func1()
```

This creates an infinite loop (recursion).

---

# Parameters, Arguments & Return

## Parameters

- Variables defined in the function header.
- Used inside the function.

Example:

```python
def remaining_login_attempts(maximum_attempts, total_attempts):
    print(maximum_attempts - total_attempts)
```

Parameters:
- `maximum_attempts`
- `total_attempts`

---

## Arguments

- Values passed when calling a function.

Example:

```python
remaining_login_attempts(3, 2)
```

Arguments:
- `3`
- `2`

---

## Return Statement

Returns data from a function.

Example:

```python
def remaining_login_attempts(maximum_attempts, total_attempts):
    return maximum_attempts - total_attempts
```

Using returned value:

```python
remaining_attempts = remaining_login_attempts(3, 3)

if remaining_attempts <= 0:
    print("Your account is locked")
```

Notes:
- `return` is **not** a function.
- Code after `return` is not executed.

---

# Global vs Local Variables

## Global Variable

- Defined outside functions.
- Accessible throughout the program.

Example:

```python
device_id = "7ad2130bd"
```

---

## Local Variable

- Defined inside a function.
- Exists only while the function runs.

Example:

```python
def greet_employee(name):
    total_string = "Welcome " + name
    return total_string
```

Local variables:
- `name`
- `total_string`

---

## Using Global Variables

```python
username = "elarson"

def identify_user():
    print(username)

identify_user()
```

Functions can access global variables.

---

## Local Variable Overrides Global

```python
username = "elarson"

print("1:", username)

def greet():
    username = "bmoreno"
    print("2:", username)

greet()

print("3:", username)
```

Output:

```
1: elarson
2: bmoreno
3: elarson
```

Best practice:
- Avoid using the same name for global and local variables.

---

# Built-in Functions

## print()

Displays output.

Example:

```python
month = "September"

print("Investigate failed login attempts during", month)
```

---

## type()

Returns the data type.

Example:

```python
print(type("security"))
```

---

## Passing Functions into Functions

```python
print(type("This is a string"))
```

`type()` runs first and its result is passed to `print()`.

---

## max()

Returns the largest value.

Example:

```python
time_list = [12, 2, 32, 19, 57, 22, 14]

print(max(time_list))
```

---

## min()

Returns the smallest value.

Example:

```python
print(min(time_list))
```

---

## sorted()

Returns a sorted copy.

Example:

```python
time_list = [12, 2, 32, 19, 57, 22, 14]

print(sorted(time_list))
```

Original list remains unchanged:

```python
print(time_list)
```

Notes:
- Sorts in ascending order.
- Cannot sort mixed data types like:

```python
[1, 2, "hello"]
```

---

# Modules & Libraries

## Module

- A Python file containing functions, variables, classes, and executable code.

Examples:
- `re`
- `csv`
- `os`
- `glob`
- `time`
- `datetime`
- `statistics`

---

## Library

- A collection of modules.

---

## Python Standard Library

Modules included with Python.

---

## Import Entire Module

```python
import statistics
```

Using functions:

```python
statistics.mean(data)
statistics.median(data)
```

Example:

```python
import statistics

monthly_failed_attempts = [20,17,178,33,15,21,19,29,32,15,25,19]

print(statistics.mean(monthly_failed_attempts))
print(statistics.median(monthly_failed_attempts))
```

---

## Import Specific Functions

```python
from statistics import mean, median
```

Now call directly:

```python
mean(data)
median(data)
```

---

## External Libraries

Must be installed before importing.

Example:

```python
%pip install numpy
```

Import:

```python
import numpy
```

Examples mentioned:
- Beautiful Soup (`bs4`)
- NumPy (`numpy`)

---

# Comments, Indentation & PEP 8

## Comments

Explain code for readability.

---

### Single-line Comment

```python
# Print computer assets

for asset in computer_assets:
    print(asset)
```

---

### Multi-line Comment

Using multiple `#`:

```python
# remaining_login_attempts() takes two integers.
# Returns remaining login attempts.
```

Using docstrings:

```python
"""
remaining_login_attempts() takes two integers.

Returns remaining login attempts.
"""
```

---

## Indentation

- Uses spaces at the beginning of a line.
- PEP 8 recommends **4 spaces**.
- Required for:
  - Functions
  - Loops
  - Conditional statements

Example:

```python
count = 0
login_status = True

while login_status == True:
    print("Try again.")
    count += 1

    if count == 4:
        login_status = False
```

---

## Common Syntax Rules

### Strings

```python
username = "bmoreno"
```

---

### Numbers & Boolean

```python
login_attempts = 5
percentage_successful = 0.8
login_status = True
```

---

### Lists

```python
username_list = ["bmoreno", "tshah"]
```

---

### Colons

Required after:

- Function headers
- `if`
- `elif`
- `else`
- `for`
- `while`

Example:

```python
def remaining_login_attempts(maximum_attempts, total_attempts):
    return maximum_attempts - total_attempts
```

---

# Key Terms

| Term | Definition |
|------|------------|
| Argument | Data passed into a function when called |
| Built-in function | Function already available in Python |
| Comment | Note explaining code |
| Function | Reusable section of code |
| Global variable | Variable available throughout the program |
| Indentation | Spaces at the beginning of a line |
| Library | Collection of modules |
| Local variable | Variable defined inside a function |
| Module | Python file containing code |
| Parameter | Variable defined in a function header |
| PEP 8 | Python style guide |
| Python Standard Library | Collection of built-in Python modules |
| Return statement | Sends data back from a function |
| Style guide | Rules for writing readable code |
| User-defined function | Function created by the programmer |
