# Tất Tần Tật về Java Autoboxing/Unboxing

## 📋 Autoboxing là gì?
Autoboxing là quá trình tự động chuyển đổi từ **kiểu dữ liệu nguyên thủy (Primitive)** sang **đối tượng Wrapper (Wrapper Object)**.

- **Ví dụ:**
  ```java
  int primitive = 5;
  Integer wrapper = primitive; // Autoboxing
  ```

## 📋 Unboxing là gì?
Unboxing là quá trình ngược lại, tự động chuyển đổi từ **đối tượng Wrapper** về **kiểu dữ liệu nguyên thủy**.

- **Ví dụ:**
  ```java
  Integer wrapper = 10;
  int primitive = wrapper; // Unboxing
  ```

## ⚙️ Cách hoạt động
Autoboxing và Unboxing được Java thực hiện tự động nhờ tính năng hỗ trợ từ trình biên dịch (compiler).

- **Autoboxing:**
  ```java
  List<Integer> numbers = new ArrayList<>();
  numbers.add(1); // Compiler tự động chuyển 1 thành Integer.valueOf(1)
  ```

- **Unboxing:**
  ```java
  Integer number = 20;
  int result = number + 5; // Compiler tự động chuyển number thành number.intValue()
  ```

## 💡 Lợi ích
- **Mã nguồn gọn gàng:**
  Không cần gọi thủ công các phương thức như `Integer.valueOf()` hoặc `intValue()`.
- **Dễ sử dụng:**
  Hỗ trợ các cấu trúc dữ liệu sử dụng Generics như `List`, `Map`.

## ⚠️ Lưu ý

### 1. Hiệu năng
Autoboxing/Unboxing có thể gây ra chi phí ẩn do tạo đối tượng hoặc gọi phương thức.
  ```java
  Integer a = 1000;
  Integer b = 1000;
  System.out.println(a == b); // false vì hai đối tượng khác nhau
  ```

### 2. NullPointerException
Cẩn thận khi unboxing `null` giá trị:
  ```java
  Integer num = null;
  int value = num; // Lỗi NullPointerException
  ```

### 3. So sánh
Sử dụng `equals()` thay vì `==` khi so sánh các đối tượng Wrapper:
  ```java
  Integer x = 100;
  Integer y = 100;
  System.out.println(x == y); // true (do caching trong khoảng -128 đến 127)

  Integer m = 200;
  Integer n = 200;
  System.out.println(m == n); // false
  ```

## 🔑 Tổng Kết
- **Autoboxing và Unboxing** giúp viết mã Java gọn gàng và dễ bảo trì hơn, nhưng cần hiểu rõ để tránh các vấn đề liên quan đến hiệu năng và lỗi runtime.
- Quản lý đúng cách sẽ cải thiện hiệu quả sử dụng bộ nhớ và hiệu năng ứng dụng.

✨ **Mẹo:** Sử dụng các kỹ thuật tối ưu và kiểm tra kỹ khi làm việc với Autoboxing/Unboxing để tránh các lỗi không mong muốn!

---

📝 **Created by ducanhduocdochu**
