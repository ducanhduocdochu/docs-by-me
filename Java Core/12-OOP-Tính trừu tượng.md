# 🛠️ Lập trình hướng đối tượng (OOP): Tính trừu tượng

## 📌 Tính trừu tượng là gì?
Tính trừu tượng (Abstraction) là tính chất của lập trình hướng đối tượng, trong đó chỉ những đặc điểm quan trọng nhất của đối tượng được hiển thị, còn các chi tiết không cần thiết được ẩn đi. Điều này giúp đơn giản hóa việc sử dụng đối tượng và tập trung vào chức năng chính.

---

## 🌟 Các đặc điểm chính của tính trừu tượng
1. **Ẩn chi tiết triển khai**: Người dùng chỉ cần quan tâm đến cách sử dụng mà không cần biết cách nó hoạt động bên trong.
2. **Cải thiện bảo mật**: Bằng cách ẩn đi các phần không cần thiết, bạn có thể giảm thiểu lỗi và bảo vệ dữ liệu.
3. **Tập trung vào logic chính**: Dễ dàng xây dựng hệ thống lớn hơn mà không bị phân tâm bởi các chi tiết nhỏ.

---

## 🛠️ Triển khai tính trừu tượng trong Java
Trong Java, tính trừu tượng được triển khai bằng:
1. **Lớp trừu tượng (Abstract Class)**.
2. **Giao diện (Interface)**.

---

### 🖋️ Ví dụ: Lớp trừu tượng
```java
// Lớp trừu tượng
abstract class Animal {
    // Phương thức trừu tượng (không có phần thân)
    abstract void sound();

    // Phương thức thông thường
    void sleep() {
        System.out.println("Động vật đang ngủ...");
    }
}

// Lớp con kế thừa lớp trừu tượng
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
        Animal dog = new Dog();
        Animal cat = new Cat();

        dog.sound(); // Xuất: Chó sủa: Gâu gâu!
        cat.sound(); // Xuất: Mèo kêu: Meo meo!
        dog.sleep(); // Xuất: Động vật đang ngủ...
    }
}
```

---

### 🖋️ Ví dụ: Giao diện
```java
// Giao diện
interface Vehicle {
    void start();
    void stop();
}

// Lớp triển khai giao diện
class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("Xe hơi bắt đầu chạy...");
    }

    @Override
    public void stop() {
        System.out.println("Xe hơi dừng lại...");
    }
}

class Bike implements Vehicle {
    @Override
    public void start() {
        System.out.println("Xe đạp bắt đầu chạy...");
    }

    @Override
    public void stop() {
        System.out.println("Xe đạp dừng lại...");
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        Vehicle car = new Car();
        Vehicle bike = new Bike();

        car.start(); // Xuất: Xe hơi bắt đầu chạy...
        bike.start(); // Xuất: Xe đạp bắt đầu chạy...
        car.stop();  // Xuất: Xe hơi dừng lại...
    }
}
```

---

## 🚀 Lợi ích của tính trừu tượng
- **Dễ bảo trì và mở rộng**: Giúp xây dựng hệ thống dễ dàng thay đổi hoặc mở rộng chức năng.
- **Giảm độ phức tạp**: Tập trung vào logic chính thay vì các chi tiết triển khai.
- **Tăng khả năng tái sử dụng mã**: Các lớp khác nhau có thể triển khai cùng một giao diện hoặc lớp trừu tượng.

---

## ⚡ Các trường hợp sử dụng phổ biến
- **Hệ thống thanh toán**: Mô tả các phương thức thanh toán như thẻ tín dụng, PayPal, chuyển khoản ngân hàng.
- **Quản lý phương tiện giao thông**: Mô hình hóa xe hơi, xe tải, xe đạp với các đặc điểm chung.

---

🔗 **Tính trừu tượng giúp tập trung vào cốt lõi của vấn đề và xây dựng các hệ thống phần mềm phức tạp một cách dễ dàng. Hãy sử dụng tính năng này để tối ưu hóa mã của bạn!** 🎉

---

📝 **Created by ducanhduocdochu**
