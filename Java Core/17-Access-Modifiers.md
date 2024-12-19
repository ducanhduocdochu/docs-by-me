# 🔐 Access Modifiers in Java

Access modifiers in Java define the accessibility or scope of classes, methods, and variables. They are essential for encapsulation and ensuring proper access control.

---

## 🌟 Types of Access Modifiers

| Modifier       | Class | Package | Subclass | World |
|----------------|-------|---------|----------|-------|
| `public`       | ✅     | ✅       | ✅        | ✅     |
| `protected`    | ✅     | ✅       | ✅        | ❌     |
| (default)      | ✅     | ✅       | ❌        | ❌     |
| `private`      | ✅     | ❌       | ❌        | ❌     |

---

## 🔑 Access Modifier Details

### 1. **`public`**
- Accessible from **anywhere** in the program.
- Used when the method, variable, or class should be accessible globally.

```java
public class Example {
    public int value = 42;

    public void display() {
        System.out.println("Value: " + value);
    }
}
```

**Usage:**
```java
Example obj = new Example();
obj.display(); // Accessible from anywhere
```

---

### 2. **`protected`**
- Accessible within the **same package** and by **subclasses** (even if in different packages).

```java
class Example {
    protected int value = 42;

    protected void display() {
        System.out.println("Value: " + value);
    }
}
```

**Usage in Subclass:**
```java
class Derived extends Example {
    public void show() {
        display(); // Accessible because of inheritance
    }
}
```

---

### 3. **Default (No Modifier)**
- Also called **package-private**.
- Accessible **only within the same package**.

```java
class Example {
    int value = 42; // Default modifier

    void display() {
        System.out.println("Value: " + value);
    }
}
```

**Usage:**
- Cannot be accessed from a class in another package.

---

### 4. **`private`**
- Accessible **only within the same class**.
- Used to achieve **encapsulation** by hiding implementation details.

```java
class Example {
    private int value = 42;

    private void display() {
        System.out.println("Value: " + value);
    }

    public void accessPrivate() {
        display(); // Accessible within the class
    }
}
```

**Usage:**
```java
Example obj = new Example();
// obj.display(); // Error: display() has private access
obj.accessPrivate(); // Indirect access through public method
```

---

## 📜 Access Modifiers for Classes

| Modifier   | Top-Level Class | Nested Class |
|------------|-----------------|--------------|
| `public`   | ✅               | ✅            |
| (default)  | ✅               | ✅            |
| `protected`| ❌               | ✅            |
| `private`  | ❌               | ✅            |

### 1. **`public` Classes**
- Accessible from **anywhere**.

```java
public class Example {
    public void display() {
        System.out.println("Public class");
    }
}
```

### 2. **Default Classes**
- Accessible only within the **same package**.

```java
class Example {
    void display() {
        System.out.println("Default class");
    }
}
```

---

## 🔥 Use Cases

1. **`public`**: For APIs and widely used utilities.
2. **`protected`**: For extending classes while hiding implementation from non-subclass users.
3. **Default**: For internal package-level functionalities.
4. **`private`**: For hiding sensitive implementation details.

---

## ⚠️ Best Practices
1. Use **`private`** for member variables and provide getters/setters for controlled access.
2. Minimize the use of **`public`** to reduce the risk of unintended usage.
3. Use **`protected`** for methods intended for subclass customization.
4. Avoid package-private unless collaborating with tightly coupled classes in the same package.

---

## 🌀 Combining with Other Modifiers
### Access Modifiers + Non-Access Modifiers
- Can combine `public`, `protected`, `private` with:
  - **`final`**: Prevent overriding or inheritance.
  - **`static`**: Belong to the class rather than an instance.
  - **`abstract`**: For abstract methods or classes.

```java
public final class Example {
    private static int count = 0;

    public static void displayCount() {
        System.out.println("Count: " + count);
    }
}
```

---

## 🎯 Summary Table
| Modifier       | Scope                                          | Use Case                          |
|----------------|-----------------------------------------------|------------------------------------|
| `public`       | Everywhere                                    | Global access                     |
| `protected`    | Same package + subclasses                    | Controlled inheritance            |
| Default        | Same package                                 | Internal collaboration            |
| `private`      | Within the same class                        | Encapsulation and data hiding     |

---

Happy Coding! 😊

---

📝 **Created by ducanhduocdochu**
