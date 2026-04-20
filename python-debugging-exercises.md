# Python Debugging and Output Prediction Practice

## Student Progress Report

---

## Q1

```python
x = 5
y = x
x = 10
print(y)
```

**Your Answer:** 5
**Correct Answer:** 5

### Concept

Assignment copies value for immutable types.

---

## Q2

```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)
```

**Your Answer:** [1, 2, 3]
**Correct Answer:** [1, 2, 3, 4]

### Mistake

You assumed `b` is a copy.

### Concept

* `b = a` → both refer to the same list (reference)
* Lists are mutable → changes reflect in both

---

## Q3

```python
a = [1, 2, 3]
b = a.copy()
b.append(4)
print(a)
```

**Your Answer:** [1, 2, 3, 4]
**Correct Answer:** [1, 2, 3]

### Mistake

Confused `.copy()` with reference.

### Concept

`.copy()` creates a new list (separate memory)

---

## Q4

```python
x = "hello"
y = x.upper()
print(x, y)
```

**Your Answer:** HELLO HELLO
**Correct Answer:** hello HELLO

### Mistake

Thought string changes in-place.

### Concept

Strings are immutable → new object is created

---

## Q5

```python
x = [1, 2, 3]
print(x * 2)
```

**Your Answer:** [1, 2, 3] [1, 2, 3]
**Correct Answer:** [1, 2, 3, 1, 2, 3]

### Mistake

Thought it creates separate lists.

### Concept

`*` repeats elements into a single list

---

## Q6

```python
for i in range(3):
    i = i + 1
    print(i)
```

**Your Answer:** 1, 2, 3
**Correct Answer:**

```
1
2
3
```

### Concept

Loop variable resets on each iteration

---

## Q7

```python
x = 10

def change():
    x = 5
    print(x)

change()
print(x)
```

**Your Answer:**

```
5
10
```

**Correct Answer:** Same as above

### Concept

Local vs global variables (scope)

---

## Q8

```python
lst = [1, 2, 3]

for i in lst:
    lst.append(i)

print(lst)
```

**Your Answer:** [1, 2, 3, 1, 2, 3]
**Correct Answer:** Infinite loop

### Mistake

Assumed loop runs fixed times.

### Concept

Loop iterates over a dynamically growing list → causes infinite loop

---

## Q9

```python
def add_item(item, lst=[]):
    lst.append(item)
    return lst

print(add_item(1))
print(add_item(2))
```

**Your Answer:**

```
[1]
[1, 2]
```

**Correct Answer:** Same as above

### Concept

Default mutable arguments persist across function calls

---

## Q10

```python
a = [1, 2, 3, 4]
b = a[1:3]
b[0] = 100

print(a)
print(b)
```

**Your Answer:**

```
[100, 1, 2, 3, 4]
[100, 2, 3]
```

**Correct Answer:**

```
[1, 2, 3, 4]
[100, 3]
```

### Mistake

* Thought slicing affects original list
* Index confusion

### Concept

Slicing creates a new list (copy)

---

## Overall Analysis

### Strengths

* Basic syntax understanding is good
* Loop basics are clear
* Scope concept understood

### Weak Areas

1. Reference vs Copy
2. Mutable vs Immutable
3. Hidden Python edge cases
4. Execution tracing accuracy

---

## Key Concepts to Master

### 1. Memory Behavior

* `=` → reference
* `.copy()` → new object
* slicing → new object

### 2. Mutability

* Mutable → list, dict
* Immutable → int, string, tuple

### 3. Loop Behavior

* Loops don’t use fixed snapshots
* They operate on the actual object

### 4. Function Defaults

* Evaluated once
* Reused across calls

---

## Suggestions

### Practice Method

* Dry run code line-by-line
* Track memory mentally
* Ask: "Is this a new object or the same object?"

