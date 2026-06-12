---

## What is `bool`?

`bool` (Boolean) is a data type that represents only two values:

```python
True
False
```

Used to make decisions in code.

---

## 1. Basic Usage

```python
is_admin = True

if is_admin:
    print("Access granted")
```

If condition is `True` → code runs
If `False` → skipped

---

## 2. Boolean from Comparisons

```python
print(10 == 9)   # False
print(5 > 3)     # True
print(7 != 7)    # False
```

### Operators

| Operator | Meaning   |
| -------- | --------- |
| `==`     | equal     |
| `!=`     | not equal |
| `>`      | greater   |
| `<`      | less      |

---

## 3. How Comparison Works Internally

```python
10 == 9
```

Internally:

```python
10.__eq__(9)
```

Calls special method `__eq__()` and returns `True` or `False`.

---

## 4. `bool()` Function

Converts any value into `True` or `False`:

```python
bool("hello")   # True
bool(15)        # True
bool("")        # False
bool(0)         # False
```

---

## 5. Truthy vs Falsy

### Falsy values:

```python
False
0
""
None
[]
{}
```

### Truthy values:

```python
"hello"
1
[1,2,3]
```

Rule:
If value exists → True
If empty or zero → False

---

## 6. Internal Logic of `bool()`

Python checks:

### For numbers:

```python
number != 0
```

### For strings/lists:

```python
len(value) > 0
```

Uses:

* `__bool__()`
* or `__len__()`

---

## 7. `__len__()` Connection

```python
text = "hello"

len(text)          # 5
bool(text)         # True
```

Internally:

```python
text.__len__() > 0
```

---

## 8. Logical Operators

```python
True and False   # False
True or False    # True
not True         # False
```

Example:

```python
is_logged_in = True
is_admin = False

if is_logged_in and is_admin:
    print("Admin access")
```

---

## 9. Boolean in Conditions

```python
x = 10

if x > 5:
    print("Big")
else:
    print("Small")
```

---

## 10. Custom Boolean Behavior

```python
class Hacker:
    def __len__(self):
        return 0

obj = Hacker()

print(bool(obj))   # False
```

---

## 11. `__bool__()` (Advanced)

```python
class Test:
    def __bool__(self):
        return True

obj = Test()
print(bool(obj))   # True
```

---

## 12. Priority Order

When calling `bool(obj)`:

1. `obj.__bool__()`
2. else → `obj.__len__()`
3. else → `True`

---

## 13. Hacker Mindset

Weak code:

```python
if user_input:
    allow_access()
```

Any non-empty input → True → bypass possible.

Dangerous logic:

```python
if is_admin == True:
```

---

## 14. Common Mistakes

Checking only existence:

```python
if password:
```

Better:

```python
if password == "secure123":
```

---

## 15. Practice Ideas

* Create a login system
* Try breaking it using:

  * empty input
  * random strings
  * wrong types

---

## Final Summary

* `bool` = True / False
* Used in conditions and decisions
* Based on comparison and truthy/falsy values
* Internally uses:

  * `__bool__()`
  * `__len__()`

---

## Pro Tip

Avoid:

```python
if input:
```

Always validate properly.
