
# 📌 Python Tuần 13: Kế thừa – Đơn, Đa kế thừa và `super()` chuyên sâu

---

## 🚩 1. Kế thừa trong Python là gì?

Kế thừa (inheritance) cho phép một lớp con kế thừa thuộc tính và phương thức từ lớp cha. Giúp **tái sử dụng code**, dễ mở rộng và duy trì.

---

## 🚩 2. Single Inheritance (Đơn kế thừa)

Một lớp con kế thừa từ **một** lớp cha.

**Ví dụ đơn giản:**
```python
class NhanVien:
    def __init__(self, ten):
        self.ten = ten

    def lam_viec(self):
        print(f"{self.ten} đang làm việc.")

class LapTrinhVien(NhanVien):
    def viet_code(self):
        print(f"{self.ten} đang viết code.")

ltv = LapTrinhVien("Khang")
ltv.lam_viec()
ltv.viet_code()
```

---

## 🚩 3. Dùng `super()` trong single inheritance

`super()` dùng để gọi phương thức từ lớp cha – thường dùng trong `__init__()` hoặc khi override method.

**Ví dụ dùng `super()` trong constructor:**
```python
class NhanVien:
    def __init__(self, ten):
        self.ten = ten

class LapTrinhVien(NhanVien):
    def __init__(self, ten, ngon_ngu):
        super().__init__(ten)  # Gọi init của lớp cha
        self.ngon_ngu = ngon_ngu

    def __str__(self):
        return f"{self.ten} - {self.ngon_ngu}"

ltv = LapTrinhVien("Khang", "Python")
print(ltv)
```

**Lỗi thường gặp:**
- 🔴 Quên `super().__init__()` dẫn đến thiếu thuộc tính.
- 🔴 Gọi sai thứ tự đối số.

---

## 🚩 4. Multiple Inheritance (Đa kế thừa)

Lớp con kế thừa từ **nhiều lớp cha**.

**Cú pháp:**
```python
class A:
    pass

class B:
    pass

class C(A, B):  # kế thừa cả A và B
    pass
```

**Ví dụ cụ thể:**
```python
class Cha:
    def chao(self):
        print("Chào từ Cha")

class Me:
    def yeu_thuong(self):
        print("Yêu thương từ Mẹ")

class Con(Cha, Me):
    pass

con = Con()
con.chao()
con.yeu_thuong()
```

---

## 🚩 5. Method Resolution Order (MRO)

Khi kế thừa nhiều lớp, Python dùng **MRO** để xác định thứ tự gọi phương thức.

**Kiểm tra MRO:**
```python
print(Con.__mro__)
```

**Lỗi thường gặp:**
- 🔴 Trùng tên phương thức trong nhiều lớp cha dẫn đến kết quả không như mong đợi nếu không hiểu MRO.

---

## 🚩 6. Gọi `super()` trong multiple inheritance

Trong đa kế thừa, `super()` gọi theo MRO, không đơn giản là lớp cha trực tiếp.

**Ví dụ nâng cao:**
```python
class A:
    def __init__(self):
        print("A init")
        super().__init__()

class B:
    def __init__(self):
        print("B init")
        super().__init__()

class C(A, B):
    def __init__(self):
        print("C init")
        super().__init__()

c = C()
# Kết quả:
# C init
# A init
# B init
```

---

## 🚩 7. Override phương thức và dùng `super()` nâng cao

```python
class Animal:
    def speak(self):
        print("Animal sound")

class Dog(Animal):
    def speak(self):
        super().speak()
        print("Woof woof")

d = Dog()
d.speak()
```

---

## 🚩 8. Sử dụng mixin với multiple inheritance

Mixin: lớp chỉ chứa phương thức bổ sung, không có `__init__()`.

```python
class WalkMixin:
    def walk(self):
        print("Walking...")

class TalkMixin:
    def talk(self):
        print("Talking...")

class Human(WalkMixin, TalkMixin):
    pass

h = Human()
h.walk()
h.talk()
```

---

## 🚩 9. Tổng kết lỗi thường gặp

| Lỗi | Mô tả |
|-----|-------|
| Quên gọi `super()` | Không kế thừa đầy đủ |
| Trùng tên method | Không rõ ràng khi MRO xử lý |
| Gọi sai thứ tự `__init__()` | Gây lỗi `TypeError` |
| Kế thừa nhiều lớp mà không hiểu MRO | Kết quả bất ngờ |

---

## 🎯 Tổng kết nhanh

| Khái niệm | Giải thích |
|----------|------------|
| Single Inheritance | Kế thừa từ một lớp cha |
| Multiple Inheritance | Kế thừa từ nhiều lớp cha |
| `super()` | Gọi phương thức/lớp cha theo MRO |
| MRO | Quy tắc xác định thứ tự gọi phương thức |
| Mixin | Lớp bổ sung hành vi, không độc lập |

---

Hãy luyện tập với các sơ đồ MRO, nhiều lớp kế thừa và override để hiểu sâu hơn! 💡
