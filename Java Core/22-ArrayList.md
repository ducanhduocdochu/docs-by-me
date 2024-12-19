# Tất Tần Tật về ArrayList và So Sánh với Array

## 📋 ArrayList là gì?
`ArrayList` là một lớp trong Java thuộc gói `java.util`, cung cấp một danh sách động có khả năng tự động thay đổi kích thước. 
Không giống như mảng (`Array`), `ArrayList` có thể lưu trữ các phần tử không giới hạn kích thước và hỗ trợ nhiều phương thức hữu ích để thao tác với dữ liệu.

### ⚙️ Cách tạo ArrayList
```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");

        System.out.println(list); // [A, B, C]
    }
}
```

---

## 💡 Đặc điểm chính của ArrayList

### 1. **Kích thước động**
- ArrayList tự động tăng kích thước khi cần thêm phần tử.
- Ngược lại, Array có kích thước cố định và không thể thay đổi sau khi khởi tạo.

### 2. **Lưu trữ các đối tượng**
- ArrayList chỉ lưu trữ các đối tượng, không thể lưu trữ kiểu dữ liệu nguyên thủy (Primitive).
  - Ví dụ: Thay vì `int`, bạn phải dùng `Integer`.
- Array có thể lưu trữ cả đối tượng và kiểu nguyên thủy.

### 3. **Các phương thức hỗ trợ**
ArrayList cung cấp nhiều phương thức hỗ trợ như:
- `add(E element)`: Thêm phần tử.
- `remove(Object o)`: Xóa phần tử.
- `get(int index)`: Lấy phần tử tại vị trí chỉ định.
- `size()`: Trả về số lượng phần tử hiện tại.

---

## 🔍 So sánh ArrayList và Array

| **Đặc điểm**           | **ArrayList**                                     | **Array**                     |
|-------------------------|---------------------------------------------------|--------------------------------|
| **Kích thước**         | Động (có thể tăng giảm tự động).                  | Cố định (đã khai báo thì không thể thay đổi). |
| **Hiệu năng**          | Chậm hơn Array vì có cơ chế resize.               | Nhanh hơn trong thao tác trực tiếp. |
| **Kiểu dữ liệu**       | Lưu trữ đối tượng (Wrapper).                     | Có thể lưu cả kiểu nguyên thủy lẫn đối tượng. |
| **Phương thức hỗ trợ** | Nhiều phương thức tiện dụng (add, remove, size).  | Không có phương thức hỗ trợ, thao tác thủ công. |
| **Sử dụng bộ nhớ**     | Tốn bộ nhớ hơn do quản lý thêm các phương thức.    | Tối ưu hơn cho dữ liệu cố định. |

---

## 📚 Khi nào nên dùng Array và ArrayList?

### Dùng `Array` khi:
- Bạn biết trước kích thước dữ liệu.
- Hiệu năng là ưu tiên hàng đầu.
- Cần lưu trữ dữ liệu nguyên thủy để tiết kiệm bộ nhớ.

### Dùng `ArrayList` khi:
- Dữ liệu có kích thước không cố định và cần mở rộng thường xuyên.
- Cần sử dụng các phương thức hỗ trợ mạnh mẽ để thao tác trên danh sách.
- Yêu cầu xử lý linh hoạt với các cấu trúc dữ liệu.

---

## ✨ Ví dụ minh họa so sánh

### Array
```java
public class ArrayExample {
    public static void main(String[] args) {
        int[] arr = new int[3];
        arr[0] = 10;
        arr[1] = 20;
        arr[2] = 30;

        // Không thể thêm phần tử thứ 4
        // arr[3] = 40; // Lỗi

        for (int num : arr) {
            System.out.println(num);
        }
    }
}
```

### ArrayList
```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40); // Không có giới hạn

        for (int num : list) {
            System.out.println(num);
        }
    }
}
```

---

## 🚀 Tổng Kết
- **Array** phù hợp khi bạn cần hiệu năng cao và dữ liệu cố định.
- **ArrayList** là lựa chọn linh hoạt cho các ứng dụng yêu cầu xử lý danh sách động.

👉 Lựa chọn đúng giữa Array và ArrayList sẽ giúp cải thiện hiệu năng và quản lý dữ liệu hiệu quả hơn!

---

📝 **Created by ducanhduocdochu**
