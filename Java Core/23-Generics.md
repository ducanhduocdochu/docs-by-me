# Tất Tần Tật về Generics trong Java

## 📋 Generics là gì?
**Generics** là một tính năng trong Java, được giới thiệu từ Java 5, giúp chúng ta định nghĩa các lớp, phương thức hoặc giao diện có thể hoạt động trên nhiều kiểu dữ liệu khác nhau mà vẫn đảm bảo tính an toàn kiểu (type safety) tại thời điểm biên dịch.

- **Cú pháp cơ bản:**
  ```java
  class ClassName<T> {
      // T là một kiểu dữ liệu generic
  }
  ```
- `T`, `E`, `K`, `V` là các ký hiệu phổ biến:
  - `T`: Type (Kiểu dữ liệu bất kỳ)
  - `E`: Element (Phần tử, dùng trong các collection)
  - `K`, `V`: Key và Value (Trong Map)

---

## 💡 Lợi ích của Generics

### 1. **An toàn kiểu (Type Safety)**
- Generics giúp phát hiện lỗi kiểu dữ liệu tại thời điểm biên dịch.
  ```java
  List<String> list = new ArrayList<>();
  list.add("Hello");
  list.add(123); // Lỗi biên dịch
  ```

### 2. **Loại bỏ ép kiểu (Type Casting)**
- Không cần ép kiểu thủ công, giúp mã nguồn rõ ràng hơn.
  ```java
  // Không dùng Generics
  List list = new ArrayList();
  list.add("Hello");
  String str = (String) list.get(0); // Ép kiểu thủ công

  // Dùng Generics
  List<String> list = new ArrayList<>();
  list.add("Hello");
  String str = list.get(0); // Không cần ép kiểu
  ```

### 3. **Tái sử dụng mã nguồn**
- Giúp viết mã nguồn có tính tổng quát và tái sử dụng cao.
  ```java
  class Box<T> {
      private T value;

      public void setValue(T value) {
          this.value = value;
      }

      public T getValue() {
          return value;
      }
  }

  Box<Integer> intBox = new Box<>();
  intBox.setValue(123);

  Box<String> strBox = new Box<>();
  strBox.setValue("Hello");
  ```

---

## 📚 Các loại Generics trong Java

### 1. **Generic Class**
Khai báo một lớp có Generics.
```java
class GenericClass<T> {
    private T data;

    public T getData() {
        return data;
    }

    public void setData(T data) {
        this.data = data;
    }
}

public class Main {
    public static void main(String[] args) {
        GenericClass<String> obj = new GenericClass<>();
        obj.setData("Hello");
        System.out.println(obj.getData());
    }
}
```

### 2. **Generic Method**
Định nghĩa một phương thức có thể hoạt động với nhiều kiểu dữ liệu.
```java
public class GenericMethod {
    public static <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.println(element);
        }
    }

    public static void main(String[] args) {
        Integer[] intArray = {1, 2, 3};
        String[] strArray = {"A", "B", "C"};

        printArray(intArray);
        printArray(strArray);
    }
}
```

### 3. **Generic Interface**
Khai báo một giao diện có Generics.
```java
interface GenericInterface<T> {
    void display(T data);
}

class GenericClass<T> implements GenericInterface<T> {
    @Override
    public void display(T data) {
        System.out.println("Data: " + data);
    }
}

public class Main {
    public static void main(String[] args) {
        GenericInterface<String> obj = new GenericClass<>();
        obj.display("Hello Generics");
    }
}
```

### 4. **Bounded Type Parameters**
Giới hạn kiểu dữ liệu có thể được sử dụng trong Generics.
```java
class GenericClass<T extends Number> {
    private T data;

    public T getData() {
        return data;
    }

    public void setData(T data) {
        this.data = data;
    }
}

public class Main {
    public static void main(String[] args) {
        GenericClass<Integer> obj = new GenericClass<>();
        obj.setData(123);

        // GenericClass<String> obj2 = new GenericClass<>(); // Lỗi biên dịch
    }
}
```

---

## 🔄 Wildcards trong Generics
Wildcards (`?`) được sử dụng khi bạn không biết hoặc không muốn chỉ định kiểu dữ liệu cụ thể.

### 1. **Unbounded Wildcards**
```java
public void printList(List<?> list) {
    for (Object obj : list) {
        System.out.println(obj);
    }
}
```

### 2. **Bounded Wildcards**
- **Upper Bound:**
  ```java
  public void printNumbers(List<? extends Number> list) {
      for (Number num : list) {
          System.out.println(num);
      }
  }
  ```

- **Lower Bound:**
  ```java
  public void addNumbers(List<? super Integer> list) {
      list.add(123);
  }
  ```

---

## 🚀 Tổng Kết
- Generics giúp mã nguồn Java an toàn, dễ bảo trì và tái sử dụng hơn.
- Hiểu rõ các loại Generics (class, method, interface) và cách sử dụng Wildcards là chìa khóa để làm việc hiệu quả với Generics.

✨ **Mẹo:** Sử dụng Generics đúng cách để viết mã nguồn mạnh mẽ và dễ mở rộng! 🚀

---

📝 **Created by ducanhduocdochu**
