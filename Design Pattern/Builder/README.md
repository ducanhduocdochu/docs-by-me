
# 🎨 Design Pattern: Builder

---

## 📖 1. Overview of Builder Pattern
The **Builder Pattern** is a **Creational Design Pattern** that allows constructing complex objects step by step. Unlike other creational patterns, the Builder pattern separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

### 💡 Key Features:
- **Step-by-Step Construction:** Objects are constructed through a series of discrete steps.
- **Decoupling:** The construction logic is separated from the final product's structure.
- **Customizable Objects:** It allows constructing complex objects with various representations or configurations.

---

## 🚀 2. Builder Pattern in Action
Here’s an example demonstrating the Builder pattern in Java:

### 🎯 Code Example: Building Complex Objects with Builder
```java
// Product class
class House {
    private String foundation;
    private String structure;
    private String roof;
    private boolean hasGarage;
    private boolean hasSwimmingPool;

    public void setFoundation(String foundation) {
        this.foundation = foundation;
    }

    public void setStructure(String structure) {
        this.structure = structure;
    }

    public void setRoof(String roof) {
        this.roof = roof;
    }

    public void setGarage(boolean hasGarage) {
        this.hasGarage = hasGarage;
    }

    public void setSwimmingPool(boolean hasSwimmingPool) {
        this.hasSwimmingPool = hasSwimmingPool;
    }

    @Override
    public String toString() {
        return "House [Foundation=" + foundation + ", Structure=" + structure + 
               ", Roof=" + roof + ", Garage=" + hasGarage + 
               ", Swimming Pool=" + hasSwimmingPool + "]";
    }
}

// Builder Interface
interface HouseBuilder {
    void buildFoundation();
    void buildStructure();
    void buildRoof();
    void buildGarage();
    void buildSwimmingPool();
    House getHouse();
}

// Concrete Builder
class ConcreteHouseBuilder implements HouseBuilder {
    private House house;

    public ConcreteHouseBuilder() {
        this.house = new House();
    }

    public void buildFoundation() {
        house.setFoundation("Concrete foundation");
    }

    public void buildStructure() {
        house.setStructure("Wooden structure");
    }

    public void buildRoof() {
        house.setRoof("Shingle roof");
    }

    public void buildGarage() {
        house.setGarage(true);
    }

    public void buildSwimmingPool() {
        house.setSwimmingPool(true);
    }

    public House getHouse() {
        return this.house;
    }
}

// Director class
class ConstructionEngineer {
    private HouseBuilder houseBuilder;

    public ConstructionEngineer(HouseBuilder houseBuilder) {
        this.houseBuilder = houseBuilder;
    }

    public House constructHouse() {
        houseBuilder.buildFoundation();
        houseBuilder.buildStructure();
        houseBuilder.buildRoof();
        houseBuilder.buildGarage();
        houseBuilder.buildSwimmingPool();
        return houseBuilder.getHouse();
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        HouseBuilder builder = new ConcreteHouseBuilder();
        ConstructionEngineer engineer = new ConstructionEngineer(builder);

        House house = engineer.constructHouse();
        System.out.println(house);
    }
}
```

---

## 🌐 3. Builder Pattern vs Other Creational Patterns
Unlike **Factory Method** or **Abstract Factory**, the **Builder Pattern** is used when you need to build complex objects step by step, especially when there are many optional features or configurations.

### Example Scenario:
Imagine you are building a house. You may have different configurations: some houses may have a garage, a swimming pool, or specific kinds of roofs. The Builder Pattern allows for constructing such diverse configurations without modifying the core product.

---

## ⚙️ 4. Pros and Cons of Builder Pattern
### ✅ Advantages:
- **Complex Object Construction:** It simplifies the process of constructing complex objects with many optional features.
- **Clearer Code:** The construction process is broken down into small, manageable steps.
- **Reusability:** Builders can be reused across various complex object constructions.

### ❌ Disadvantages:
- **Overhead:** If the object isn’t complex enough, using the Builder pattern may introduce unnecessary overhead.
- **Construction Logic:** You need to ensure that the Director or client code follows the correct steps in building the object.

---

## 🌍 5. Real-World Applications
- **GUI Builders:** Used for building complex UIs where different components need to be assembled (buttons, sliders, windows, etc.).
- **Document Generation:** Builders can be used to assemble complex documents like reports or presentations with optional sections.
- **Vehicle Assembly:** Car builders assemble complex configurations of vehicles with different parts (engines, tires, interiors).

---

📝 **Created by ducanhduocdochu**
