# ✨ **Tất Tần Tật Về Class Và Object Trong Java** 📚

## 📚 **1. Giới Thiệu Về Class Và Object**

Trong Java, **class** và **object** là hai khái niệm cốt lõi của lập trình hướng đối tượng (OOP - Object-Oriented Programming).

- **Class** là bản thiết kế (blueprint) cho các đối tượng. Class xác định các thuộc tính (property) và hành vi (method) mà đối tượng thuộc lớp đó sẽ có.
- **Object** là thực thể (instance) của class. Mỗi object được tạo từ class và có thể chứa dữ liệu riêng.

**Ví dụ đơn giản:**
```java
class Animal {
    String name;
    int age;

    void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Animal cat = new Animal();
        cat.name = "Milo";
        cat.age = 3;
        cat.displayInfo();
    }
}
```

> Kết quả:
```
Name: Milo
Age: 3
```

Trong ví dụ trên:
- `Animal` là class với hai thuộc tính `name` và `age`, cùng với phương thức `displayInfo`.
- `cat` là một object được tạo từ class `Animal`.

## 🌟 **2. Class Trong Java**

### 🔧 **Các Thành Phần Của Class**

Một class trong Java bao gồm:

1. **Thuộc tính (Fields/Properties)**: Là các biến lưu trữ trạng thái hoặc thông tin của đối tượng. Mỗi thuộc tính có thể có kiểu dữ liệu và tên gọi riêng.

2. **Phương thức (Methods)**: Là các hàm định nghĩa hành động hoặc thao tác mà đối tượng có thể thực hiện. Phương thức thường làm việc với dữ liệu được lưu trữ trong các thuộc tính của class.

3. **Constructor**: Là một phương thức đặc biệt được gọi khi một object được tạo ra. Constructor thường được dùng để khởi tạo các giá trị ban đầu cho object.

**Ví dụ:**

```java
class Car {
    // Thuộc tính
    String model;
    int year;

    // Constructor
    Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // Phương thức
    void displayCarInfo() {
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}
```

### 🛠️ **Cú Pháp Định Nghĩa Class**

Cú pháp chung để định nghĩa một class trong Java:

```java
class ClassName {
    // Thuộc tính
    type variableName;
    
    // Constructor
    ClassName(parameters) {
        // Khởi tạo thuộc tính
    }
    
    // Phương thức
    returnType methodName(parameters) {
        // Thân phương thức
    }
}
```

### 👑 **Tính Chất Của Class Trong Java**

1. **Tính đóng gói (Encapsulation)**: Bảo vệ dữ liệu bằng cách che giấu thông tin và chỉ cho phép truy cập dữ liệu qua các phương thức công khai.

2. **Tính kế thừa (Inheritance)**: Cho phép một class sử dụng lại thuộc tính và phương thức từ class khác.

3. **Tính đa hình (Polymorphism)**: Cho phép các phương thức có cùng tên nhưng hành vi khác nhau.

4. **Tính trừu tượng (Abstraction)**: Che giấu chi tiết thực thi và chỉ hiển thị những gì cần thiết.

## 👀 **3. Object Trong Java**

### 💰 **Tạo Object Từ Class**

📅 Cách tạo object trong Java:
```java
ClassName objectName = new ClassName(arguments);
```

**Ví dụ:**
```java
Car myCar = new Car("Toyota", 2021);
myCar.displayCarInfo();
```

### 📊 **Sử Dụng Object**

1. **Gán giá trị cho thuộc tính:**

    ```java
    myCar.model = "Honda";
    myCar.year = 2022;
    ```

2. **Gọi phương thức:**

    ```java
    myCar.displayCarInfo();
    ```

## 🔎 **4. Sự Khác Biệt Giữa Class Và Object**

| **Class**            | **Object**                         |
|-----------------------|------------------------------------|
| Bản thiết kế          | Thực thể cụ thể                   |
| Được khai báo một lần | Có thể tạo nhiều object từ class  |
| Không chiếm bộ nhớ   | Chiếm bộ nhớ khi được tạo         |

## 💡 **5. Ví Dụ Nâng Cao Về Class Và Object**

### 🚗 **Ví Dụ Với Nhiều Phương Thức Và Thuộc Tính**

```java
class Person {
    String name;
    int age;

    // Constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức để chào hỏi
    void greet() {
        System.out.println("Hello, my name is " + name);
    }

    // Phương thức để hiển thị tuổi
    void displayAge() {
        System.out.println("I am " + age + " years old.");
    }
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person("Alice", 25);
        person1.greet();
        person1.displayAge();
    }
}
```

> **Kết quả:**
```
Hello, my name is Alice
I am 25 years old.
```

### 🧠 **Giải Thích**
- **Class `Person`** có hai thuộc tính `name` và `age`.
- **Constructor** được dùng để khởi tạo giá trị cho `name` và `age` khi tạo object.
- Hai phương thức `greet()` và `displayAge()` thực hiện các hành động liên quan đến object.

## 📝 **6. Tổng Kết**

- **Class** là bản thiết kế mô tả đối tượng.
- **Object** là thực thể được tạo từ class.
- Mỗi class có thể có các **thuộc tính**, **phương thức**, và **constructor** để mô tả và khởi tạo object.
- Hiểu rõ các tính chất của class như **đóng gói**, **kế thừa**, **đa hình**, và **trừu tượng** giúp bạn sử dụng Java hiệu quả hơn trong lập trình hướng đối tượng.

✨ **Chúc bạn học Java vui vẻ!** 🚀

---

📝 **Created by ducanhduocdochu**
