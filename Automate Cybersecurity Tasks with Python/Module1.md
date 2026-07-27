# Course 7 - Module 1 Notes

## Index
- [Programming & Python](#programming--python)
- [Python Data Types](#python-data-types)
- [Variables](#variables)
- [Conditional Statements](#conditional-statements)
- [Loops](#loops)
- [Key Terms](#key-terms)

---

# Programming & Python

## Programming
- Programming is the process of creating instructions for a computer to perform tasks.
- Programs are converted into **binary (0s and 1s)** that the CPU executes.
- Python simplifies programming by using human-readable syntax.

## Python
- General-purpose programming language.
- Used for:
  - Website development
  - Data analysis
  - Automation
- Python code is executed through an **interpreter**, which translates code line by line.

## Python Versions
- This course uses **Python 3**.
- Different Python versions have different syntax.

## Python in Cybersecurity
Python is commonly used for automation in:
- Log analysis
- Malware analysis
- Access control list (ACL) management
- Intrusion detection
- Compliance checks
- Network scanning

---

# Python Data Types

## String
- Ordered sequence of characters.
- Written inside quotes.
- Can contain letters, numbers, symbols, and spaces.
- Empty string: `""`

Example:
```python
print("updates needed")
```

---

## List
- Ordered collection of data.
- Uses square brackets `[]`.
- Can store multiple data types.
- Empty list: `[]`

Example:
```python
print([12, 36, 54])
```

---

## Integer
- Whole number without decimal.

Example:
```python
print(5)
print(5 + 2)
```

---

## Float
- Number containing a decimal.

Example:
```python
print(1.2 + 2.8)
```

Division:
```python
1 / 4      # 0.25
1 // 4     # 0
```

---

## Boolean
- Only two values:
  - `True`
  - `False`

Example:
```python
print(True)
print(9 > 10)
```

---

## Tuple
- Ordered collection that **cannot be changed**.
- Uses parentheses `()`.

Example:
```python
("user1", "user2")
```

---

## Dictionary
- Stores **key-value pairs**.
- Uses curly braces `{}`.

Example:
```python
{
    1: "East",
    2: "West"
}
```

---

## Set
- Unordered collection of **unique values**.
- Uses curly braces `{}`.

Example:
```python
{"user1", "user2"}
```

---

# Variables

## Variable
- Container used to store data.
- Can be reassigned.

Example:
```python
username = "nzhao"
username = "zhao2"
```

Assign one variable to another:

```python
username = "nzhao"
old_username = username
```

Example:

```python
username = "nzhao"
old_username = username
username = "zhao2"

print("Previous username:", old_username)
print("Current username:", username)
```

## Variable Naming Rules

Use:
- Letters
- Numbers
- Underscores

Python variable names are **case-sensitive**.

Avoid:
- Python keywords
- Built-in function names

Best practices:
- Use descriptive names.
- Separate words with underscores.
- Avoid long or confusing names.

Examples:
```python
login_attempts
device_id
invalid_usernames
```

---

# Conditional Statements

## Comparison Operators

| Operator | Meaning |
|----------|---------|
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `==` | Equal to |
| `!=` | Not equal to |

---

## if

```python
if status == 200:
    print("OK")
```

---

## else

```python
if status == 200:
    print("OK")
else:
    print("check other status")
```

---

## elif

```python
if status == 200:
    print("OK")
elif status == 400:
    print("Bad Request")
elif status == 500:
    print("Internal Server Error")
else:
    print("check other status")
```

---

## Logical Operators

### and

Both conditions must be True.

```python
if status >= 200 and status <= 226:
    print("successful response")
```

---

### or

At least one condition must be True.

```python
if status == 100 or status == 102:
    print("informational response")
```

---

### not

Reverses the result of a condition.

```python
if not(status >= 200 and status <= 226):
    print("check status")
```

---

# Loops

## for Loop

Used to iterate through a sequence.

Example:

```python
for i in ["elarson", "bmoreno", "tshah"]:
    print(i)
```

Loop through a list:

```python
computer_assets = ["laptop1", "desktop20", "smartphone03"]

for asset in computer_assets:
    print(asset)
```

Loop through a string:

```python
for character in "security":
    print(character)
```

---

## range()

Generates a sequence of numbers.

```python
range(start, stop, increment)
```

Example:

```python
for i in range(0, 5, 1):
    print(i)
```

Shortcut:

```python
for i in range(5):
    print(i)
```

---

## while Loop

Runs while a condition is True.

Example:

```python
i = 1

while i < 5:
    print(i)
    i = i + 1
```

Example using login attempts:

```python
login_attempts = 0

while login_attempts < 5:
    print(login_attempts)
    login_attempts += 1
```

Boolean example:

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

## break

Stops the loop completely.

```python
for asset in computer_assets:
    if asset == "desktop20":
        break
    print(asset)
```

---

## continue

Skips the current iteration.

```python
for asset in computer_assets:
    if asset == "desktop20":
        continue
    print(asset)
```

---

## Infinite Loop

A loop that never ends.

Stop it with:
- `Ctrl + C`
- `Ctrl + Z`

---

# Key Terms

| Term | Definition |
|------|------------|
| Automation | Use of technology to reduce repetitive manual work |
| Boolean | Data that is either `True` or `False` |
| Command-line interface | Text-based interface for interacting with a computer |
| Comment | Notes added by programmers to explain code |
| Conditional statement | Executes code based on conditions |
| Data type | Category of data |
| Dictionary | Collection of key-value pairs |
| Float | Number with decimal |
| Integer | Whole number |
| IDE | Software used to write and debug code |
| Interpreter | Converts Python code into executable instructions |
| Iterative statement | Loop that repeats instructions |
| List | Ordered collection of data |
| Loop variable | Variable controlling loop iterations |
| Notebook | Interface for writing and running code |
| Programming | Process of creating instructions for computers |
| Set | Collection of unique unordered values |
| String | Ordered sequence of characters |
| Syntax | Rules for writing valid code |
| Tuple | Ordered immutable collection |
| Type error | Error caused by using the wrong data type |
| Variable | Container that stores data |
