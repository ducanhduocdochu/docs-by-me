# Tất Tần Tật về Abstract Class trong Java

## 1. Abstract Class là gì?
**Abstract Class** (lớp trừu tượng) là một lớp không thể được khởi tạo trực tiếp. Nó được sử dụng để cung cấp một khung hoặc chuẩn cho các lớp con kế thừa.

- **Cú pháp:**
  ```java
  abstract class ClassName {
      // Các thuộc tính và phương thức
  }
  ```
- Một lớp trừu tượng có thể chứa:
  - Phương thức trừu tượng (không có thân hàm).
  - Phương thức cụ thể (có thân hàm).

---

## 2. Tại sao cần Abstract Class?
- **Định nghĩa một chuẩn chung** cho các lớp con.
- **Giảm thiểu lặp lại mã nguồn** bằng cách cung cấp các phương thức cụ thể.
- **Hỗ trợ tính đa hình**: Cho phép các lớp con thực hiện các hành vi cụ thể riêng của chúng.

---

## 3. Đặc điểm của Abstract Class
- Không thể khởi tạo trực tiếp.
  ```java
  abstract class Animal {
      abstract void sound();
  }

  Animal animal = new Animal(); // Lỗi biên dịch
  ```
- Có thể chứa cả **phương thức trừu tượng** và **phương thức cụ thể**.
- Có thể có **constructor** để khởi tạo thuộc tính chung cho các lớp con.
- Có thể có các **biến tĩnh** và **hằng số**.

---

## 4. Abstract Method
Phương thức trừu tượng không có thân hàm và phải được lớp con ghi đè.

- **Khai báo:**
  ```java
  abstract class Animal {
      abstract void sound(); // Phương thức trừu tượng
  }

  class Dog extends Animal {
      @Override
      void sound() {
          System.out.println("Woof Woof");
      }
  }
  ```

---

## 5. Ví dụ chi tiết về Abstract Class
### Ví dụ 1: Lớp trừu tượng đơn giản
```java
abstract class Animal {
    abstract void sound();

    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Woof Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
        dog.eat();
    }
}
```
**Kết quả:**
```
Woof Woof
This animal eats food.
```

### Ví dụ 2: Abstract Class với Constructor
```java
abstract class Shape {
    String color;

    Shape(String color) {
        this.color = color;
    }

    abstract double area();

    void displayColor() {
        System.out.println("Color: " + color);
    }
}

class Circle extends Shape {
    double radius;

    Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle("Red", 5.0);
        circle.displayColor();
        System.out.println("Area: " + circle.area());
    }
}
```
**Kết quả:**
```
Color: Red
Area: 78.53981633974483
```

---

## 6. Abstract Class vs Interface
| **Thuộc tính**               | **Abstract Class**                     | **Interface**                            |
|------------------------------|----------------------------------------|-----------------------------------------|
| **Phương thức trừu tượng**   | Có thể có phương thức cụ thể           | Chỉ chứa phương thức mặc định/tĩnh (Java 8 trở lên) |
| **Kế thừa**                  | Chỉ kế thừa từ một lớp trừu tượng      | Có thể triển khai nhiều interface       |
| **Constructor**              | Có                                      | Không                                    |
| **Biến**                     | Có thể có biến instance                | Chỉ chứa hằng số (final static)         |

---

## 7. Khi nào sử dụng Abstract Class?
1. Khi bạn muốn cung cấp một **chuẩn chung** cho các lớp con.
2. Khi có **hành vi mặc định** mà các lớp con có thể dùng lại.
3. Khi các lớp con có mối quan hệ gần gũi (cùng loại).

---

## 8. Kết luận
- Abstract Class là công cụ mạnh mẽ để xây dựng cấu trúc kế thừa trong Java.
- Hiểu rõ các đặc điểm và cách sử dụng Abstract Class sẽ giúp bạn thiết kế hệ thống linh hoạt, dễ mở rộng.

👉 **Mẹo:** Sử dụng Abstract Class khi cần định nghĩa hành vi chung, và Interface khi cần tính đa kế thừa. 🚀

---

📝 **Created by ducanhduocdochu**
