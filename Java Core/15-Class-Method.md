# 🚀 **Tất Tần Tật Về Class Method Trong Java** 📚

## 📚 **1. Giới Thiệu Về Class Method**

Trong Java, **Class Method** (hay còn gọi là **Static Method**) là phương thức được khai báo với từ khóa `static`. Phương thức này không cần đối tượng để gọi mà có thể được gọi trực tiếp từ class.

### 🧩 **Đặc Điểm Của Class Method**

1. **Thuộc về class**, không phải đối tượng cụ thể.
2. Có thể gọi trực tiếp qua tên class.
3. Không thể truy cập trực tiếp vào các thuộc tính hoặc phương thức không `static`.
4. Có thể được sử dụng để thao tác với dữ liệu hoặc logic chung cho tất cả các đối tượng của class.

**Ví dụ:**

```java
class MathUtils {
    // Class Method
    public static int add(int a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        int sum = MathUtils.add(5, 3);
        System.out.println("Sum: " + sum);
    }
}
```

> **Kết quả:** `Sum: 8`

## 🛠️ **2. Cú Pháp Class Method**

Cú pháp để khai báo class method:

```java
class ClassName {
    public static returnType methodName(parameters) {
        // Thân phương thức
    }
}
```

**Ví dụ:**

```java
class Calculator {
    public static double square(double number) {
        return number * number;
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println("Square of 4: " + Calculator.square(4));
    }
}
```

## 🌟 **3. Phân Biệt Class Method Và Instance Method**

| **Class Method (Static Method)**        | **Instance Method**                   |
|-----------------------------------------|----------------------------------------|
| Được khai báo với từ khóa `static`      | Không sử dụng từ khóa `static`         |
| Được gọi qua tên class                  | Được gọi qua đối tượng                 |
| Không thể truy cập trực tiếp vào instance variables | Có thể truy cập vào instance variables |

**Ví dụ:**

```java
class Example {
    int instanceVar = 10;
    
    // Instance Method
    public void displayInstanceVar() {
        System.out.println("Instance Var: " + instanceVar);
    }
    
    // Class Method
    public static void displayStaticMessage() {
        System.out.println("This is a static method.");
    }
}

public class Main {
    public static void main(String[] args) {
        Example.displayStaticMessage(); // Gọi class method
        
        Example obj = new Example();
        obj.displayInstanceVar();       // Gọi instance method
    }
}
```

## 🔍 **4. Các Lưu Ý Khi Sử Dụng Class Method**

1. **Không thể sử dụng `this` hoặc `super` bên trong class method**.
2. **Class method chỉ có thể gọi các biến và phương thức `static` khác**.
3. **Thường được sử dụng cho các tiện ích chung (utility methods)** hoặc các thao tác không phụ thuộc vào đối tượng cụ thể.

## ⚡ **5. Ứng Dụng Của Class Method**

### ✅ **Ví Dụ: Tạo Tiện Ích Chung**

```java
class StringUtils {
    public static boolean isNullOrEmpty(String str) {
        return str == null || str.isEmpty();
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println(StringUtils.isNullOrEmpty(""));    // true
        System.out.println(StringUtils.isNullOrEmpty("Java")); // false
    }
}
```

### 🕹️ **Ví Dụ: Quản Lý Bộ Đếm**

```java
class Counter {
    private static int count = 0;

    public static void increment() {
        count++;
    }

    public static int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        Counter.increment();
        Counter.increment();
        System.out.println("Count: " + Counter.getCount()); // Count: 2
    }
}
```

## 🎯 **6. Tổng Kết**

- **Class Method** được khai báo với từ khóa `static`.
- Có thể gọi trực tiếp từ class mà không cần tạo object.
- Phù hợp với các chức năng không phụ thuộc vào dữ liệu cụ thể của object.
- Không thể truy cập các thành phần không `static` của class.

🚀 **Chúc bạn học Java vui vẻ và thành công!** ✨

---

📝 **Created by ducanhduocdochu**
