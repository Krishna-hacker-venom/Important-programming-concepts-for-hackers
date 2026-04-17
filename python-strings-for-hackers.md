## Python Strings

If you're trying to handle quotes inside strings in Python, there are multiple clean approaches depending on the situation.

---

### 1. Mixing Single and Double Quotes

Simplest and most readable approach:

```python
text = "He said, 'Hello there!'"
```

```python
text = 'She said, "Hi!"'
```

---

### 2. Escaping Quotes

Use backslash when using the same quote type:

```python
text = "He said, \"Hello there!\""
```

```python
text = 'It\'s a nice day'
```

---

### 3. Triple Quotes

Useful for multi-line strings or complex text:

```python
text = """He said, "It's a beautiful day!" and smiled."""
```

```python
text = '''She replied, "Yes, it's perfect!"'''
```

---

### 4. Raw Strings

Raw strings treat backslashes as literal characters:

```python
text = r"He said \"Hello\""
```

Use cases:

* File paths
* Regular expressions

Limitation:

```python
r"C:\path\"   # Error
```

---

### 5. repr() Function

Returns the exact internal representation of a string:

```python
text = "hello\nworld"
print(repr(text))
```

Difference:

* str() → human-readable
* repr() → debugging

---

### 6. Format Strings (f-strings)

Used to insert variables inside strings:

```python
name = "Alice"
text = f"Hello {name}"
```

Supports expressions:

```python
f"{2 + 3}"         # '5'
f"{name.upper()}"  # 'ALICE'
```

Formatting example:

```python
pi = 3.14159
f"{pi:.2f}"   # '3.14'
```

---

## String Operations (Important for Hackers)

---

### 7. Checking Strings (`in` / `not in`)

Used to check presence of substring:

```python
"admin" in "admin123"      # True
"root" not in "user123"    # True
```

Hacker use:

* Input validation bypass
* Keyword filtering checks

---

### 8. String Slicing

Used to extract parts of a string:

```python
text = "hacker"
text[0:4]   # 'hack'
text[::-1]  # reverse
```

Hacker use:

* Payload manipulation
* Extract sensitive parts

---

### 9. Placeholders and Modifiers

Older formatting methods:

```python
name = "Alice"
"Hello %s" % name
```

```python
"Hello {}".format(name)
```

Modern approach:

```python
f"Hello {name}"
```

---

### 10. Escape Characters

Used to represent special characters:

| Escape | Meaning      |
| ------ | ------------ |
| \n     | New line     |
| \t     | Tab          |
| \      | Backslash    |
| "      | Double quote |
| '      | Single quote |

Example:

```python
print("Hello\nWorld")
```

---

## Practical Hacker Insight

* Strings are the most common attack surface
* Most vulnerabilities (XSS, SQLi) come from improper string handling
* Always test how input is processed, escaped, and validated

---
