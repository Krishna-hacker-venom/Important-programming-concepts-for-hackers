## Python Operators 

---

### 1. Walrus Operator (`:=`)

The walrus operator allows you to assign a value to a variable inside an expression.

```python
if (n := len("hacker")) > 5:
    print(n)
```

Instead of:

```python
n = len("hacker")
if n > 5:
    print(n)
```

Hacker Insight:

* Useful in writing compact payloads
* Can hide logic inside conditions (harder to detect)

---

### 2. Chaining Comparison Operators

Python allows multiple comparisons in a single line:

```python
10 < x < 20
```

Equivalent to:

```python
10 < x and x < 20
```

Hacker Insight:

* Helps bypass poorly written validation logic
* Developers sometimes misunderstand how chaining works

---

### 3. Identity Operators

Used to compare memory location:

* `is`
* `is not`

```python
a = [1, 2]
b = a

a is b   # True
```

---

### 4. Difference Between `is` and `==`

| Operator | Meaning                  |
| -------- | ------------------------ |
| `==`     | Compares values          |
| `is`     | Compares memory location |

Example:

```python
a = [1, 2]
b = [1, 2]

a == b   # True
a is b   # False
```

Hacker Insight:

* Logic bugs occur when developers use `is` instead of `==`
* Can lead to authentication or validation bypass

---

### 5. Membership Operators

Used to check presence:

* `in`
* `not in`

```python
"admin" in "admin123"      # True
"user" not in "admin123"   # True
```

Hacker Insight:

* Weak filtering logic can be bypassed
* Example: checking only `"admin"` instead of exact match

---

### 6. Bitwise Operators

Operate at binary level:

| Operator | Meaning     |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

Example:

```python
5 & 3   # 1
5 | 3   # 7
```

Hacker Insight:

* Used in cryptography and encoding
* Important in exploit development and reverse engineering

---

### 7. Operator Precedence

Defines order of execution.

Example:

```python
result = 2 + 3 * 4   # 14
```

Multiplication runs before addition.

---

### Common Precedence Order (High → Low)

1. `()`
2. `**`
3. `* / // %`
4. `+ -`
5. Comparison (`<`, `>`, `==`)
6. `not`
7. `and`
8. `or`

---

Hacker Insight:

* Misunderstanding precedence can lead to logic flaws
* Example:

```python
if not user == "admin":
```

Can behave unexpectedly if misused

---

## Practical Insight

* Operators are heavily used in conditions and validations
* Most logic-based vulnerabilities come from incorrect operator usage
* Always test edge cases and operator behavior

---
