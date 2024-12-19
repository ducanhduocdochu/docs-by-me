# 🚀 Constructors in Java

Constructors in Java are special methods used to initialize objects. They are called when an object of a class is created. Let's dive into all the details about constructors in Java.

---

## 🏗️ What is a Constructor?
- A constructor is a block of code similar to a method.
- It is called when an instance of a class is created.
- The name of the constructor must match the name of the class.
- Constructors do not have a return type (not even `void`).

---

## 🔑 Key Characteristics
1. **Automatic Invocation**: Called automatically when an object is created.
2. **No Return Type**: Does not return any value, not even `void`.
3. **Name Matching**: Must have the same name as the class.
4. **Can Be Overloaded**: You can define multiple constructors with different parameter lists.

---

## 🌟 Types of Constructors
### 1. **Default Constructor**
- A constructor provided by Java if no other constructors are defined.
- Has no parameters.

```java
class Example {
    // Default constructor
    Example() {
        System.out.println("Default constructor called!");
    }

    public static void main(String[] args) {
        Example obj = new Example();
    }
}
```

### 2. **Parameterized Constructor**
- Accepts arguments to initialize an object with specific values.

```java
class Example {
    int value;

    // Parameterized constructor
    Example(int value) {
        this.value = value;
    }

    public static void main(String[] args) {
        Example obj = new Example(10);
        System.out.println("Value: " + obj.value);
    }
}
```

### 3. **No-Argument Constructor**
- A constructor that does not accept any parameters. Explicitly defined by the programmer.

```java
class Example {
    // No-argument constructor
    Example() {
        System.out.println("No-argument constructor called!");
    }

    public static void main(String[] args) {
        Example obj = new Example();
    }
}
```

### 4. **Copy Constructor**
- Used to create a new object as a copy of an existing object.
- Not built-in, but can be defined manually.

```java
class Example {
    int value;

    // Parameterized constructor
    Example(int value) {
        this.value = value;
    }

    // Copy constructor
    Example(Example obj) {
        this.value = obj.value;
    }

    public static void main(String[] args) {
        Example obj1 = new Example(10);
        Example obj2 = new Example(obj1); // Copy constructor

        System.out.println("Value of obj1: " + obj1.value);
        System.out.println("Value of obj2: " + obj2.value);
    }
}
```

---

## ⚙️ Constructor Overloading
- You can have multiple constructors in the same class with different parameter lists.

```java
class Example {
    int value;

    // Constructor 1: No arguments
    Example() {
        value = 0;
    }

    // Constructor 2: One argument
    Example(int value) {
        this.value = value;
    }

    public static void main(String[] args) {
        Example obj1 = new Example();
        Example obj2 = new Example(42);

        System.out.println("Value of obj1: " + obj1.value);
        System.out.println("Value of obj2: " + obj2.value);
    }
}
```

---

## 🛑 Rules and Restrictions
1. A class can have multiple constructors but they must have different parameter lists (overloading).
2. If no constructor is defined, Java provides a default constructor.
3. If any constructor is defined, the default constructor is not provided.
4. You cannot call a constructor explicitly like a method.

---

## 🌀 Using `this()` and `super()`
### **`this()`**
- Refers to another constructor in the same class.
- Must be the first statement in the constructor.

```java
class Example {
    int value;

    // Constructor 1
    Example() {
        this(42); // Calls Constructor 2
        System.out.println("Default constructor called.");
    }

    // Constructor 2
    Example(int value) {
        this.value = value;
        System.out.println("Parameterized constructor called.");
    }

    public static void main(String[] args) {
        Example obj = new Example();
    }
}
```

### **`super()`**
- Refers to a constructor in the parent class.
- Must be the first statement in the derived class constructor.

```java
class Parent {
    Parent() {
        System.out.println("Parent constructor called.");
    }
}

class Child extends Parent {
    Child() {
        super(); // Calls Parent constructor
        System.out.println("Child constructor called.");
    }

    public static void main(String[] args) {
        Child obj = new Child();
    }
}
```

---

## 🔥 Common Errors
1. **Missing `this` keyword**: Can lead to shadowing of instance variables.
2. **Improper use of `this()` or `super()`**: Not placing them as the first statement.
3. **No default constructor**: If only parameterized constructors exist, objects cannot be created without arguments unless explicitly handled.

---

## 🎯 Summary
- Constructors initialize objects and provide flexibility in object creation.
- Mastering constructors enables cleaner, more maintainable code.
- Use overloading, `this()`, and `super()` wisely for advanced functionality.

Happy Coding! 😊

---

📝 **Created by ducanhduocdochu**
