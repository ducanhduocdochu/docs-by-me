🎨 Design Pattern: Factory Method

---

📖 1. Overview of Factory Method
- The Factory Method is a Creational Design Pattern that defines an interface for creating an object but lets subclasses decide which class to instantiate. This pattern provides a way to delegate the creation of objects to subclasses.

- 💡 Key Features:
- Delegated Creation: The base class provides the framework, but subclasses handle object instantiation.
- Looser Coupling: Clients only interact with the base class, improving flexibility.
- Extensibility: Easy to add new types of products without modifying existing code.

---

🚀 2. Factory Method in Action
- Here’s a practical example of Factory Method in Java:

🎯 Code Example: Creating Products with Factory Method
```java
// Product Interface
interface Product {
    void use();
}

// Concrete Product A
class ConcreteProductA implements Product {
    public void use() {
        System.out.println("Using Product A");
    }
}

// Concrete Product B
class ConcreteProductB implements Product {
    public void use() {
        System.out.println("Using Product B");
    }
}

// Creator Abstract Class
abstract class Creator {
    public abstract Product createProduct(); // Factory Method

    // Business logic
    public void someOperation() {
        Product product = createProduct();
        product.use();
    }
}

// Concrete Creator A
class ConcreteCreatorA extends Creator {
    public Product createProduct() {
        return new ConcreteProductA();
    }
}

// Concrete Creator B
class ConcreteCreatorB extends Creator {
    public Product createProduct() {
        return new ConcreteProductB();
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Creator creatorA = new ConcreteCreatorA();
        creatorA.someOperation(); // Output: Using Product A

        Creator creatorB = new ConcreteCreatorB();
        creatorB.someOperation(); // Output: Using Product B
    }
}
```
🛠️ How It Works:
- Product interface: Defines the interface for objects that the factory will create.
- ConcreteProductA and ConcreteProductB: Concrete implementations of the Product interface.
- Creator class: Declares the createProduct() method, which subclasses must implement.
- Subclasses: Each subclass implements createProduct() to instantiate a specific product (ConcreteProductA or ConcreteProductB).

---

🌐 3. Factory Method in Real Systems
- A real-world example: Shape Factories in a drawing application.

🖌️ Example: Shape Factory
```java
// Shape Interface
interface Shape {
    void draw();
}

// Concrete Shapes
class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

// Abstract Creator
abstract class ShapeCreator {
    public abstract Shape createShape(); // Factory Method

    // Drawing logic
    public void drawShape() {
        Shape shape = createShape();
        shape.draw();
    }
}

// Concrete Creator
class CircleCreator extends ShapeCreator {
    public Shape createShape() {
        return new Circle();
    }
}

class RectangleCreator extends ShapeCreator {
    public Shape createShape() {
        return new Rectangle();
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        ShapeCreator circleCreator = new CircleCreator();
        circleCreator.drawShape(); // Output: Drawing a Circle

        ShapeCreator rectangleCreator = new RectangleCreator();
        rectangleCreator.drawShape(); // Output: Drawing a Rectangle
    }
}
```
📘 In this example:
Shapes like circles and rectangles are created using a factory method, making it easy to extend the application with new shapes in the future without touching the core logic.

---

⚙️ 4. Pros and Cons of Factory Method
✅ Advantages:
- Decouples creation logic: The client doesn’t need to know the specific class to instantiate.
- Extensible: You can easily add new products (e.g., new shapes, new widgets) without altering existing code.
- Centralized logic: All creation logic is centralized, improving maintainability.
❌ Disadvantages:
- Complexity: It can add unnecessary complexity for small applications.
- Too many classes: You might end up with a lot of extra classes, especially in larger systems.

---

🌍 5. Real-World Applications
- Factory Method is widely used in many real-world systems:
+ GUI frameworks: Used to create different UI elements (buttons, windows, etc.) in a flexible way.
+ Database Connections: Factories create and return the appropriate connection objects depending on the database (MySQL, PostgreSQL, etc.).
+ Document Processing: Factories create various types of documents like PDF, DOCX, and others based on user input.

---

📝 **Created by ducanhduocdochu**
