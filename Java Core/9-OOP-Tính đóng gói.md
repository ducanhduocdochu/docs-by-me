# 🛠️ Lập trình hướng đối tượng (OOP): Tính đóng gói

## 📌 Tính đóng gói là gì?
Tính đóng gói là quá trình gói gọn dữ liệu (biến) và các phương thức (hàm) hoạt động trên dữ liệu vào trong một đơn vị duy nhất, thường là một lớp (class). Đây là một trong những nguyên tắc cốt lõi của lập trình hướng đối tượng (OOP).

---

## 🌟 Các đặc điểm chính của tính đóng gói
1. **Ẩn dữ liệu**: Hạn chế truy cập trực tiếp vào một số thành phần của đối tượng, giúp mã an toàn và dễ bảo trì hơn.
2. **Kiểm soát truy cập**: Cung cấp các phương thức công khai (getter/setter) để thay đổi và xem dữ liệu riêng tư.
3. **Cải thiện khả năng bảo trì**: Thay đổi triển khai bên trong không ảnh hưởng đến các phần khác của chương trình.
4. **Tái sử dụng**: Mã đã được đóng gói có thể tái sử dụng mà không lộ thông tin nhạy cảm.

---

## 🛠️ Ví dụ về tính đóng gói

### 🖋️ Triển khai mã
```java
// Lớp với tính đóng gói
class Student {
    // Biến private (ẩn dữ liệu)
    private String name;
    private int age;

    // Getter công khai cho name
    public String getName() {
        return name;
    }

    // Setter công khai cho name
    public void setName(String name) {
        this.name = name;
    }

    // Getter công khai cho age
    public int getAge() {
        return age;
    }

    // Setter công khai cho age
    public void setAge(int age) {
        if (age > 0) { // Xác thực dữ liệu đầu vào
            this.age = age;
        } else {
            System.out.println("Tuổi không hợp lệ");
        }
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        // Tạo đối tượng của lớp Student
        Student student = new Student();

        // Sử dụng setter để gán giá trị
        student.setName("Alice");
        student.setAge(20);

        // Sử dụng getter để lấy giá trị
        System.out.println("Tên: " + student.getName());
        System.out.println("Tuổi: " + student.getAge());

        // Thử gán tuổi không hợp lệ
        student.setAge(-5); // Xuất: Tuổi không hợp lệ
    }
}
```

---

### 🔍 Giải thích mã
1. **Biến Private**: Các biến `name` và `age` được khai báo là `private` để ngăn chặn truy cập trực tiếp.
2. **Getter và Setter**:
   - Phương thức `getName()` và `getAge()` cho phép đọc dữ liệu một cách kiểm soát.
   - Phương thức `setName()` và `setAge()` cho phép ghi dữ liệu và đảm bảo tính toàn vẹn với xác thực.
3. **Lớp chính**: Minh họa tính đóng gói bằng cách truy cập các biến private qua các phương thức công khai.

---

## 🚀 Lợi ích của tính đóng gói
- **Bảo mật**: Ngăn chặn truy cập trái phép vào các thành phần của lớp.
- **Linh hoạt**: Cho phép thay đổi triển khai bên trong mà không ảnh hưởng đến mã bên ngoài.
- **Dễ đọc**: Mã được chia thành các phần nhỏ gọn, dễ hiểu.

---

## ⚡ Các trường hợp sử dụng phổ biến
- **Hệ thống ngân hàng**: Bảo vệ dữ liệu nhạy cảm như số tài khoản hoặc số dư.
- **Xác thực**: Quản lý thông tin đăng nhập của người dùng một cách an toàn.

---

🔗 **Tính đóng gói là nền tảng để viết mã bảo mật và đáng tin cậy trong lập trình hướng đối tượng. Hãy nắm vững để viết các chương trình Java tốt hơn!** 🎉

---

📝 **Created by ducanhduocdochu**
