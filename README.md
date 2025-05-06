# 📘 Python Programming - Week 3: Tổng Hợp Kiến Thức Chi Tiết

---

## ✅ 1. List Basics

### 🔹 Tạo list
```python
my_list = [10, 'abc']
empty_list = []
```

### 🔹 Truy cập và cập nhật phần tử
```python
my_list[0]       # truy cập phần tử đầu
my_list[1] = 99  # cập nhật phần tử tại index 1
```

### 🔹 Thêm và xoá phần tử
```python
my_list.append('xyz')     # thêm cuối
my_list.pop(1)            # xoá theo index
my_list.remove('xyz')     # xoá theo giá trị
```

### 🔹 Các hàm thường dùng
```python
len(my_list), sum([1,2,3]), my_list.index('abc'), my_list.count(10)
```

### 🔹 List comprehension
```python
squares = [x**2 for x in range(5)]
```

---

## ✅ 2. Tuple Basics

### 🔹 Tuple là immutable list
```python
t = (5, 10, 15)
print(t[1])    # 10
```

### 🔹 Named tuple
```python
from collections import namedtuple
Car = namedtuple('Car', ['make', 'model', 'year'])
my_car = Car('Toyota', 'Corolla', 2022)
print(my_car.model)
```

---

## ✅ 3. Set Basics

### 🔹 Tạo set
```python
s = {1, 2, 3}
s2 = set([1, 2, 2, 3])  # bỏ trùng
```

### 🔹 Thêm, xoá phần tử
```python
s.add(4)
s.remove(1)
s.pop()        # xoá phần tử ngẫu nhiên
s.clear()
```

### 🔹 Toán tử tập hợp
```python
a.union(b), a.intersection(b), a.difference(b), a.symmetric_difference(b)
```

---

## ✅ 4. Dictionary Basics

### 🔹 Tạo dict
```python
d = {'name': 'Khang', 'age': 18}
```

### 🔹 Truy cập, thêm, cập nhật
```python
d['age']        # 18
d['email'] = 'khang@gmail.com'
d['age'] = 19
```

### 🔹 Xoá phần tử
```python
del d['name']
```

### 🔹 Duyệt dict
```python
for k, v in d.items():
    print(k, v)
```

---

## ✅ 5. Membership vs Identity Operators

### 🔹 Membership
```python
5 in [1,2,5]             # True
'apple' not in fruits    # True
'abc' in '123abcd'       # True
```

### 🔹 Dictionary
```python
'key' in d     # kiểm tra key
```

### 🔹 Identity
```python
a = [1,2]
b = a
c = [1,2]
a is b     # True
a is c     # False
```

---

## ✅ 6. Type Conversion

### 🔹 Implicit
```python
5 + 2.0 = 7.0  # float
```

### 🔹 Explicit
```python
int('10')        # 10
float('3.14')    # 3.14
str(5)           # '5'
```

### 🔹 Lưu ý
- `int(4.9)` → 4 (bỏ phần thập phân)
- `int('abc')` → lỗi

---

## ✅ 7. Substrings (Chuỗi con)

### 🔹 Truy cập ký tự
```python
s = "Python"
s[0], s[-1]
```

### 🔹 Slicing
```python
s[1:4]       # 'yth'
s[:3], s[3:], s[::-1], s[::2]
```

### 🔹 Tách chuỗi:
```python
"abc@xyz.com".split('@')    # ['abc', 'xyz.com']
```

---

## ✅ 8. String Formatting (f-strings)

### 🔹 Cơ bản
```python
name = "Khang"
print(f"My name is {name}")
```

### 🔹 Biểu thức bên trong
```python
print(f"{2*3}")        # 6
print(f"{2*3=}")       # 2*3=6
```

### 🔹 Escape dấu {}
```python
print(f"{{Hello}}")    # {Hello}
```

### 🔹 Format nâng cao
```python
f"{4:.2f}"        # 4.00
f"{5:03d}"        # 005
f"{7600:,.2f}"    # 7,600.00
f"{31:b}"         # 11111
f"{31:x}"         # 1f
```

### 🔹 Căn lề
```python
f"{42:>5}"   # '   42'
f"{42:<5}"   # '42   '
f"{42:^5}"   # ' 42  '
```

---

## 📌 Tổng kết

| Chủ đề | Kỹ thuật chính |
|--------|----------------|
| List   | append(), pop(), comprehension |
| Tuple  | immutable, namedtuple |
| Set    | unique, union/intersection |
| Dict   | key-value, items(), del |
| Membership | in / not in |
| Identity   | is / is not |
| Conversion | int(), float(), str() |
| String     | slicing, split |
| Formatting | f-string, :,.2f, {:03d}, {:b} |

---
