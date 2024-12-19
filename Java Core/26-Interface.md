# Tất Tần Tật về Interface trong Java

## 1. Interface là gì?
**Interface** là một bản thiết kế (blueprint) trong Java, được sử dụng để định nghĩa các phương thức mà một lớp phải triển khai.

- **Cú pháp:**
  ```java
  interface InterfaceName {
      // Các phương thức trừu tượng
  }
  ```
- **Đặc điểm:**
  - Tất cả các phương thức mặc định là **abstract** và **public** (trừ khi được định nghĩa khác).
  - Các biến trong interface luôn là **public static final**.

---

## 2. Đặc điểm chính của Interface
- Không thể chứa **constructor**.
- Một lớp có thể triển khai nhiều interface.
- Từ Java 8:
  - **Phương thức mặc định (default method):** Phương thức cụ thể trong interface.
  - **Phương thức tĩnh (static method):** Phương thức tĩnh có thể được gọi mà không cần một instance.
- Từ Java 9:
  - **Phương thức private:** Hỗ trợ định nghĩa phương thức dùng trong nội bộ interface.

---

## 3. Cách sử dụng Interface

### Ví dụ cơ bản
```java
interface Animal {
    void sound(); // Phương thức trừu tượng
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Woof Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
    }
}
```
**Kết quả:**
```
Woof Woof
```

---

### Triển khai nhiều Interface
```java
interface Animal {
    void sound();
}

interface Pet {
    void play();
}

class Dog implements Animal, Pet {
    @Override
    public void sound() {
        System.out.println("Woof Woof");
    }

    @Override
    public void play() {
        System.out.println("Playing fetch");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();
        dog.play();
    }
}
```
**Kết quả:**
```
Woof Woof
Playing fetch
```

---

### Phương thức mặc định và tĩnh (Java 8+)
```java
interface Vehicle {
    void start();

    default void stop() {
        System.out.println("Vehicle is stopping...");
    }

    static void maintenance() {
        System.out.println("Performing maintenance");
    }
}

class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("Car is starting...");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start();
        car.stop();

        Vehicle.maintenance(); // Gọi phương thức tĩnh
    }
}
```
**Kết quả:**
```
Car is starting...
Vehicle is stopping...
Performing maintenance
```

---

## 4. Interface vs Abstract Class

| **Thuộc tính**               | **Interface**                            | **Abstract Class**                     |
|------------------------------|------------------------------------------|---------------------------------------|
| **Phương thức cụ thể**        | Hỗ trợ từ Java 8 (default, static)       | Có thể có                             |
| **Phương thức trừu tượng**    | Tất cả đều mặc định là abstract          | Có thể có                             |
| **Constructor**              | Không                                    | Có                                    |
| **Biến**                     | Chỉ chứa hằng số (public static final)   | Có thể chứa biến instance             |
| **Đa kế thừa**               | Một lớp có thể triển khai nhiều interface| Một lớp chỉ kế thừa một abstract class|

---

## 5. Ứng dụng thực tế của Interface
1. **Định nghĩa hành vi chung:**
   - Ví dụ: Tất cả các lớp kế thừa `Comparable` phải triển khai phương thức `compareTo()`.
   ```java
   interface Comparable<T> {
       int compareTo(T o);
   }
   ```
2. **Tính đa hình:**
   - Cho phép các lớp khác nhau thực hiện các hành vi theo cách riêng.
3. **Kết nối giữa các module:**
   - Ví dụ: `Runnable` interface được sử dụng để thực hiện đa luồng trong Java.
   ```java
   class Task implements Runnable {
       @Override
       public void run() {
           System.out.println("Task is running...");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Thread thread = new Thread(new Task());
           thread.start();
       }
   }
   ```

---

## 6. Khi nào nên sử dụng Interface?
1. Khi cần tính đa kế thừa (vì một lớp có thể triển khai nhiều interface).
2. Khi cần định nghĩa một tập hợp các phương thức mà nhiều lớp phải tuân theo.
3. Khi cần tạo một API linh hoạt và có thể mở rộng.

---

## 7. Kết luận
- **Interface** là công cụ mạnh mẽ để xây dựng hệ thống với tính linh hoạt và tái sử dụng cao.
- Hiểu rõ cách sử dụng và đặc điểm của interface sẽ giúp bạn thiết kế ứng dụng tốt hơn.

👉 **Mẹo:** Sử dụng Interface khi cần định nghĩa các hành vi chung và hỗ trợ đa kế thừa. 🚀

---

📝 **Created by ducanhduocdochu**
