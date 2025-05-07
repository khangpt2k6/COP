
# 📌 Tổng hợp kiến thức Python tuần 8

---

## 🚩 1. Arbitrary Arguments (`*args`)

Dùng để truyền số lượng đối số không xác định.

**Ví dụ:**
```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3))
print(sum_all(5, 10))
```

---

## 🚩 2. Arbitrary Keyword Arguments (`**kwargs`)

Dùng để truyền số lượng đối số keyword không xác định.

**Ví dụ:**
```python
def print_user(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_user(name="Khang", age=18, country="Vietnam")
```

---

## 🚩 3. Lambda Functions

Hàm ẩn danh, viết gọn trên một dòng.

**Cú pháp:**
```python
lambda arguments: expression
```

**Ví dụ cơ bản:**
```python
square = lambda x: x**2
print(square(5))
```

**Ví dụ nâng cao (dùng với sorted):**
```python
points = [(1, 2), (15, 1), (5, -1)]
sorted_points = sorted(points, key=lambda x: x[1])
print(sorted_points)
```

---

## 🚩 4. Hàm Đệ Quy (Recursive Functions)

Hàm gọi lại chính nó, cần điều kiện dừng (base case).

**Ví dụ: Giai thừa**
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)

print(factorial(5))
```

**Phân tích đệ quy:**
- Luôn phải có base case (trường hợp dừng).
- Kiểm tra độ phức tạp về stack memory.

---

## 🚩 5. List Comprehension

Tạo list ngắn gọn, hiệu quả.

**Ví dụ cơ bản:**
```python
squares = [x**2 for x in range(10)]
print(squares)
```

**Ví dụ nâng cao (với điều kiện):**
```python
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares)
```

**Tương đương với vòng lặp:**
```python
squares = []
for x in range(10):
    if x % 2 == 0:
        squares.append(x**2)
print(squares)
```

---

## 🚩 6. Type Hinting (Annotation)

Ghi chú rõ kiểu dữ liệu, giúp code rõ ràng và dễ bảo trì.

**Ví dụ cơ bản:**
```python
def greet(name: str) -> str:
    return f"Hello {name}"

print(greet("Khang"))
```

**Ví dụ phức tạp hơn:**
```python
from typing import List, Dict

def summarize(numbers: List[int]) -> Dict[str, float]:
    return {
        "sum": sum(numbers),
        "avg": sum(numbers) / len(numbers)
    }

print(summarize([1, 2, 3, 4, 5]))
```

---

## 🚩 7. Lỗi thường gặp

- **Đệ quy vô hạn:** Thiếu base case.
- **Lambda phức tạp:** Viết quá dài dòng, mất dễ đọc.
- **Sai cú pháp List Comprehension:** Quên ngoặc vuông hoặc dùng sai vị trí vòng lặp.

---

## 🎯 Tổng kết nhanh

| Tính năng | Khi nào dùng? |
| --- | --- |
| `*args`, `**kwargs` | Hàm cần linh hoạt số lượng tham số |
| Lambda | Hàm nhỏ, dùng một lần, thường đi với sorted/filter/map |
| Đệ quy | Bài toán chia nhỏ (factorial, fibonacci, cây nhị phân...) |
| List comprehension | Tạo list nhanh, gọn từ các vòng lặp |
| Type hinting | Giúp dễ bảo trì, rõ ràng, hỗ trợ IDE tốt hơn |

---

Chúc bạn thành công và thành thạo Python! 🚀
