# 🎨 Design Pattern: Decorator

---

## 📖 1. Overview of Decorator
The **Decorator Design Pattern** is a **Structural Design Pattern** that allows behavior to be added to individual objects, dynamically, without affecting the behavior of other objects from the same class. It provides a flexible alternative to subclassing for extending functionality.

- 💡 **Key Features**:
  - **Dynamic Behavior Addition**: Enables adding responsibilities to objects at runtime.
  - **Flexible and Reusable**: Promotes code reuse by allowing functionalities to be mixed and matched.
  - **Transparent to Clients**: Clients interact with decorated objects in the same way as with the original objects.

---

## 🚀 2. Decorator Pattern in Action
Here's a practical example of the Decorator Pattern in Java:

### 🎯 Code Example: Enhancing Beverage Objects with Decorators
```java
// Component Interface
interface Beverage {
    String getDescription();
    double cost();
}

// Concrete Component
class Espresso implements Beverage {
    public String getDescription() {
        return "Espresso";
    }

    public double cost() {
        return 1.99;
    }
}

// Another Concrete Component
class HouseBlend implements Beverage {
    public String getDescription() {
        return "House Blend Coffee";
    }

    public double cost() {
        return 0.89;
    }
}

// Decorator Abstract Class
abstract class CondimentDecorator implements Beverage {
    protected Beverage beverage;

    public CondimentDecorator(Beverage beverage) {
        this.beverage = beverage;
    }

    public abstract String getDescription();
}

// Concrete Decorators
class Mocha extends CondimentDecorator {
    public Mocha(Beverage beverage) {
        super(beverage);
    }

    public String getDescription() {
        return beverage.getDescription() + ", Mocha";
    }

    public double cost() {
        return beverage.cost() + 0.20;
    }
}

class Soy extends CondimentDecorator {
    public Soy(Beverage beverage) {
        super(beverage);
    }

    public String getDescription() {
        return beverage.getDescription() + ", Soy";
    }

    public double cost() {
        return beverage.cost() + 0.15;
    }
}

// Client code
public class CoffeeShop {
    public static void main(String[] args) {
        Beverage beverage = new Espresso();
        beverage = new Mocha(beverage);
        beverage = new Soy(beverage);

        System.out.println(beverage.getDescription() + " $" + beverage.cost());
        // Output: Espresso, Mocha, Soy $2.34
    }
}
```

### 🛠️ How It Works:
- **Component**: The `Beverage` interface defines the operations that can be dynamically added to.
- **Concrete Component**: Classes like `Espresso` and `HouseBlend` implement the `Beverage` interface.
- **Decorator**: The abstract `CondimentDecorator` class implements the `Beverage` interface and contains a reference to a `Beverage` object.
- **Concrete Decorators**: Classes like `Mocha` and `Soy` extend the `CondimentDecorator` and add their own behavior.

---

## 🌐 3. Decorator Pattern in Real Systems
A real-world example of the Decorator Pattern is in **Java I/O Streams**, where various decorators add functionalities like buffering, data type conversion, or compression to the basic input/output streams.

### 🖥️ Example: Enhancing Text Processing with Decorators
```java
// Component Interface
interface Text {
    String getContent();
}

// Concrete Component
class PlainText implements Text {
    private String content;

    public PlainText(String content) {
        this.content = content;
    }

    public String getContent() {
        return content;
    }
}

// Decorator Abstract Class
abstract class TextDecorator implements Text {
    protected Text text;

    public TextDecorator(Text text) {
        this.text = text;
    }

    public abstract String getContent();
}

// Concrete Decorators
class BoldDecorator extends TextDecorator {
    public BoldDecorator(Text text) {
        super(text);
    }

    public String getContent() {
        return "<b>" + text.getContent() + "</b>";
    }
}

class ItalicDecorator extends TextDecorator {
    public ItalicDecorator(Text text) {
        super(text);
    }

    public String getContent() {
        return "<i>" + text.getContent() + "</i>";
    }
}

// Client code
public class TextEditor {
    public static void main(String[] args) {
        Text text = new PlainText("Hello, World!");
        Text boldText = new BoldDecorator(text);
        Text boldItalicText = new ItalicDecorator(boldText);

        System.out.println(boldItalicText.getContent());
        // Output: <i><b>Hello, World!</b></i>
    }
}
```

📘 In this example:
- **Text** is the component interface.
- **PlainText** is the concrete component.
- **TextDecorator** is the abstract decorator.
- **BoldDecorator** and **ItalicDecorator** are concrete decorators that add HTML tags to the text.

---

## ⚙️ 4. Pros and Cons of Decorator

### ✅ **Advantages**:
- **Single Responsibility Principle**: Divides functionality between classes with unique areas of concern.
- **Open/Closed Principle**: Classes are open for extension but closed for modification.
- **Flexible and Reusable**: Easily add new functionalities by creating new decorators without altering existing code.

### ❌ **Disadvantages**:
- **Complexity**: Can lead to a large number of small classes, making the system harder to understand.
- **Order Dependency**: The order in which decorators are applied can affect the final behavior, potentially leading to unexpected results.

---

## 🌍 5. Real-World Applications
The Decorator Pattern is widely used in systems such as:
- **Graphical User Interfaces (GUI)**: Enhancing window components with scrollbars, borders, or other decorations.
- **Java I/O Streams**: Adding functionalities like buffering, data conversion, and compression to streams.
- **Logging Systems**: Dynamically adding logging, authentication, or encryption features to existing services.

---

📝 **Created by ducanhduocdochu**
