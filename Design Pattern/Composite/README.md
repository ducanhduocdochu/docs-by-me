
# 🎨 Design Pattern: Composite

---

## 📖 1. Overview of Composite
The Composite Design Pattern is a **Structural Design Pattern** that allows you to compose objects into tree-like structures to represent part-whole hierarchies. This pattern lets clients treat individual objects and compositions of objects uniformly, providing a flexible way to work with complex structures.

- 💡 **Key Features**:
  - **Hierarchical Structure**: Organizes objects into tree structures, where a group of objects can be treated the same as a single object.
  - **Uniformity**: Provides uniformity in how individual objects and composites of objects are handled.
  - **Simplified Client Code**: Allows clients to interact with objects and their compositions through a common interface.

---

## 🚀 2. Composite Pattern in Action
Here's a practical example of the Composite Pattern in Java:

### 🎯 Code Example: Creating Part-Whole Hierarchies with Composite
```java
// Component
interface Graphic {
    void draw();
}

// Leaf
class Circle implements Graphic {
    public void draw() {
        System.out.println("Drawing a Circle.");
    }
}

// Another Leaf
class Rectangle implements Graphic {
    public void draw() {
        System.out.println("Drawing a Rectangle.");
    }
}

// Composite
class CompositeGraphic implements Graphic {
    private List<Graphic> childGraphics = new ArrayList<>();

    public void add(Graphic graphic) {
        childGraphics.add(graphic);
    }

    public void remove(Graphic graphic) {
        childGraphics.remove(graphic);
    }

    public void draw() {
        for (Graphic graphic : childGraphics) {
            graphic.draw();
        }
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        // Creating leaf objects
        Graphic circle = new Circle();
        Graphic rectangle = new Rectangle();

        // Creating composite objects
        CompositeGraphic composite = new CompositeGraphic();
        composite.add(circle);
        composite.add(rectangle);

        // Drawing all graphics
        composite.draw();  // Output: Drawing a Circle. Drawing a Rectangle.
    }
}
```

### 🛠️ How It Works:
- **Component**: The `Graphic` interface defines the common operations (e.g., `draw`) for both individual objects and composite objects.
- **Leaf**: The `Circle` and `Rectangle` classes represent individual objects.
- **Composite**: The `CompositeGraphic` class contains a collection of `Graphic` objects and performs operations on them.

---

## 🌐 3. Composite Pattern in Real Systems
A real-world example of the Composite Pattern can be seen in GUI frameworks, where components like windows, buttons, and text fields are arranged hierarchically.

### 🖥️ Example: File System Hierarchy
```java
// Component
interface FileSystem {
    void showDetails();
}

// Leaf
class File implements FileSystem {
    private String name;

    public File(String name) {
        this.name = name;
    }

    public void showDetails() {
        System.out.println("File: " + name);
    }
}

// Composite
class Directory implements FileSystem {
    private String name;
    private List<FileSystem> children = new ArrayList<>();

    public Directory(String name) {
        this.name = name;
    }

    public void add(FileSystem fileSystem) {
        children.add(fileSystem);
    }

    public void remove(FileSystem fileSystem) {
        children.remove(fileSystem);
    }

    public void showDetails() {
        System.out.println("Directory: " + name);
        for (FileSystem fileSystem : children) {
            fileSystem.showDetails();
        }
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        FileSystem file1 = new File("file1.txt");
        FileSystem file2 = new File("file2.txt");

        Directory directory = new Directory("Documents");
        directory.add(file1);
        directory.add(file2);

        directory.showDetails();  // Output: Directory: Documents File: file1.txt File: file2.txt
    }
}
```

📘 In this example:
- **FileSystem** is the abstraction, which can either be a single file or a directory.
- **File** is a leaf that represents an individual file.
- **Directory** is a composite that contains multiple files or other directories.

---

## ⚙️ 4. Pros and Cons of Composite

### ✅ **Advantages**:
- **Simplifies Client Code**: Clients can treat individual objects and compositions uniformly.
- **Flexibility**: Allows creation of complex hierarchies dynamically.
- **Scalability**: Makes it easy to add new types of components (both individual objects and composites).

### ❌ **Disadvantages**:
- **Complexity**: Introducing composite structures can add unnecessary complexity if the system does not need part-whole hierarchies.
- **Overhead**: Manipulating large structures can introduce performance overhead.

---

## 🌍 5. Real-World Applications
The Composite Pattern is widely used in systems like:
- **File Systems**: Where files and directories are treated uniformly.
- **GUI Toolkits**: Where components like panels, buttons, and text fields are part of a hierarchical structure.

---

📝 **Created by ducanhduocdochu**
