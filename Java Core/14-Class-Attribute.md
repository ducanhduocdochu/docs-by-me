# 🌟 **Class Attributes trong Java** 📚

Trong lập trình Java, **Class Attributes** (còn gọi là **thuộc tính của lớp**) là các biến được khai báo bên trong một class và được sử dụng để lưu trữ trạng thái của đối tượng. Chúng có thể được chia thành hai loại chính: **Instance Attributes** (thuộc tính thể hiện) và **Static Attributes** (thuộc tính tĩnh).

## 📌 **1. Instance Attributes (Thuộc Tính Thể Hiện)**

### 🔹 **Định Nghĩa**

**Instance Attributes** là các biến được khai báo trong class nhưng nằm ngoài các phương thức. Mỗi object (instance) của class sẽ có một bản sao riêng của các thuộc tính này.

### 🛠️ **Cú Pháp**

```java
class ClassName {
    // Instance Attribute
    dataType attributeName;
}
```

### 📝 **Ví Dụ**

```java
public class Car {
    // Instance Attributes
    String model;
    int year;

    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    public void displayInfo() {
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }

    public static void main(String[] args) {
        Car car1 = new Car("Toyota", 2021);
        Car car2 = new Car("Honda", 2022);

        car1.displayInfo();
        car2.displayInfo();
    }
}
```

### 📊 **Giải Thích**
- **`model`** và **`year`** là **instance attributes**.
- Mỗi object (`car1` và `car2`) có bản sao riêng của các thuộc tính này.

> **Kết quả chạy chương trình:**
```
Model: Toyota
Year: 2021
Model: Honda
Year: 2022
```

---

## 🔹 **2. Static Attributes (Thuộc Tính Tĩnh)**

### 🌐 **Định Nghĩa**

**Static Attributes** là các biến được khai báo với từ khóa `static`. Chúng thuộc về class thay vì các object cụ thể. Tất cả các object đều chia sẻ cùng một bản sao của static attribute.

### 🛠️ **Cú Pháp**

```java
class ClassName {
    // Static Attribute
    static dataType attributeName;
}
```

### 📝 **Ví Dụ**

```java
public class Car {
    // Static Attribute
    static int numberOfCars = 0;

    String model;

    public Car(String model) {
        this.model = model;
        numberOfCars++;
    }

    public void displayInfo() {
        System.out.println("Model: " + model);
        System.out.println("Total Cars: " + numberOfCars);
    }

    public static void main(String[] args) {
        Car car1 = new Car("Toyota");
        car1.displayInfo();

        Car car2 = new Car("Honda");
        car2.displayInfo();

        System.out.println("Final Total Cars: " + Car.numberOfCars);
    }
}
```

### 📊 **Giải Thích**
- **`numberOfCars`** là một static attribute.
- Mỗi khi một object `Car` được tạo, `numberOfCars` sẽ tăng thêm 1.
- Tất cả các object chia sẻ cùng một giá trị của `numberOfCars`.

> **Kết quả chạy chương trình:**
```
Model: Toyota
Total Cars: 1
Model: Honda
Total Cars: 2
Final Total Cars: 2
```

---

## 🔎 **So Sánh Instance Attribute và Static Attribute**

| **Đặc Điểm**                  | **Instance Attribute**                  | **Static Attribute**                |
|-------------------------------|------------------------------------------|-------------------------------------|
| **Phạm vi**                  | Thuộc về từng object                    | Thuộc về class                      |
| **Bản sao**                  | Mỗi object có bản sao riêng             | Tất cả object chia sẻ một bản sao   |
| **Khai báo**                 | Không có từ khóa `static`               | Có từ khóa `static`                 |
| **Truy cập**                 | `objectName.attributeName`              | `ClassName.attributeName`           |

---

## 📝 **3. Quy Tắc Đặt Tên Class Attribute**

1. **Tên phải bắt đầu bằng chữ cái** (không phải số hoặc ký tự đặc biệt).
2. **Sử dụng camelCase** cho instance attributes và static attributes (ví dụ: `numberOfWheels`).
3. **Tránh sử dụng từ khóa Java** làm tên biến (ví dụ: `int`, `class`).
4. **Tên phải có ý nghĩa và mô tả đúng chức năng** của attribute.

---

## 🛠️ **4. Truy Cập và Thay Đổi Class Attribute**

### 🧩 **Truy Cập Instance Attribute**

```java
Car myCar = new Car("BMW");
System.out.println(myCar.model);
```

### 🌐 **Truy Cập Static Attribute**

```java
System.out.println(Car.numberOfCars);
```

### 📝 **Thay Đổi Static Attribute**

```java
Car.numberOfCars = 5;
```

---

## 🔐 **5. Đóng Gói (Encapsulation) Class Attribute**

Để bảo vệ class attribute, bạn nên sử dụng **private** và truy cập thông qua các **getter** và **setter**.

### 📝 **Ví Dụ**

```java
public class Person {
    private String name;

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("Alice");
        System.out.println(person.getName());
    }
}
```

---

## 🌟 **Kết Luận**

- **Instance Attributes** lưu trữ trạng thái của từng object riêng biệt.
- **Static Attributes** lưu trữ dữ liệu chung cho tất cả các object.
- Sử dụng đúng loại attribute giúp bạn tối ưu hóa chương trình và giữ mã nguồn dễ hiểu.

🚀 **Chúc bạn học Java hiệu quả!** 🌟

---

📝 **Created by ducanhduocdochu**
