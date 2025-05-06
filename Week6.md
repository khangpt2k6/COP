# 📌 Tóm tắt Python: Vòng lặp cơ bản, Vòng lặp lồng nhau, Vòng lặp với else, Hàm random, Hàm enumerate, Hàm trùng tên

## 🔁 Các vòng lặp cơ bản

### 1. Vòng lặp cơ bản (`for` / `while`)

- **Vòng lặp for:**
```python
for i in range(5):
    print(i)
# Kết quả: 0 1 2 3 4
```

- **Vòng lặp while:**
```python
i = 0
while i < 5:
    print(i)
    i += 1
# Kết quả: 0 1 2 3 4
```

### 2. Ý tưởng chung
- Lặp lại một khối lệnh nhiều lần.
- Dừng khi điều kiện sai (`while`) hoặc kết thúc dải số (`for`).

### 3. Vòng lặp lồng nhau
- Vòng lặp bên trong một vòng lặp khác:
```python
for i in range(3):
    for j in range(2):
        print(f"i={i}, j={j}")
```

### 4. Vòng lặp với `else`
- `else` chỉ chạy nếu vòng lặp hoàn tất mà không gặp `break`:

```python
for i in range(5):
    if i == 3:
        break
else:
    print("Vòng lặp đã hoàn thành")  # không in do gặp break
```

```python
for i in range(5):
    print(i)
else:
    print("Vòng lặp kết thúc bình thường")  # sẽ được in
```

## 🎲 Hàm random và phạm vi giá trị

```python
import random

random.randint(1, 5)     # Số nguyên từ 1 đến 5 (bao gồm 5)
random.randrange(1, 5)   # Số nguyên từ 1 đến 4
random.random()          # Số thực từ 0.0 đến 1.0
random.uniform(1, 5)     # Số thực từ 1 đến 5 (bao gồm cả 5)
```

| Hàm           | Kiểu dữ liệu | Phạm vi   | Ví dụ kết quả |
|---------------|--------------|-----------|---------------|
| randint(a, b) | int          | [a, b]    | 1, 2, 3, 4, 5 |
| randrange(a,b)| int          | [a, b)    | 1, 2, 3, 4    |
| random()      | float        | [0.0,1.0) | 0.2374        |
| uniform(a,b)  | float        | [a, b]    | 2.6345        |

## ⛔ `break` và `continue`

- **break:** Thoát khỏi vòng lặp ngay lập tức.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
# Kết quả: 0 1 2
```

- **continue:** Bỏ qua phần còn lại của vòng lặp, tiếp tục vòng mới.

```python
for i in range(5):
    if i == 3:
        continue
    print(i)
# Kết quả: 0 1 2 4
```

### Trong vòng lặp lồng nhau:

```python
for i in range(3):
    for j in range(3):
        if j == 1:
            break
        print(f"i={i}, j={j}")
# break chỉ thoát khỏi vòng trong (for j)
```

## 🧮 Hàm `enumerate()`

- Cho cả chỉ số và giá trị khi duyệt:

```python
fruits = ["apple", "banana", "cherry"]
for index, value in enumerate(fruits):
    print(index, value)
# Kết quả:
# 0 apple
# 1 banana
# 2 cherry
```

## 🎯 Hàm trùng tên

- Python **KHÔNG** hỗ trợ đa hình (overloading). Hàm khai báo sau sẽ ghi đè hàm trước.

```python
def greet():
    print("Hello")

def greet():
    print("Xin chào")

greet()
# Kết quả: Xin chào
```

- Thường dùng khi viết lại hàm để cải tiến. Chỉ hàm sau cùng có hiệu lực.
