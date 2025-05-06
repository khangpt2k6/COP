**COP2510 - Week 6 Python Summary: Loops, Random, Control Statements, Enumerate, Function Overwrite**

---

### I. General & Basic Loops

#### 1. `for` Loop:

* Syntax:

  ```python
  for variable in iterable:
      # code block
  ```
* Example:

  ```python
  for i in range(5):
      print(i)  # Output: 0 1 2 3 4
  ```

#### 2. `while` Loop:

* Syntax:

  ```python
  while condition:
      # code block
  ```
* Example:

  ```python
  i = 0
  while i < 5:
      print(i)
      i += 1
  ```

### II. Nested Loops

#### - Loops inside another loop:

```python
for i in range(2):
    for j in range(3):
        print(f"i={i}, j={j}")
```

---

### III. Loop with `else`

* The `else` clause runs **only if the loop doesn't encounter a `break`**.

Example 1 (without `break`):

```python
for i in range(3):
    print(i)
else:
    print("Loop finished")  # This will run
```

Example 2 (with `break`):

```python
for i in range(5):
    if i == 3:
        break
else:
    print("Loop finished")  # This will NOT run
```

---

### IV. Random Function Ranges (via `random` module)

```python
import random

random.randint(a, b)    # Returns integer in [a, b]
random.randrange(a, b)  # Returns integer in [a, b)
random.random()         # Returns float in [0.0, 1.0)
random.uniform(a, b)    # Returns float in [a, b]
```

| Function          | Output Type | Range       | Includes End? |
| ----------------- | ----------- | ----------- | ------------- |
| `randint(1, 5)`   | int         | 1 to 5      | Yes           |
| `randrange(1, 5)` | int         | 1 to 4      | No            |
| `random()`        | float       | 0.0 to <1.0 | No            |
| `uniform(1, 5)`   | float       | 1.0 to 5.0  | Yes           |

---

### V. `break` and `continue` Statements

#### `break`:

* Immediately exits the loop (inner-most loop if nested).

#### `continue`:

* Skips the remaining code in the current iteration.

Example:

```python
for i in range(5):
    if i == 2:
        continue  # Skips printing 2
    if i == 4:
        break     # Exits before printing 4
    print(i)      # Output: 0, 1, 3
```

---

### VI. Using `enumerate()`

* Returns index and value when looping through an iterable.

```python
fruits = ['apple', 'banana', 'cherry']
for index, fruit in enumerate(fruits):
    print(index, fruit)
# Output:
# 0 apple
# 1 banana
# 2 cherry
```

---

### VII. Function Overwriting

* Defining multiple functions with the same name in a scope means the **latest one overwrites the previous ones**.

```python
def greet():
    print("Hello")

def greet():
    print("Xin chao")

greet()  # Output: Xin chao
```

* Python does NOT support traditional function overloading like Java/C++.

---

### VIII. Common Quiz Concepts

* `loop + else` only executes when **no break** occurs.
* `break` exits the loop entirely.
* `continue` skips only one iteration.
* `enumerate()` helps track indexes.
* `random` functions differ in range inclusivity.
* Last function with a duplicate name overwrites the previous.

---

**Practice Suggestion:**
Try writing loops with both `break` and `else`, test each `random` function, and play with overwriting function definitions.
