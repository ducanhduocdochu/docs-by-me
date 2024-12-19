# 🧩 Primitive Types in Java

In Java, primitive types are the most basic data types that are not objects. They are predefined by the language and serve as building blocks for data manipulation.

---

## 📜 List of Primitive Types
Java provides 8 primitive types:

| Type      | Size (bits) | Default Value | Description                             |
|-----------|-------------|---------------|-----------------------------------------|
| `byte`    | 8           | `0`           | Small integer (-128 to 127)             |
| `short`   | 16          | `0`           | Medium integer (-32,768 to 32,767)      |
| `int`     | 32          | `0`           | Standard integer (-2³¹ to 2³¹-1)        |
| `long`    | 64          | `0L`          | Large integer (-2⁶³ to 2⁶³-1)          |
| `float`   | 32          | `0.0f`        | Single-precision floating-point         |
| `double`  | 64          | `0.0d`        | Double-precision floating-point         |
| `char`    | 16          | `\u0000`      | Single 16-bit Unicode character         |
| `boolean` | 1 (logical) | `false`       | Logical value (`true` or `false`)       |

---

## 🔍 Detailed Explanation

### 1. **`byte`**
- Smallest integer type.
- Useful for saving memory in large arrays.

```java
byte b = 100;
System.out.println(b); // Output: 100
```

### 2. **`short`**
- Larger than `byte` but smaller than `int`.

```java
short s = 32000;
System.out.println(s); // Output: 32000
```

### 3. **`int`**
- Default data type for integer values.

```java
int i = 100000;
System.out.println(i); // Output: 100000
```

### 4. **`long`**
- Used for very large integer values. Needs an `L` suffix.

```java
long l = 10000000000L;
System.out.println(l); // Output: 10000000000
```

### 5. **`float`**
- Single-precision floating-point.
- Needs an `f` suffix.

```java
float f = 3.14f;
System.out.println(f); // Output: 3.14
```

### 6. **`double`**
- Default data type for decimal values.

```java
double d = 3.14159265359;
System.out.println(d); // Output: 3.14159265359
```

### 7. **`char`**
- Holds a single character or Unicode value.

```java
char c = 'A';
System.out.println(c); // Output: A
```

### 8. **`boolean`**
- Logical type representing `true` or `false`.

```java
boolean flag = true;
System.out.println(flag); // Output: true
```

---

## 🚀 Default Values
Primitive types have default values if not explicitly initialized:

| Type      | Default Value |
|-----------|---------------|
| `byte`    | `0`           |
| `short`   | `0`           |
| `int`     | `0`           |
| `long`    | `0L`          |
| `float`   | `0.0f`        |
| `double`  | `0.0d`        |
| `char`    | `\u0000`      |
| `boolean` | `false`       |

---

## 🔄 Type Conversion
### 1. **Implicit Casting (Widening)**
- Converts smaller types to larger types automatically.

```java
int i = 100;
long l = i; // Implicit casting
System.out.println(l); // Output: 100
```

### 2. **Explicit Casting (Narrowing)**
- Converts larger types to smaller types manually.

```java
long l = 100000L;
int i = (int) l; // Explicit casting
System.out.println(i); // Output: 100000
```

---

## 🔥 Wrapper Classes
Primitive types have corresponding wrapper classes in `java.lang` package:

| Primitive | Wrapper   |
|-----------|-----------|
| `byte`    | `Byte`    |
| `short`   | `Short`   |
| `int`     | `Integer` |
| `long`    | `Long`    |
| `float`   | `Float`   |
| `double`  | `Double`  |
| `char`    | `Character` |
| `boolean` | `Boolean` |

### Example:
```java
int primitive = 5;
Integer wrapper = Integer.valueOf(primitive); // Boxing
int unboxed = wrapper.intValue(); // Unboxing
```

---

## 🛠️ Common Operations

### Arithmetic Operations
```java
int a = 10;
int b = 20;
System.out.println(a + b); // Output: 30
```

### Relational Operations
```java
int x = 10;
int y = 20;
System.out.println(x < y); // Output: true
```

### Logical Operations
```java
boolean flag1 = true;
boolean flag2 = false;
System.out.println(flag1 && flag2); // Output: false
```

---

## 🌟 Summary Table
| Type      | Size   | Range                          | Default Value |
|-----------|--------|--------------------------------|---------------|
| `byte`    | 8 bits | -128 to 127                   | `0`           |
| `short`   | 16 bits| -32,768 to 32,767             | `0`           |
| `int`     | 32 bits| -2³¹ to 2³¹-1                 | `0`           |
| `long`    | 64 bits| -2⁶³ to 2⁶³-1                 | `0L`          |
| `float`   | 32 bits| ~6-7 decimal digits precision | `0.0f`        |
| `double`  | 64 bits| ~15 decimal digits precision  | `0.0d`        |
| `char`    | 16 bits| Unicode (\u0000 to \uFFFF)   | `\u0000`      |
| `boolean` | 1 bit  | `true` or `false`             | `false`       |

---

Happy Coding! 😊

---

📝 **Created by ducanhduocdochu**
