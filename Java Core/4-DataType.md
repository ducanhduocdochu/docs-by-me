# ✨ Comprehensive Guide to Data Types in Java ✨

## 🔢 What Are Data Types in Java?
Data types in Java define the type and size of data a variable can hold. They are crucial for ensuring type safety and optimizing memory usage.

---

## 🔍 Categories of Data Types

### 1. **Primitive Data Types**
Java has 8 built-in primitive data types:

| Data Type   | Size    | Default Value | Description                          |
|-------------|---------|---------------|--------------------------------------|
| `byte`      | 1 byte  | `0`           | Small integer, range: -128 to 127    |
| `short`     | 2 bytes | `0`           | Larger integer, range: -32,768 to 32,767 |
| `int`       | 4 bytes | `0`           | Standard integer, range: -2³¹ to 2³¹-1 |
| `long`      | 8 bytes | `0L`          | Large integer, range: -2⁶³ to 2⁶³-1 |
| `float`     | 4 bytes | `0.0f`        | Single-precision decimal, ~7 digits |
| `double`    | 8 bytes | `0.0d`        | Double-precision decimal, ~15 digits |
| `char`      | 2 bytes | `\u0000`      | Single Unicode character             |
| `boolean`   | 1 bit   | `false`       | Represents `true` or `false`         |

**Examples:**
```java
byte age = 25;
int salary = 50000;
boolean isJavaFun = true;
double pi = 3.14159;
```

---

### 2. **Non-Primitive Data Types**
These include classes, interfaces, and arrays. They do not store the actual data value but reference the memory location where the data is stored.

#### Common Examples:
1. **`String`**
   - Represents a sequence of characters.
   - Immutable in nature.

   **Example:**
   ```java
   String name = "Java";
   ```

2. **`Array`**
   - Stores a fixed-size collection of elements of the same type.

   **Example:**
   ```java
   int[] numbers = {1, 2, 3};
   ```

3. **`Class` and `Object`**
   - Classes are blueprints for objects.

   **Example:**
   ```java
   class Car {
       String model;
       int year;
   }
   ```

---

## 🔮 Default Values for Data Types
| Data Type   | Default Value |
|-------------|---------------|
| `byte`      | `0`           |
| `short`     | `0`           |
| `int`       | `0`           |
| `long`      | `0L`          |
| `float`     | `0.0f`        |
| `double`    | `0.0d`        |
| `char`      | `\u0000`      |
| `boolean`   | `false`       |
| Object Types | `null`       |

---

## 🎨 Type Casting
Java allows type casting between compatible data types.

### 1. **Implicit Casting (Widening Conversion):**
- Automatically converts smaller types to larger types.

**Example:**
```java
int x = 100;
double y = x; // int to double
System.out.println(y); // Output: 100.0
```

### 2. **Explicit Casting (Narrowing Conversion):**
- Requires manual conversion when moving from larger to smaller types.

**Example:**
```java
double pi = 3.14159;
int approx = (int) pi; // double to int
System.out.println(approx); // Output: 3
```

---

## 🔧 Wrapper Classes
Java provides wrapper classes to use primitive types as objects.

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

**Example:**
```java
int x = 5;
Integer y = Integer.valueOf(x); // Auto-boxing
int z = y.intValue(); // Unboxing
```

---

## 🌟 Best Practices
1. Use `int` for whole numbers unless larger ranges are needed.
2. Prefer `double` for decimal values as it provides better precision.
3. Always initialize variables to avoid unexpected behavior.
4. Use wrapper classes for collections and advanced features like nullability.

---

With these data types and best practices, you can build efficient and type-safe Java applications! 🚀

---

📝 **Created by ducanhduocdochu**
