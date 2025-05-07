
# 📌 Python Tuần 9: Sử dụng từ khóa `with` để đọc và ghi file

---

## 🚩 Tổng quan về quản lý file trong Python

Trong Python, việc đọc/ghi file cần quản lý chặt chẽ để tránh lỗi mất dữ liệu, leak tài nguyên.

- Từ khóa `with` đảm bảo file tự động đóng khi không sử dụng nữa.
- An toàn, tiện lợi, code sạch và chuyên nghiệp.

---

## 🚩 1. Cấu trúc cơ bản của `with`

Cú pháp tổng quát:

```python
with open('filename', 'mode') as file:
    # Thực hiện các thao tác trên file
```

- File sẽ được tự động đóng khi khối with kết thúc.

---

## 🚩 2. Các mode thông dụng

- `'r'`: đọc file (mặc định)
- `'w'`: ghi đè file (tạo mới nếu chưa có)
- `'a'`: ghi nối tiếp file
- `'r+'`: đọc và ghi
- `'w+'`: ghi và đọc, xóa hết nội dung file cũ
- `'a+'`: ghi nối và đọc

---

## 🚩 3. Đọc file (`'r'`)

Ví dụ cơ bản đọc nội dung file:

```python
with open('example.txt', 'r', encoding='utf-8') as file:
    content = file.read()
    print(content)
```

**Đọc từng dòng:**

```python
with open('example.txt', 'r', encoding='utf-8') as file:
    for line in file:
        print(line.strip())
```

---

## 🚩 4. Ghi file (`'w'` và `'a'`)

**Ghi đè nội dung mới:**

```python
with open('output.txt', 'w', encoding='utf-8') as file:
    file.write("Hello, Khang!\n")
    file.write("This is a new file.")
```

**Ghi nối tiếp nội dung:**

```python
with open('output.txt', 'a', encoding='utf-8') as file:
    file.write("\nAdding new content.")
```

---

## 🚩 5. Kết hợp đọc và ghi (`'r+'`, `'w+'`, `'a+'`)

Ví dụ nâng cao với `r+`:

```python
with open('data.txt', 'r+', encoding='utf-8') as file:
    data = file.read()
    file.seek(0)  # quay về đầu file để ghi
    file.write("New line added\n" + data)
```

---

## 🚩 6. Quản lý file nhị phân (binary files)

Mode thêm `b` để đọc/ghi file nhị phân (ảnh, âm thanh...)

**Ví dụ ghi ảnh:**

```python
with open('image.png', 'rb') as src:
    content = src.read()

with open('copy_image.png', 'wb') as dest:
    dest.write(content)
```

---

## 🚩 7. Xử lý ngoại lệ (Exceptions)

Nên xử lý ngoại lệ khi thao tác file:

```python
try:
    with open('example.txt', 'r', encoding='utf-8') as file:
        content = file.read()
        print(content)
except FileNotFoundError:
    print("File không tồn tại!")
except IOError:
    print("Lỗi khi đọc file!")
```

---

## 🚩 8. Context Manager (nâng cao)

Có thể tự tạo context manager bằng class:

```python
class CustomFile:
    def __init__(self, filename, mode):
        self.file = open(filename, mode)

    def __enter__(self):
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        self.file.close()

with CustomFile('example.txt', 'w') as file:
    file.write("Dùng Custom Context Manager")
```

Hoặc dùng decorator `@contextmanager`:

```python
from contextlib import contextmanager

@contextmanager
def custom_open(filename, mode):
    file = open(filename, mode)
    try:
        yield file
    finally:
        file.close()

with custom_open('example.txt', 'w') as file:
    file.write("Dùng decorator context manager")
```

---

## 🚩 9. Các lỗi thường gặp

- 🔴 Quên encoding: lỗi khi đọc ghi unicode
- 🔴 Sai chế độ mode: lỗi không như mong muốn
- 🔴 Quên seek(): khi vừa đọc vừa ghi (`r+`, `w+`, `a+`)

---

## 🎯 Tổng kết nhanh

| Mode | Công dụng | Lưu ý |
|------|-----------|-------|
| `'r'`| Chỉ đọc | File phải tồn tại |
| `'w'`| Ghi đè | Xóa dữ liệu cũ |
| `'a'`| Ghi nối | Không xóa dữ liệu cũ |
| `'r+'`| Đọc + ghi | Cần chú ý vị trí con trỏ |
| `'w+'`| Ghi đè + đọc | Xóa dữ liệu cũ |
| `'a+'`| Ghi nối + đọc | Ghi ở cuối file |

---

Chúc bạn nắm vững và làm chủ kỹ thuật thao tác file! 🚀
