# Python Sets 

## What is a Set?

A **set** in Python is a built-in data type used to store **multiple unique items** in a single variable.

```python
my_set = {1, 2, 3, 4}
print(my_set)
```

### Key Characteristics

* Unordered (no indexing)
* No duplicate values
* Mutable (you can add/remove items)
* Uses `{}` brackets

---

## Why Use Sets?

Sets are extremely useful when you want to:

### 1. Remove duplicates

```python
nums = [1, 2, 2, 3, 4, 4]
unique_nums = set(nums)
print(unique_nums)  # {1, 2, 3, 4}
```

### 2. Perform fast membership checks

```python
users = {"admin", "guest", "root"}

print("admin" in users)  # True
```

### 3. Perform mathematical operations (like union, intersection)

---

## How Sets Work Internally

Sets use a concept called **Hashing**.

* Each element is stored using a **hash value**
* This allows:

  * Fast lookup (`O(1)` average time)
  * No duplicates (same hash = same value)

Example:

```python
s = {1, 1, 2, 2}
print(s)  # {1, 2}
```

---

# Joining Sets (Set Operations)

## 1. Union (Combine All Elements)

The `union()` method returns a new set with all items from both sets.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}

result = set1.union(set2)
print(result)  # {1, 2, 3, 4, 5}
```

### Using Operator `|`

```python
result = set1 | set2
```

### Important Note

* `|` works **only with sets**
* `union()` works with other iterables too (like lists)

---

## 2. Update (Modify Original Set)

Adds elements of another set into the current set.

```python
set1 = {1, 2, 3}
set2 = {4, 5}

set1.update(set2)
print(set1)  # {1, 2, 3, 4, 5}
```

### Key Point

* Modifies original set
* Returns `None`

---

## 3. Intersection (Common Elements Only)

Returns elements present in **both sets**

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}

print(set1.intersection(set2))  # {2, 3}
```

### Using Operator `&`

```python
print(set1 & set2)
```

---

## 4. intersection_update()

Modifies original set and keeps only common elements

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}

set1.intersection_update(set2)
print(set1)  # {2, 3}
```

---

## 5. Difference (Unique to First Set)

Returns elements in first set but not in second

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}

print(set1.difference(set2))  # {1}
```

### Using Operator `-`

```python
print(set1 - set2)
```

### Note

* `-` works only with sets

---

## 6. difference_update()

Modifies original set

```python
set1 = {1, 2, 3}
set2 = {2, 3}

set1.difference_update(set2)
print(set1)  # {1}
```

---

## 7. Symmetric Difference (Exclude Common Elements)

Keeps elements that are **NOT common**

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}

print(set1.symmetric_difference(set2))  # {1, 4}
```

### Using Operator `^`

```python
print(set1 ^ set2)
```

---

## 8. symmetric_difference_update()

Modifies original set

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}

set1.symmetric_difference_update(set2)
print(set1)  # {1, 4}
```

---

# Important Notes

## 1. No Duplicates

```python
s = {1, 1, 2}
print(s)  # {1, 2}
```

## 2. True and 1 Are Same

```python
s = {True, 1}
print(s)  # {True}
```

Same applies for:

* `False == 0`

---

# FrozenSet (Immutable Set)

A **frozenset** is just like a set, but **immutable** (cannot be changed).

```python
fs = frozenset([1, 2, 3])
print(fs)
```

### Key Features

* Immutable (no add/remove)
* Can be used as dictionary keys
* Still supports set operations

---

## Example

```python
fs1 = frozenset([1, 2, 3])
fs2 = frozenset([3, 4, 5])

print(fs1.union(fs2))  # frozenset({1, 2, 3, 4, 5})
```

---

## When to Use frozenset?

* When data should not change
* When using sets as dictionary keys
* For security / consistency

---

# Quick Summary Table

| Operation                   | Method                          | Operator | Modifies Original |   |
| --------------------------- | ------------------------------- | -------- | ----------------- | - |
| Union                       | `union()`                       | `        | `                 | ❌ |
| Update                      | `update()`                      | ❌        | ✅                 |   |
| Intersection                | `intersection()`                | `&`      | ❌                 |   |
| Intersection Update         | `intersection_update()`         | ❌        | ✅                 |   |
| Difference                  | `difference()`                  | `-`      | ❌                 |   |
| Difference Update           | `difference_update()`           | ❌        | ✅                 |   |
| Symmetric Difference        | `symmetric_difference()`        | `^`      | ❌                 |   |
| Symmetric Difference Update | `symmetric_difference_update()` | ❌        | ✅                 |   |

---


