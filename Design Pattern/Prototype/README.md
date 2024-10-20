
# 🎨 Design Pattern: Prototype

---

## 📖 1. Overview of Prototype Pattern
The **Prototype Pattern** is a **Creational Design Pattern** that enables the creation of new objects by copying or cloning existing ones. It reduces the need to subclass and ensures that the creation process is more flexible by cloning an object rather than creating one from scratch.

### 💡 Key Features:
- **Object Cloning:** Instead of instantiating a new object, it creates a copy of an existing one.
- **Reduces Complexity:** It avoids the need for subclasses when creating variations of objects.
- **Performance Boost:** Cloning an object can be more efficient than creating it from scratch, especially when initialization is costly.

---

## 🚀 2. Prototype Pattern in Action
Here’s an example demonstrating the Prototype pattern in Java:

### 🎯 Code Example: Cloning Objects with Prototype
```java
// Prototype Interface
interface Prototype {
    Prototype clone();
}

// Concrete Prototype 1
class ConcretePrototype1 implements Prototype {
    private String name;

    public ConcretePrototype1(String name) {
        this.name = name;
    }

    @Override
    public Prototype clone() {
        return new ConcretePrototype1(this.name);
    }

    @Override
    public String toString() {
        return "ConcretePrototype1{name='" + name + "'}";
    }
}

// Concrete Prototype 2
class ConcretePrototype2 implements Prototype {
    private int value;

    public ConcretePrototype2(int value) {
        this.value = value;
    }

    @Override
    public Prototype clone() {
        return new ConcretePrototype2(this.value);
    }

    @Override
    public String toString() {
        return "ConcretePrototype2{value=" + value + "}";
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        ConcretePrototype1 prototype1 = new ConcretePrototype1("Prototype1");
        ConcretePrototype2 prototype2 = new ConcretePrototype2(100);

        // Cloning prototypes
        Prototype clone1 = prototype1.clone();
        Prototype clone2 = prototype2.clone();

        System.out.println(clone1);
        System.out.println(clone2);
    }
}
```

---

## 🌐 3. Prototype Pattern vs Other Creational Patterns
While other creational patterns focus on creating new objects, **Prototype Pattern** focuses on duplicating or cloning existing ones, which is useful when object creation is complex or expensive.

### Example Scenario:
If you are working with an object that takes significant time to initialize (e.g., a large database or a complex UI component), instead of creating it from scratch every time, you can clone an existing one.

---

## ⚙️ 4. Pros and Cons of Prototype Pattern
### ✅ Advantages:
- **Avoids Reinitialization:** Cloning avoids reinitializing an object and provides performance improvements when object creation is expensive.
- **Simplifies Object Creation:** It simplifies the creation of objects by cloning instead of requiring a detailed constructor.
- **No Subclassing Needed:** New object variations can be created without modifying existing classes or needing subclasses.

### ❌ Disadvantages:
- **Cloning Complexity:** Depending on the depth of the object (deep or shallow copy), implementing the clone() method can be complex.
- **Cyclic Dependencies:** If objects have circular references, implementing cloning may result in unexpected behavior or require extra handling.

---

## 🌍 5. Real-World Applications
- **UI Components:** Cloning pre-existing UI components in complex applications to avoid constructing new ones each time.
- **Database Entities:** Cloning objects that represent data from a database, allowing you to work with copies rather than re-query the database.
- **Game Development:** In game engines, where you often clone objects like characters, weapons, or environment elements that share similar properties.

---

📝 **Created by ducanhduocdochu**
