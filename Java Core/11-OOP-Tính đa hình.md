
# 🛠️ Lập trình hướng đối tượng (OOP): Tính đa hình

## 📌 Tính đa hình là gì?
Tính đa hình (Polymorphism) là khả năng cho phép một phương thức, đối tượng hoặc lớp hoạt động theo nhiều cách khác nhau, dựa trên ngữ cảnh sử dụng. Đây là một tính chất quan trọng trong lập trình hướng đối tượng, giúp cải thiện tính linh hoạt và mở rộng của mã nguồn.

---

## 🌟 Các loại tính đa hình
1. **Đa hình tại runtime (Runtime Polymorphism)**:
   - Xảy ra khi phương thức được ghi đè (override) trong lớp con. Quyết định phương thức nào được gọi chỉ được thực hiện tại thời điểm chạy.
2. **Đa hình tại compile-time (Compile-time Polymorphism)**:
   - Xảy ra khi có sự nạp chồng phương thức (overloading). Quyết định phương thức nào được gọi dựa trên tham số truyền vào khi biên dịch.

---

## 🛠️ Ví dụ về tính đa hình

### 🖋️ Đa hình tại runtime (Override)
```java
// Lớp cha
class Animal {
    void sound() {
        System.out.println("Động vật phát ra âm thanh...");
    }
}

// Lớp con
class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Chó sủa: Gâu gâu!");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Mèo kêu: Meo meo!");
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Dog();
        Animal animal2 = new Cat();

        animal1.sound(); // Xuất: Chó sủa: Gâu gâu!
        animal2.sound(); // Xuất: Mèo kêu: Meo meo!
    }
}
```

### 🖋️ Đa hình tại compile-time (Overload)
```java
class Calculator {
    // Phương thức nạp chồng
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();

        System.out.println("Tổng 2 số: " + calc.add(5, 10)); // Xuất: 15
        System.out.println("Tổng 3 số: " + calc.add(5, 10, 20)); // Xuất: 35
    }
}
```

---

## 🚀 Lợi ích của tính đa hình
- **Tăng tính linh hoạt**: Giúp sử dụng chung một giao diện nhưng có thể tùy chỉnh hành vi.
- **Giảm trùng lặp mã**: Tái sử dụng các phương thức với mục đích khác nhau.
- **Dễ mở rộng**: Dễ dàng thêm hành vi mới mà không ảnh hưởng đến các phần khác.

---

## ⚡ Các trường hợp sử dụng phổ biến
- **Hệ thống quản lý**: Ví dụ, xử lý các loại nhân viên khác nhau (nhân viên bán hàng, quản lý, kỹ thuật).
- **Giao diện người dùng**: Thay đổi cách hiển thị cho từng loại đối tượng khác nhau.

---

🔗 **Tính đa hình là công cụ mạnh mẽ trong OOP, giúp viết mã linh hoạt và dễ mở rộng. Hãy nắm vững để tận dụng tối đa khả năng của nó!** 🎉

---

📝 **Created by ducanhduocdochu**
