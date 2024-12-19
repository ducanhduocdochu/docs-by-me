# 🌳 Non-Primitive Types in Java

Non-primitive types in Java, also known as reference types, are more complex than primitive types. They are used to store references to memory locations where data is stored, rather than directly storing the data themselves.

---

## 📜 Types of Non-Primitive Data
1. **Classes**: User-defined data types that define the blueprint for objects.
2. **Interfaces**: Define a contract for classes without implementation.
3. **Arrays**: Fixed-size collections of similar data types.
4. **Enums**: Special types used to define a set of constants.
5. **Strings**: Immutable sequences of characters.
6. **Collections**: Framework classes for dynamic data management (e.g., Lists, Sets, Maps).

---

## 🔍 Characteristics of Non-Primitive Types
- **Reference-based**: Store references (memory addresses) instead of raw values.
- **Default Value**: If uninitialized, their default value is `null`.
- **Memory Size**: Depends on the JVM and the actual data structure.
- **Extensibility**: Can include methods, properties, and user-defined behaviors.
- **Garbage Collection**: Managed by the JVM, unlike primitive types.

---

## 📘 Detailed Explanation

### 1. **Classes**
- **Definition**: A class is a blueprint for creating objects. It can include fields (variables) and methods (functions).

#### Example:
```java
class Person {
    String name;
    int age;

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

Person person = new Person();
person.name = "Alice";
person.age = 25;
person.display(); // Output: Name: Alice, Age: 25
```

#### Key Points:
- Classes can have constructors to initialize objects.
- Methods in classes can be overloaded or overridden.
- Fields can have different access modifiers (e.g., `private`, `protected`, `public`).

---

### 2. **Interfaces**
- **Definition**: Interfaces define a contract for classes to implement. All methods in interfaces are implicitly `public` and `abstract`.

#### Example:
```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Woof Woof");
    }
}

Animal dog = new Dog();
dog.sound(); // Output: Woof Woof
```

#### Key Points:
- Interfaces support multiple inheritance.
- Fields in interfaces are `public`, `static`, and `final` by default.
- Interfaces can have default and static methods (from Java 8 onwards).

---

### 3. **Arrays**
- **Definition**: Arrays are fixed-size, ordered collections of elements of the same type.

#### Single-Dimensional Array Example:
```java
int[] numbers = {1, 2, 3, 4, 5};
System.out.println(numbers[2]); // Output: 3
```

#### Multi-Dimensional Array Example:
```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println(matrix[1][2]); // Output: 6
```

#### Key Points:
- Arrays are indexed starting from `0`.
- Can be dynamically initialized: `int[] arr = new int[5];`.
- Length is accessed using `.length` property.

---

### 4. **Enums**
- **Definition**: Enums are special classes that represent a group of constants (unchangeable variables).

#### Example:
```java
enum Days {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY;
}

Days today = Days.WEDNESDAY;
System.out.println(today); // Output: WEDNESDAY
```

#### Key Points:
- Can have fields, methods, and constructors.
- Useful for predefined sets of values (e.g., days, states).
- Cannot be extended.

---

### 5. **Strings**
- **Definition**: Strings are sequences of characters and are immutable in Java.

#### Example:
```java
String greeting = "Hello, World!";
System.out.println(greeting.toUpperCase()); // Output: HELLO, WORLD!
```

#### Common Methods:
| Method          | Description                               |
|-----------------|-------------------------------------------|
| `length()`      | Returns the length of the string.         |
| `charAt(int i)` | Returns the character at index `i`.       |
| `substring()`   | Extracts a substring.                    |
| `replace()`     | Replaces characters or substrings.        |
| `split()`       | Splits the string into an array.          |

---

### 6. **Collections**
- **Definition**: Collections are part of the Java Collections Framework and are used for dynamic data management.

#### List Example:
```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
System.out.println(list.get(1)); // Output: Banana
```

#### Set Example:
```java
import java.util.HashSet;

HashSet<Integer> set = new HashSet<>();
set.add(1);
set.add(2);
set.add(2); // Duplicate is ignored
System.out.println(set.size()); // Output: 2
```

#### Map Example:
```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Alice", 30);
map.put("Bob", 25);
System.out.println(map.get("Alice")); // Output: 30
```

#### Key Points:
- **List**: Allows duplicates and maintains order.
- **Set**: No duplicates allowed, unordered.
- **Map**: Stores key-value pairs.
- Collections have utility classes like `Collections` for operations like sorting.

---

## 🌟 Differences Between Primitive and Non-Primitive Types

| Feature              | Primitive Types            | Non-Primitive Types                 |
|----------------------|----------------------------|-------------------------------------|
| Storage              | Stores values directly     | Stores references to objects        |
| Default Value        | Type-specific (`0`, `false`)| `null`                              |
| Size                 | Fixed                      | Variable (depends on JVM)           |
| Methods Available    | None                       | Multiple utility methods available  |
| Extensibility        | No                         | Yes                                 |

---

## 🔄 Wrapper Classes
Primitive types can be converted into non-primitive types using **Wrapper Classes**.

| Primitive Type | Wrapper Class |
|----------------|---------------|
| `byte`         | `Byte`        |
| `short`        | `Short`       |
| `int`          | `Integer`     |
| `long`         | `Long`        |
| `float`        | `Float`       |
| `double`       | `Double`      |
| `char`         | `Character`   |
| `boolean`      | `Boolean`     |

#### Example:
```java
int primitive = 10;
Integer wrapper = Integer.valueOf(primitive); // Boxing
int unboxed = wrapper.intValue(); // Unboxing
```

---

## 🚀 Use Cases
1. **Classes**: Represent real-world entities.
2. **Interfaces**: Define behaviors across unrelated classes.
3. **Arrays**: Store collections of fixed size.
4. **Enums**: Use for fixed categories (e.g., days of the week).
5. **Strings**: Handle textual data.
6. **Collections**: Manage dynamic groups of objects.

---

Happy Coding! 😊

---

📝 **Created by ducanhduocdochu**
