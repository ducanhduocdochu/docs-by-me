
# 🛠️ Lập trình hướng đối tượng (OOP): Tính kế thừa

## 📌 Tính kế thừa là gì?
Tính kế thừa là một đặc tính của lập trình hướng đối tượng, cho phép một lớp (class) con thừa hưởng các thuộc tính và phương thức từ một lớp cha (superclass). Điều này giúp tái sử dụng mã, giảm trùng lặp, và hỗ trợ mở rộng tính năng một cách dễ dàng.

---

## 🌟 Các đặc điểm chính của tính kế thừa
1. **Thừa hưởng thuộc tính và phương thức**: Lớp con có thể sử dụng lại mã từ lớp cha mà không cần định nghĩa lại.
2. **Mở rộng lớp cha**: Lớp con có thể thêm các thuộc tính và phương thức mới hoặc ghi đè (override) các phương thức của lớp cha.
3. **Phân cấp**: Cấu trúc kế thừa cho phép tổ chức mã theo dạng cây phân cấp.

---

## 🛠️ Ví dụ về tính kế thừa

### 🖋️ Triển khai mã
```java
// Lớp cha
class Animal {
    // Phương thức của lớp cha
    void eat() {
        System.out.println("Động vật đang ăn...");
    }
}

// Lớp con thừa kế lớp cha
class Dog extends Animal {
    // Ghi đè phương thức của lớp cha
    @Override
    void eat() {
        System.out.println("Chó đang ăn...");
    }

    // Phương thức riêng của lớp con
    void bark() {
        System.out.println("Chó sủa: Gâu gâu!");
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        // Tạo đối tượng của lớp Dog
        Dog dog = new Dog();

        // Gọi phương thức từ lớp cha và lớp con
        dog.eat(); // Xuất: Chó đang ăn...
        dog.bark(); // Xuất: Chó sủa: Gâu gâu!
    }
}
```

---

### 🔍 Giải thích mã
1. **Lớp Cha (`Animal`)**:
   - Chứa một phương thức `eat()` để thể hiện hành vi chung của các loài động vật.
2. **Lớp Con (`Dog`)**:
   - Kế thừa phương thức `eat()` từ lớp `Animal` và ghi đè (override) nó để thay đổi hành vi.
   - Thêm một phương thức riêng `bark()` để mô tả hành vi cụ thể của loài chó.
3. **Ghi đè phương thức**: Lớp con thay thế hoặc mở rộng hành vi của lớp cha thông qua từ khóa `@Override`.

---

## 🚀 Lợi ích của tính kế thừa
- **Tái sử dụng mã**: Giảm thiểu việc viết lại mã, tăng hiệu quả lập trình.
- **Dễ mở rộng**: Cho phép thêm hoặc sửa đổi chức năng mà không ảnh hưởng đến lớp cha.
- **Tổ chức mã tốt hơn**: Dễ quản lý các lớp và mối quan hệ giữa chúng.

---

## ⚡ Các trường hợp sử dụng phổ biến
- **Hệ thống phân cấp**: Mô hình hóa các đối tượng theo phân cấp như nhân viên, quản lý, giám đốc.
- **Mở rộng chức năng**: Thêm các tính năng mới vào một lớp hiện có mà không làm thay đổi mã gốc.

---

🔗 **Tính kế thừa là một công cụ mạnh mẽ trong OOP, giúp bạn tổ chức và tái sử dụng mã hiệu quả hơn. Hãy áp dụng nó đúng cách để xây dựng các ứng dụng mạnh mẽ!** 🎉

---

📝 **Created by ducanhduocdochu**
