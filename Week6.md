# **Tóm tắt kiến thức Python Tuần 6 - COP2510**

---

## I. Vòng lặp cơ bản và tổng quát

### 1. Vòng lặp `for`

* Cú pháp:

  ```python
  for biến in dãy:
      # khối lệnh
  ```
* Ví dụ:

  ```python
  for i in range(5):
      print(i)  # Kết quả: 0 1 2 3 4
  ```

### 2. Vòng lặp `while`

* Cú pháp:

  ```python
  while điều_kiện:
      # khối lệnh
  ```
* Ví dụ:

  ```python
  i = 0
  while i < 5:
      print(i)
      i += 1
  ```

## II. Vòng lặp lồng nhau (nested loop)

```python
for i in range(2):
    for j in range(3):
        print(f"i={i}, j={j}")
```

---

## III. Vòng lặp với `else`

* Phần `else` sẽ **chỉ chạy nếu vòng lặp không bị `break`**.

Ví dụ 1 (không có `break`):

```python
for i in range(3):
    print(i)
else:
    print("Kết thúc vòng lặp")  # Sẽ chạy
```

Ví dụ 2 (có `break`):

```python
for i in range(5):
    if i == 3:
        break
else:
    print("Kết thúc vòng lặp")  # Không chạy
```

---

## IV. Hàm random và phạm vi giá trị

```python
import random

random.randint(a, b)    # Số nguyên trong khoảng [a, b]
random.randrange(a, b)  # Số nguyên trong khoảng [a, b)
random.random()         # Số thực trong khoảng [0.0, 1.0)
random.uniform(a, b)    # Số thực trong khoảng [a, b]
```

| Hàm               | Kiểu trả về | Khoảng giá trị | Có bao gồm giá trị cuối? |
| ----------------- | ----------- | -------------- | ------------------------ |
| `randint(1, 5)`   | int         | 1 đến 5        | Có                       |
| `randrange(1, 5)` | int         | 1 đến 4        | Không                    |
| `random()`        | float       | 0.0 đến <1.0   | Không                    |
| `uniform(1, 5)`   | float       | 1.0 đến 5.0    | Có                       |

---

## V. Câu lệnh `break` và `continue`

### `break`: thoát khỏi vòng lặp

### `continue`: bỏ qua lần lặp hiện tại

Ví dụ:

```python
for i in range(5):
    if i == 2:
        continue  # Bỏ qua in 2
    if i == 4:
        break     # Thoát vòng lặp khi i = 4
    print(i)      # Kết quả: 0, 1, 3
```

---

## VI. Hàm `enumerate()`

* Dùng để lấy **chỉ số và giá trị** trong vòng lặp:

```python
fruits = ['tao', 'chuoi', 'xoai']
for index, fruit in enumerate(fruits):
    print(index, fruit)
# Kết quả:
# 0 tao
# 1 chuoi
# 2 xoai
```

---

## VII. Hàm bị ghi đè (overwritten functions)

* Khi định nghĩa 2 hàm cùng tên, hàm sau **sẽ thay thế hàm trước**.

```python
def xin_chao():
    print("Hello")

def xin_chao():
    print("Xin chào")

xin_chao()  # Kết quả: Xin chào
```

⚠️ Python **không hỗ trợ** overload nhiều hàm giống như C++/Java.

---

## VIII. Tổng kết nhanh

* `else` trong vòng lặp chỉ chạy khi **không có `break`**
* `break` thoát vòng lặp ngay lập tức
* `continue` bỏ qua vòng lặp hiện tại
* `enumerate()` giúp có chỉ số trong vòng `for`
* Hàm `random` có sự khác biệt rõ ràng về phạm vi và kiểu dữ liệu
* Định nghĩa lại hàm cùng tên sẽ ghi đè hàm cũ

---

## Bài tập gợi ý

1. In ra các số từ 1 đến 10, bỏ qua số chia hết cho 3.
2. Viết vòng `while` đoán số ngẫu nhiên cho đến khi đúng.
3. Dùng `for-else` để kiểm tra xem có số nào chia hết cho 7 trong list hay không.
4. Viết 2 hàm cùng tên, xem hàm nào được gọi.

---

**Gợi ý ôn tập:**

* Thử viết các đoạn code có dùng cả `break`, `continue`, `else`
* In thử kết quả các hàm `random`
* Dùng `enumerate()` trong lặp để hiểu cách hoạt động
* Viết lại các hàm để thấy ghi đè diễn ra
