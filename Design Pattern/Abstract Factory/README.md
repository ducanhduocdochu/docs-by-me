
# 🎨 Design Pattern: Abstract Factory

---

## 📖 1. Overview of Abstract Factory
The **Abstract Factory** is a **Creational Design Pattern** that provides an interface for creating families of related or dependent objects without specifying their concrete classes. Unlike Factory Method, which focuses on a single product, Abstract Factory deals with the creation of multiple related objects, typically from different classes.

### 💡 Key Features:
- **Multiple Products:** This pattern allows creating a group of objects (e.g., multiple product families) that are designed to work together.
- **High Flexibility:** The Abstract Factory provides a way to easily switch between different families of products.
- **Separation of Concerns:** The pattern keeps the client code independent of the actual product creation and specific concrete classes.

---

## 🚀 2. Abstract Factory in Action
Here’s a practical example of how the Abstract Factory Pattern works in Java:

### 🎯 Code Example: Creating Families of Products with Abstract Factory
```java
// Product Family 1
interface Button {
    void click();
}

class WinButton implements Button {
    public void click() {
        System.out.println("Windows Button Clicked");
    }
}

class MacButton implements Button {
    public void click() {
        System.out.println("Mac Button Clicked");
    }
}

// Product Family 2
interface Checkbox {
    void check();
}

class WinCheckbox implements Checkbox {
    public void check() {
        System.out.println("Windows Checkbox Checked");
    }
}

class MacCheckbox implements Checkbox {
    public void check() {
        System.out.println("Mac Checkbox Checked");
    }
}

// Abstract Factory Interface
interface GUIFactory {
    Button createButton();
    Checkbox createCheckbox();
}

// Concrete Factory for Windows
class WinFactory implements GUIFactory {
    public Button createButton() {
        return new WinButton();
    }

    public Checkbox createCheckbox() {
        return new WinCheckbox();
    }
}

// Concrete Factory for Mac
class MacFactory implements GUIFactory {
    public Button createButton() {
        return new MacButton();
    }

    public Checkbox createCheckbox() {
        return new MacCheckbox();
    }
}

// Client code
public class Application {
    private Button button;
    private Checkbox checkbox;

    public Application(GUIFactory factory) {
        button = factory.createButton();
        checkbox = factory.createCheckbox();
    }

    public void run() {
        button.click();
        checkbox.check();
    }

    public static void main(String[] args) {
        // Client chooses the factory type based on some configuration or platform
        GUIFactory factory = new WinFactory(); // Can switch to MacFactory for Mac OS
        Application app = new Application(factory);
        app.run();  // Output: Windows Button Clicked 
 Windows Checkbox Checked
    }
}
```

---

## 🌐 3. Abstract Factory vs Factory Method
While **Factory Method** focuses on creating a single product, the **Abstract Factory** works on creating families of related products.

### Example Scenario:
In a graphical user interface (GUI) system, different platforms (Windows, Mac, Linux) have different implementations of buttons, checkboxes, and other widgets. With **Abstract Factory**, the GUI system can easily switch between platforms by switching the factories, without changing the core application code.

---

## ⚙️ 4. Pros and Cons of Abstract Factory
### ✅ Advantages:
- **Consistency:** Ensures that related products are used together in the client code (e.g., MacButton with MacCheckbox).
- **Scalability:** Adding new product families is easy by implementing a new factory.
- **Encapsulation:** Creation logic is hidden from the client, leading to better maintainability and flexibility.

### ❌ Disadvantages:
- **Complexity:** It increases the number of classes and interfaces, which might be overkill for small applications.
- **Difficulty in Extensions:** While it’s easy to add new families, extending individual product types may be harder, as this might affect all factories.

---

## 🌍 5. Real-World Applications
- **UI Frameworks:** Used to handle different platforms by creating UI components that are platform-specific (e.g., Windows, Mac).
- **Database Connection Kits:** A different factory can be used for connecting to various databases (MySQL, PostgreSQL, etc.) while ensuring that the correct driver and connection objects are used together.
- **Cross-Platform Tools:** In cross-platform development, the Abstract Factory pattern is often employed to generate families of platform-specific objects.

---

📝 **Created by ducanhduocdochu**
