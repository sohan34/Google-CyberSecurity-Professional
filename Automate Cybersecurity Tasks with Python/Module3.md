# Course 7 - Module 3 Notes

## Index
- [Strings](#strings)
- [Lists](#lists)
- [Regular Expressions (Regex)](#regular-expressions-regex)
- [Key Terms](#key-terms)

---

# Strings

## String Data
- Ordered sequence of characters.
- Common cybersecurity uses:
  - IP addresses
  - Usernames
  - URLs
  - Employee IDs

---

## Indices

- Every character has an index.
- Starts at **0**.
- Negative indices count from the end.

Example:

| Character | h | 3 | 2 | r | b | 1 | 7 |
|-----------|---|---|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| Negative | -7 | -6 | -5 | -4 | -3 | -2 | -1 |

---

## Bracket Notation

Access a character:

```python
device_id = "h32rb17"

print(device_id[0])
```

Output:

```
h
```

---

## String Slicing

Extract part of a string.

```python
print("h32rb17"[0:3])
```

Output:

```
h32
```

Notes:
- Start index is included.
- End index is excluded.

---

## str()

Converts data into a string.

Example:

```python
string_id = str(19329302)
```

---

## len()

Returns the length of a string.

Example:

```python
device_id_length = len("h32rb17")

if device_id_length == 7:
    print("The device ID has 7 characters.")
```

---

## .upper()

Returns an uppercase copy.

```python
print("Information Technology".upper())
```

Output:

```
INFORMATION TECHNOLOGY
```

---

## .lower()

Returns a lowercase copy.

```python
print("Information Technology".lower())
```

Output:

```
information technology
```

---

## .index()

Returns the index of the **first occurrence**.

Example:

```python
print("h32rb17".index("r"))
```

Output:

```
3
```

If the value is not found:

```python
print("h32rb17".index("a"))
```

Returns an error.

Only the first occurrence is returned.

```python
print("r45rt46".index("r"))
```

Output:

```
0
```

---

## Finding Substrings

`.index()` also finds substrings.

```python
tshah_index = "tsnow, tshah, bmoreno - updated".index("tshah")

print(tshah_index)
```

Output:

```
7
```

Be careful:

Searching for `"ts"` returns `0` because `"ts"` first appears in `"tsnow"`.

---

# Lists

## List Data

- Ordered collection of elements.
- Can store multiple data types.

Cybersecurity uses:
- Usernames
- IP addresses
- URLs
- Device IDs

---

## List Indices

Example:

```python
username_list = [
    "elarson",
    "fgarcia",
    "tshah",
    "sgilmore"
]
```

| Element | Index |
|---------|------:|
| elarson | 0 |
| fgarcia | 1 |
| tshah | 2 |
| sgilmore | 3 |

---

## Access Elements

```python
print(username_list[2])
```

Output:

```
tshah
```

---

## List Slicing

```python
print(username_list[0:2])
```

Output:

```python
["elarson", "fgarcia"]
```

Produces a **sublist**.

---

## Changing List Elements

Lists are mutable.

```python
username_list = [
    "elarson",
    "fgarcia",
    "tshah",
    "sgilmore"
]

username_list[1] = "bmoreno"
```

---

## .insert()

Adds an element at a specific index.

```python
username_list.insert(2, "wjaffrey")
```

---

## .remove()

Removes the first occurrence.

```python
username_list.remove("elarson")
```

Only removes the first matching element.

---

## .append()

Adds an element to the end.

```python
username_list.append("btang")
```

Often used with loops.

Example:

```python
numbers_list = []

for i in range(10):
    numbers_list.append(i)
```

---

## List .index()

Returns the index of the first matching element.

```python
username_index = username_list.index("tshah")

print(username_index)
```

Output:

```
2
```

Only the first occurrence is returned.

---

# Regular Expressions (Regex)

## Regular Expression

- A sequence of characters that forms a pattern.
- Used to search strings.

Import:

```python
import re
```

---

## re.findall()

Returns a list of all matches.

Syntax:

```python
re.findall(pattern, string)
```

Example:

```python
import re

re.findall("ts", "tsnow, tshah, bmoreno")
```

Output:

```python
['ts', 'ts']
```

---

## Character Symbols

| Symbol | Meaning |
|---------|---------|
| `\w` | Alphanumeric character or `_` |
| `\d` | Digit (0–9) |
| `\s` | Whitespace |
| `.` | Any character except newline |
| `\.` | Literal period (`.`) |

Examples:

```python
re.findall("\w", "h32rb17")
```

```python
re.findall("\d", "h32rb17")
```

---

## Quantifiers

| Symbol | Meaning |
|---------|---------|
| `+` | One or more occurrences |
| `*` | Zero or more occurrences |
| `{n}` | Exactly n occurrences |
| `{m,n}` | Between m and n occurrences |

---

### +

```python
re.findall("\d+", "h32rb17")
```

Output:

```python
['32', '17']
```

---

### *

```python
re.findall("\d*", "h32rb17")
```

Matches zero or more digits, producing empty strings where no digits exist.

---

### {n}

Exactly n occurrences.

```python
re.findall("\d{2}", "h32rb17 k825t0m c2994eh")
```

---

### {m,n}

Range of occurrences.

```python
re.findall("\d{1,3}", "h32rb17 k825t0m c2994eh")
```

Matches:
- 1 digit
- 2 digits
- 3 digits

---

## Building Regex Patterns

Example log:

```python
employee_logins_string = "1001 bmoreno: 12 Marketing 1002 tshah: 7 Human Resources 1003 sgilmore: 5 Finance"
```

Pattern:

```python
pattern = "\w+:\s\d+"
```

Search:

```python
import re

print(re.findall(pattern, employee_logins_string))
```

Pattern breakdown:

| Pattern | Meaning |
|---------|---------|
| `\w+` | Username |
| `:` | Colon |
| `\s` | Space |
| `\d+` | One or more digits |

---

# Key Terms

| Term | Definition |
|------|------------|
| Algorithm | A set of rules that solve a problem |
| Bracket notation | Indices placed inside square brackets |
| Debugging | Identifying and fixing errors in code |
| Immutable | Object that cannot be changed after creation |
| Index | Position of an element in a sequence |
| List concatenation | Combining two lists into one |
| List data | Ordered collection of elements |
| Method | Function belonging to a specific data type |
| Regular expression (Regex) | Sequence of characters forming a search pattern |
| String concatenation | Joining two strings together |
| String data | Ordered sequence of characters |
| Substring | Continuous sequence of characters within a string |
