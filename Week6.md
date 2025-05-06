# 📌 Summary Python: General Loop, Nested Loop, Loop with else, Random Functions, Enumerate, Same Name Functions

## 🔁 General Loops

### 1. Basic loops (`for` / `while`)

- **for loop:**
```python
for i in range(5):
    print(i)
# Output: 0 1 2 3 4
```

- **while loop:**
```python
i = 0
while i < 5:
    print(i)
    i += 1
# Output: 0 1 2 3 4
```

### 2. General loop idea
- Repeat a block of code multiple times.
- Stops when condition fails (`while`) or range ends (`for`).

### 3. Nested loop
- Loop inside another loop:
```python
for i in range(3):
    for j in range(2):
        print(f"i={i}, j={j}")
```

### 4. Loop with `else`
- `else` executes ONLY if the loop completes without a `break`:

```python
for i in range(5):
    if i == 3:
        break
else:
    print("Finished loop")  # won't print due to break
```

```python
for i in range(5):
    print(i)
else:
    print("Loop finished without break")  # will print
```

## 🎲 Random Functions and Their Ranges

```python
import random

random.randint(1, 5)     # Integer from 1 to 5 inclusive
random.randrange(1, 5)   # Integer from 1 to 4
random.random()          # Float from 0.0 to 1.0
random.uniform(1, 5)     # Float from 1 to 5 inclusive
```

| Function       | Data Type | Range    | Example     |
|----------------|-----------|----------|-------------|
| randint(a, b)  | int       | [a, b]   | 1, 2, 3, 4, 5 |
| randrange(a, b)| int       | [a, b)   | 1, 2, 3, 4   |
| random()       | float     | [0.0, 1.0)| 0.2374      |
| uniform(a, b)  | float     | [a, b]   | 2.6345       |

## ⛔ `break` vs `continue`

- **break:** Exit current loop immediately.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
# Output: 0 1 2
```

- **continue:** Skip remaining code and continue next iteration.

```python
for i in range(5):
    if i == 3:
        continue
    print(i)
# Output: 0 1 2 4
```

### In Nested Loops:

```python
for i in range(3):
    for j in range(3):
        if j == 1:
            break
        print(f"i={i}, j={j}")
# break exits only inner loop
```

## 🧮 `enumerate()`

- Provides both index and value:

```python
fruits = ["apple", "banana", "cherry"]
for index, value in enumerate(fruits):
    print(index, value)
# Output:
# 0 apple
# 1 banana
# 2 cherry
```

## 🎯 Multiple Functions with Same Name

- Python does **NOT** support function overloading. New definitions overwrite previous ones.

```python
def greet():
    print("Hello")

def greet():
    print("Xin chào")

greet()
# Output: Xin chào
```

- Used for rewriting/improving functions. Only one definition is active at a time.
