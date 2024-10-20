
# 🎨 Design Pattern: Proxy

---

## 📖 1. Overview of Proxy
The Proxy Design Pattern is a **Structural Design Pattern** that provides a surrogate or placeholder for another object to control access to it. The proxy object represents the real object and manages access, acting as a middle layer between the client and the target object.

- 💡 **Key Features**:
  - **Control Access**: Proxies manage and control access to the real object.
  - **Lazy Initialization**: They can instantiate expensive objects only when necessary.
  - **Security and Caching**: Proxies can add additional security checks or cache results for better performance.

---

## 🚀 2. Proxy Pattern in Action
Here's a practical example of the Proxy Pattern in Java:

### 🎯 Code Example: Access Control with Proxy
```java
// Subject Interface
interface Subject {
    void request();
}

// RealSubject: The object the Proxy represents
class RealSubject implements Subject {
    public void request() {
        System.out.println("RealSubject: Handling request.");
    }
}

// Proxy: Controls access to the RealSubject
class Proxy implements Subject {
    private RealSubject realSubject;

    public void request() {
        if (realSubject == null) {
            realSubject = new RealSubject(); // Lazy initialization
        }
        System.out.println("Proxy: Controlling access to RealSubject.");
        realSubject.request();
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Subject proxy = new Proxy();
        proxy.request();  // Output: Proxy: Controlling access to RealSubject. RealSubject: Handling request.
    }
}
```

### 🛠️ How It Works:
- **Subject interface**: Defines the common interface for both the proxy and real objects.
- **RealSubject**: The actual object that the proxy represents and controls access to.
- **Proxy**: Manages access to the RealSubject, adding additional logic like lazy initialization or access control.

---

## 🌐 3. Proxy Pattern in Real Systems
A real-world example: Database connections using proxies to manage pooling and lazy initialization.

### 🖥️ Example: Database Proxy
```java
// Database Connection Interface
interface Database {
    void connect();
}

// Real Database
class RealDatabase implements Database {
    public void connect() {
        System.out.println("Connecting to the real database...");
    }
}

// Proxy for the Database
class DatabaseProxy implements Database {
    private RealDatabase realDatabase;

    public void connect() {
        if (realDatabase == null) {
            realDatabase = new RealDatabase(); // Lazy initialization
        }
        System.out.println("DatabaseProxy: Checking access and connecting...");
        realDatabase.connect();
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Database dbProxy = new DatabaseProxy();
        dbProxy.connect(); // Output: DatabaseProxy: Checking access and connecting... Connecting to the real database...
    }
}
```

📘 In this example:
- The **DatabaseProxy** manages the connection process, ensuring that the real database object is only created when needed, adding access control logic.

---

## ⚙️ 4. Pros and Cons of Proxy

### ✅ **Advantages**:
- **Controlled access**: The proxy can manage access to the real object, adding security or performance enhancements like caching.
- **Lazy initialization**: Expensive objects are only created when they're needed, saving system resources.
- **Additional functionality**: Proxies can add new functionality like logging, security checks, or data compression without modifying the real object.

### ❌ **Disadvantages**:
- **Overhead**: Adding a proxy can introduce unnecessary complexity and performance overhead.
- **Code maintenance**: More classes are introduced, making the system potentially harder to maintain.

---

## 🌍 5. Real-World Applications
The Proxy Pattern is widely used in various systems:
- **Virtual Proxies**: To create expensive objects only when they are needed, such as large images in a graphic application.
- **Remote Proxies**: Used in distributed systems to represent objects in different locations.
- **Protection Proxies**: To control access to sensitive resources based on access rights.

---

📝 **Created by ducanhduocdochu**
