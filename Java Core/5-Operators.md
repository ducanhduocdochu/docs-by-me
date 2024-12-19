# ✨ Comprehensive Guide to Operators in Java ✨

## 🔍 What Are Operators?
Operators are special symbols or keywords used to perform operations on variables and values. Java supports a wide range of operators for various functionalities.

---

## 📚 Categories of Operators

### 1. **Arithmetic Operators**
Used to perform basic arithmetic operations.

| Operator | Description           | Example       |
|----------|-----------------------|---------------|
| `+`      | Addition              | `a + b`       |
| `-`      | Subtraction           | `a - b`       |
| `*`      | Multiplication        | `a * b`       |
| `/`      | Division              | `a / b`       |
| `%`      | Modulus (remainder)   | `a % b`       |

**Example:**
```java
int a = 10, b = 3;
System.out.println(a + b); // Output: 13
System.out.println(a % b); // Output: 1
```

---

### 2. **Relational (Comparison) Operators**
Used to compare two values. Returns `true` or `false`.

| Operator | Description             | Example    |
|----------|-------------------------|------------|
| `==`     | Equal to                | `a == b`   |
| `!=`     | Not equal to            | `a != b`   |
| `>`      | Greater than            | `a > b`    |
| `<`      | Less than               | `a < b`    |
| `>=`     | Greater than or equal to| `a >= b`   |
| `<=`     | Less than or equal to   | `a <= b`   |

**Example:**
```java
int x = 5, y = 10;
System.out.println(x < y); // Output: true
System.out.println(x == y); // Output: false
```

---

### 3. **Logical Operators**
Used to perform logical operations on boolean expressions.

| Operator | Description         | Example         |
|----------|---------------------|-----------------|
| `&&`     | Logical AND         | `a && b`        |
| `||`     | Logical OR          | `a || b`        |
| `!`      | Logical NOT         | `!a`            |

**Example:**
```java
boolean isAdult = true, hasID = false;
System.out.println(isAdult && hasID); // Output: false
System.out.println(isAdult || hasID); // Output: true
System.out.println(!isAdult); // Output: false
```

---

### 4. **Bitwise Operators**
Used to perform operations on bits.

| Operator | Description            | Example |
|----------|------------------------|---------|
| `&`      | Bitwise AND            | `a & b` |
| `|`      | Bitwise OR             | `a | b` |
| `^`      | Bitwise XOR            | `a ^ b` |
| `~`      | Bitwise Complement     | `~a`    |
| `<<`     | Left shift             | `a << b`|
| `>>`     | Right shift            | `a >> b`|
| `>>>`    | Unsigned right shift   | `a >>> b`|

**Example:**
```java
int a = 5, b = 3;
System.out.println(a & b); // Output: 1
System.out.println(a | b); // Output: 7
System.out.println(a ^ b); // Output: 6
```

---

### 5. **Assignment Operators**
Used to assign values to variables.

| Operator | Description             | Example    |
|----------|-------------------------|------------|
| `=`      | Simple assignment       | `a = b`    |
| `+=`     | Add and assign          | `a += b`   |
| `-=`     | Subtract and assign     | `a -= b`   |
| `*=`     | Multiply and assign     | `a *= b`   |
| `/=`     | Divide and assign       | `a /= b`   |
| `%=`     | Modulus and assign      | `a %= b`   |

**Example:**
```java
int num = 10;
num += 5; // num = num + 5
System.out.println(num); // Output: 15
```

---

### 6. **Unary Operators**
Operate on a single operand.

| Operator | Description                  | Example      |
|----------|------------------------------|--------------|
| `+`      | Unary plus (positive value)  | `+a`         |
| `-`      | Unary minus (negative value) | `-a`         |
| `++`     | Increment by 1 (prefix/postfix)| `++a`, `a++`|
| `--`     | Decrement by 1 (prefix/postfix)| `--a`, `a--`|
| `!`      | Logical complement           | `!a`         |

**Example:**
```java
int num = 5;
System.out.println(++num); // Output: 6 (prefix)
System.out.println(num--); // Output: 6 (postfix)
System.out.println(num);   // Output: 5
```

---

### 7. **Ternary Operator**
A shorthand for `if-else` statements.

**Syntax:**
```java
condition ? expression1 : expression2;
```

**Example:**
```java
int a = 10, b = 20;
int max = (a > b) ? a : b;
System.out.println(max); // Output: 20
```

---

### 8. **Instanceof Operator**
Used to test whether an object is an instance of a specific class or subclass.

**Example:**
```java
String str = "Hello";
System.out.println(str instanceof String); // Output: true
```

---

## 💡 Operator Precedence
Operators in Java are evaluated in a specific order. For example, multiplication (`*`) has a higher precedence than addition (`+`).

**Example:**
```java
int result = 10 + 5 * 2; // Multiplication is evaluated first
System.out.println(result); // Output: 20
```

| Precedence | Operators                              |
|------------|---------------------------------------|
| Highest    | `()`, `[]`, `.`                       |
|            | `++`, `--` (postfix)                  |
|            | `!`, `~`, `++`, `--` (prefix), `+`, `-` |
|            | `*`, `/`, `%`                         |
|            | `+`, `-`                              |
| Lowest     | `=` and compound assignment operators |

---

Mastering these operators will make your Java programming more efficient and expressive! 🚀

---

📝 **Created by ducanhduocdochu**
