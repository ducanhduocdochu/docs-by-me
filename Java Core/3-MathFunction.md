# ✨ Comprehensive Guide to Math Functions in Java ✨

## 🔢 Introduction to Java Math Functions
Java provides a robust set of mathematical functions within the `java.lang.Math` class. These functions help perform complex calculations such as trigonometry, logarithms, exponential functions, and more.

---

## 🔍 Commonly Used Math Functions

### 1. **Basic Operations**
- **`Math.abs(x)`**: Returns the absolute value of `x`.
  
  **Example:**
  ```java
  System.out.println(Math.abs(-5)); // Output: 5
  ```

- **`Math.max(a, b)`**: Returns the larger of `a` and `b`.
  
  **Example:**
  ```java
  System.out.println(Math.max(10, 20)); // Output: 20
  ```

- **`Math.min(a, b)`**: Returns the smaller of `a` and `b`.
  
  **Example:**
  ```java
  System.out.println(Math.min(10, 20)); // Output: 10
  ```

- **`Math.sqrt(x)`**: Returns the square root of `x`.
  
  **Example:**
  ```java
  System.out.println(Math.sqrt(16)); // Output: 4.0
  ```

- **`Math.cbrt(x)`**: Returns the cube root of `x`.
  
  **Example:**
  ```java
  System.out.println(Math.cbrt(27)); // Output: 3.0
  ```

---

### 2. **Exponential and Logarithmic Functions**
- **`Math.pow(a, b)`**: Raises `a` to the power of `b`.
  
  **Example:**
  ```java
  System.out.println(Math.pow(2, 3)); // Output: 8.0
  ```

- **`Math.exp(x)`**: Returns `e^x` (Euler's number raised to the power of `x`).
  
  **Example:**
  ```java
  System.out.println(Math.exp(1)); // Output: 2.718281828459045
  ```

- **`Math.log(x)`**: Returns the natural logarithm (base `e`) of `x`.
  
  **Example:**
  ```java
  System.out.println(Math.log(10)); // Output: 2.302585092994046
  ```

- **`Math.log10(x)`**: Returns the base 10 logarithm of `x`.
  
  **Example:**
  ```java
  System.out.println(Math.log10(100)); // Output: 2.0
  ```

---

### 3. **Trigonometric Functions**
- **`Math.sin(x)`**: Returns the sine of `x` (in radians).
  
  **Example:**
  ```java
  System.out.println(Math.sin(Math.PI / 2)); // Output: 1.0
  ```

- **`Math.cos(x)`**: Returns the cosine of `x` (in radians).
  
  **Example:**
  ```java
  System.out.println(Math.cos(0)); // Output: 1.0
  ```

- **`Math.tan(x)`**: Returns the tangent of `x` (in radians).
  
  **Example:**
  ```java
  System.out.println(Math.tan(Math.PI / 4)); // Output: 1.0
  ```

- **Inverse Trigonometric Functions:**
  - **`Math.asin(x)`**: Returns the arcsine of `x`.
  - **`Math.acos(x)`**: Returns the arccosine of `x`.
  - **`Math.atan(x)`**: Returns the arctangent of `x`.

**Example:**
```java
System.out.println(Math.asin(1)); // Output: 1.5707963267948966 (PI/2)
```

---

### 4. **Rounding Functions**
- **`Math.ceil(x)`**: Rounds `x` up to the nearest integer.
  
  **Example:**
  ```java
  System.out.println(Math.ceil(4.3)); // Output: 5.0
  ```

- **`Math.floor(x)`**: Rounds `x` down to the nearest integer.
  
  **Example:**
  ```java
  System.out.println(Math.floor(4.7)); // Output: 4.0
  ```

- **`Math.round(x)`**: Rounds `x` to the nearest integer.
  
  **Example:**
  ```java
  System.out.println(Math.round(4.5)); // Output: 5
  ```

---

### 5. **Random Number Generation**
- **`Math.random()`**: Returns a random double value between `0.0` (inclusive) and `1.0` (exclusive).

**Example:**
```java
System.out.println(Math.random());
// Output: A random number between 0.0 and 1.0
```

To generate random numbers in a specific range:
```java
int min = 1;
int max = 10;
int randomNumber = (int)(Math.random() * (max - min + 1) + min);
System.out.println(randomNumber);
// Output: A random number between min and max
```

---

## 💡 Tips for Using Math Functions
- Use `Math.toRadians(x)` and `Math.toDegrees(x)` to convert angles between degrees and radians.

**Example:**
```java
System.out.println(Math.toRadians(90)); // Output: 1.5707963267948966
System.out.println(Math.toDegrees(Math.PI)); // Output: 180.0
```

- Combine multiple Math functions for complex calculations.

**Example:**
```java
System.out.println(Math.sqrt(Math.pow(3, 2) + Math.pow(4, 2))); // Output: 5.0
```

---

## 🔧 Common Mistakes
1. **Passing invalid arguments:**
   ```java
   System.out.println(Math.sqrt(-1)); // Output: NaN (Not a Number)
   ```

2. **Forgetting to cast results:**
   ```java
   int result = Math.round(4.5); // Error: Math.round returns a long, not an int
   ```

3. **Confusing radians and degrees:**
   ```java
   System.out.println(Math.sin(90)); // Output: Not the expected value (90 is in radians)
   ```

---

By mastering these functions, you can handle all sorts of mathematical operations in Java with ease! ✨

--- 

📝 **Created by ducanhduocdochu**
