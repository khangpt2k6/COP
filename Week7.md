
# 📌 Tổng hợp kiến thức Python: Hàm, Biến và Tham số

---

## 🚩 1. Luồng thực thi hàm (Flow of execution)

Luồng thực thi là thứ tự Python chạy code:
- Từ trên xuống dưới
- Khi gặp hàm, chạy vào hàm rồi quay về.

**Ví dụ:**

```python
def greet(name):
    print("Hello,", name)

def main():
    print("Bắt đầu")
    greet("Khang")
    print("Kết thúc")

main()
```

---

## 🚩 2. Biến toàn cục và biến cục bộ

### ✅ Biến cục bộ (Local variables):
- Được khai báo trong hàm, chỉ dùng trong hàm.

```python
def func():
    x = 10
    print("Local x:", x)

func()
```

### ✅ Biến toàn cục (Global variables):
- Khai báo ngoài hàm, dùng được mọi nơi.

```python
x = 20

def func():
    print("Global x:", x)

func()
print(x)
```

### 📌 Sửa đổi biến toàn cục trong hàm:

```python
x = 10
def change_global():
    global x
    x = 20

change_global()
print(x)
```

---

## 🚩 3. Tham số mặc định (Default parameters)

- Giá trị mặc định dùng khi không truyền tham số.

```python
def greet(name, message="Hello"):
    print(message, name)

greet("Khang")
greet("Khang", "Xin chào")
```

---

## 🚩 4. Keyword arguments

- Truyền đối số bằng cách chỉ rõ tên tham số.

```python
def introduce(name, age):
    print(f"{name} is {age} years old")

introduce(age=18, name="Khang")
```

---

## 🚩 5. Kết hợp default và keyword arguments

```python
def create_user(username, password, active=True, role="user"):
    print(f"{username}, active={active}, role={role}")

create_user("khang", "1234")
create_user("admin", "pass", role="admin")
```

---

## 🚩 6. Lỗi thường gặp và cách tránh

- 🔴 Infinite loop, quên return, dùng mutable default parameters
- 🔴 Đặt tham số mặc định trước tham số không mặc định

❌ Sai:
```python
def demo(a=1, b): pass  # lỗi
```

✅ Đúng:
```python
def demo(b, a=1): pass
```

- 🔴 Mutable default parameter:

❌ Sai:
```python
def append_item(item, items=[]):
    items.append(item)
    return items

print(append_item(1))
print(append_item(2))
```

✅ Đúng:
```python
def append_item(item, items=None):
    if items is None:
        items = []
    items.append(item)
    return items

print(append_item(1))
print(append_item(2))
```

---

## 🚩 7. Nâng cao: Unpacking arguments (*args, **kwargs)

```python
def demo(*args, **kwargs):
    print(args, kwargs)

demo(1, 2, a=3, b=4)
```

---

## 🎯 Tổng kết nhanh

| Tình huống               | Cách dùng |
| ------------------------ | --------- |
| Tham số không đổi        | default parameters |
| Tham số bất kỳ thứ tự    | keyword arguments |
| Truy cập toàn chương trình| global |
| Mutable mặc định         | dùng None |

Chúc bạn nắm vững và vận dụng tốt! 🚀

