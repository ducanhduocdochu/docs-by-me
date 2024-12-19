# Tất Tần Tật về Strings trong Java

## 1. String là gì?
**String** là một lớp trong Java, đại diện cho một chuỗi ký tự. String là **immutable**, nghĩa là một khi được tạo ra, nội dung của nó không thể thay đổi.

- **Khai báo String:**
  ```java
  String str1 = "Hello";
  String str2 = new String("World");
  ```

- **Tại sao String là immutable?**
  - Để đảm bảo tính an toàn và hiệu suất trong các ứng dụng đa luồng.
  - Giúp dễ dàng chia sẻ chuỗi trong bộ nhớ mà không lo bị thay đổi.

---

## 2. Các phương thức quan trọng của String

| **Phương thức**                | **Mô tả**                             | **Ví dụ**                                  |
|--------------------------------|---------------------------------------|-------------------------------------------|
| `length()`                     | Trả về độ dài chuỗi                   | `str.length()` -> `5`                     |
| `charAt(index)`                | Lấy ký tự tại vị trí chỉ định         | `str.charAt(1)` -> `e`                    |
| `substring(begin, end)`        | Trích xuất chuỗi con                 | `str.substring(1, 4)` -> `ell`            |
| `equals(otherString)`          | So sánh nội dung chuỗi               | `str.equals("Hello")` -> `true`         |
| `equalsIgnoreCase(otherString)`| So sánh nội dung không phân biệt hoa thường | `str.equalsIgnoreCase("hello")` -> `true` |
| `toUpperCase()`                | Chuyển chuỗi sang chữ hoa            | `str.toUpperCase()` -> `HELLO`            |
| `toLowerCase()`                | Chuyển chuỗi sang chữ thường         | `str.toLowerCase()` -> `hello`            |
| `trim()`                       | Loại bỏ khoảng trắng đầu/cuối        | `" Hello ".trim()` -> `"Hello"`         |
| `replace(oldChar, newChar)`    | Thay thế ký tự                       | `str.replace('e', 'a')` -> `Hallo`        |

---

## 3. String Pool
String Pool là một vùng nhớ đặc biệt trong Heap, nơi các chuỗi được lưu trữ để tái sử dụng.

- **Ví dụ:**
  ```java
  String s1 = "Hello";
  String s2 = "Hello";
  System.out.println(s1 == s2); // true

  String s3 = new String("Hello");
  System.out.println(s1 == s3); // false
  ```
- **Giải thích:**
  - `s1` và `s2` cùng tham chiếu đến một đối tượng trong String Pool.
  - `s3` tạo đối tượng mới trong Heap.

---

## 4. Các lớp StringBuilder và StringBuffer
### 4.1. StringBuilder
- **Đặc điểm:**
  - Mutable (có thể thay đổi).
  - Hiệu năng cao hơn StringBuffer vì không đồng bộ (non-synchronized).

- **Ví dụ:**
  ```java
  StringBuilder sb = new StringBuilder("Hello");
  sb.append(" World");
  System.out.println(sb.toString()); // Hello World
  ```

### 4.2. StringBuffer
- **Đặc điểm:**
  - Mutable.
  - Đồng bộ (synchronized), thích hợp cho môi trường đa luồng.

- **Ví dụ:**
  ```java
  StringBuffer sb = new StringBuffer("Hello");
  sb.append(" World");
  System.out.println(sb.toString()); // Hello World
  ```

### So sánh String, StringBuilder và StringBuffer
| **Thuộc tính**   | **String**     | **StringBuilder** | **StringBuffer** |
|-------------------|----------------|-------------------|------------------|
| **Immutable**    | Có             | Không             | Không            |
| **Đồng bộ**       | Không          | Không             | Có               |
| **Hiệu năng**    | Chậm hơn       | Nhanh hơn         | Chậm hơn StringBuilder |

---

## 5. Một số mẹo khi làm việc với String

1. **Sử dụng StringBuilder/StringBuffer khi xử lý chuỗi lớn:**
   ```java
   StringBuilder sb = new StringBuilder();
   for (int i = 0; i < 1000; i++) {
       sb.append(i);
   }
   ```

2. **Tránh so sánh chuỗi bằng `==`:**
   ```java
   String s1 = "Hello";
   String s2 = new String("Hello");
   System.out.println(s1.equals(s2)); // true
   System.out.println(s1 == s2);      // false
   ```

3. **Sử dụng `split()` để chia chuỗi:**
   ```java
   String str = "Java,Python,C++";
   String[] languages = str.split(",");
   for (String lang : languages) {
       System.out.println(lang);
   }
   ```

---

## 6. Kết luận
- **String**: Dùng cho các chuỗi cố định, không thay đổi.
- **StringBuilder**: Dùng cho các thao tác xử lý chuỗi trong môi trường đơn luồng.
- **StringBuffer**: Dùng cho các thao tác xử lý chuỗi trong môi trường đa luồng.

👉 **Mẹo:** Hiểu rõ các đặc điểm của từng loại để lựa chọn phù hợp với nhu cầu của ứng dụng! 🚀

---

📝 **Created by ducanhduocdochu**
