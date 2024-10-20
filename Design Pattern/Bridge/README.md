
# 🎨 Design Pattern: Bridge

---

## 📖 1. Overview of Bridge
The Bridge Design Pattern is a **Structural Design Pattern** that separates an abstraction from its implementation, allowing them to vary independently. It provides a way to decouple the interface from the implementation, making it easier to modify or extend both sides without affecting each other.

- 💡 **Key Features**:
  - **Decoupling Abstraction and Implementation**: Allows independent development and extension of both the abstraction and its implementation.
  - **Improved Flexibility**: Provides flexibility to swap out different implementations without changing the abstraction.
  - **Reusability**: Encourages code reusability by allowing the use of different implementations for the same abstraction.

---

## 🚀 2. Bridge Pattern in Action
Here's a practical example of the Bridge Pattern in Java:

### 🎯 Code Example: Decoupling Abstraction and Implementation with Bridge
```java
// Abstraction
abstract class Device {
    protected Remote remote;

    public Device(Remote remote) {
        this.remote = remote;
    }

    abstract void operate();
}

// Refined Abstraction
class TV extends Device {
    public TV(Remote remote) {
        super(remote);
    }

    public void operate() {
        System.out.println("Operating TV with remote.");
        remote.power();
    }
}

// Another Refined Abstraction
class Radio extends Device {
    public Radio(Remote remote) {
        super(remote);
    }

    public void operate() {
        System.out.println("Operating Radio with remote.");
        remote.power();
    }
}

// Implementor Interface
interface Remote {
    void power();
}

// Concrete Implementor
class BasicRemote implements Remote {
    public void power() {
        System.out.println("Turning device on/off.");
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Device tv = new TV(new BasicRemote());
        tv.operate();  // Output: Operating TV with remote. Turning device on/off.

        Device radio = new Radio(new BasicRemote());
        radio.operate();  // Output: Operating Radio with remote. Turning device on/off.
    }
}
```

### 🛠️ How It Works:
- **Abstraction**: The abstract class (Device) represents the high-level concept.
- **Refined Abstraction**: Concrete subclasses like TV and Radio implement the abstract class.
- **Implementor**: The Remote interface defines the implementation side.
- **Concrete Implementor**: BasicRemote provides the actual implementation for the Remote interface.

---

## 🌐 3. Bridge Pattern in Real Systems
A real-world example: Controlling different types of devices (TV, Radio, etc.) using various remotes, where both device types and remotes can vary independently.

### 🖥️ Example: Shape and Color Bridge
```java
// Abstraction
abstract class Shape {
    protected Color color;

    public Shape(Color color) {
        this.color = color;
    }

    abstract void draw();
}

// Refined Abstraction
class Circle extends Shape {
    public Circle(Color color) {
        super(color);
    }

    public void draw() {
        System.out.print("Drawing Circle in ");
        color.fillColor();
    }
}

// Implementor Interface
interface Color {
    void fillColor();
}

// Concrete Implementor
class RedColor implements Color {
    public void fillColor() {
        System.out.println("red.");
    }
}

// Another Concrete Implementor
class BlueColor implements Color {
    public void fillColor() {
        System.out.println("blue.");
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Shape redCircle = new Circle(new RedColor());
        redCircle.draw();  // Output: Drawing Circle in red.

        Shape blueCircle = new Circle(new BlueColor());
        blueCircle.draw();  // Output: Drawing Circle in blue.
    }
}
```

📘 In this example:
- **Shape** is the abstraction, and **Color** is the implementation. The Bridge Pattern allows us to use different colors for different shapes without modifying their respective classes.

---

## ⚙️ 4. Pros and Cons of Bridge

### ✅ **Advantages**:
- **Decoupling**: Separates abstraction and implementation, allowing them to evolve independently.
- **Scalability**: Makes it easy to extend both abstractions and implementations without affecting each other.
- **Flexibility**: Enables switching between different implementations dynamically.

### ❌ **Disadvantages**:
- **Increased complexity**: The pattern introduces more layers of abstraction, which can make the code harder to follow and maintain in small systems.

---

## 🌍 5. Real-World Applications
The Bridge Pattern is widely used in various systems:
- **GUI toolkits**: Separating the platform-dependent implementation of UI components from the abstraction layer.
- **Graphics rendering**: Using different rendering techniques or APIs for rendering shapes or images.

---

📝 **Created by ducanhduocdochu**
