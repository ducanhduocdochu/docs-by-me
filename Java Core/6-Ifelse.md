# 🌟 Comprehensive Guide to `if-else` Statements in Java 🌟

## 🔍 What Are `if-else` Statements?
The `if-else` statement is a control flow structure in Java that allows conditional execution of code blocks based on boolean expressions.

---

## 📚 Syntax and Examples

### 1. **`if` Statement**
Executes a block of code if the condition is `true`.

**Syntax:**
```java
if (condition) {
    // Code to execute if condition is true
}
```

**Example:**
```java
int age = 18;
if (age >= 18) {
    System.out.println("You are eligible to vote.");
}
```

---

### 2. **`if-else` Statement**
Executes one block of code if the condition is `true` and another if it is `false`.

**Syntax:**
```java
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

**Example:**
```java
int age = 16;
if (age >= 18) {
    System.out.println("You are eligible to vote.");
} else {
    System.out.println("You are not eligible to vote.");
}
```

---

### 3. **`if-else if-else` Statement**
Allows multiple conditions to be checked in sequence.

**Syntax:**
```java
if (condition1) {
    // Code to execute if condition1 is true
} else if (condition2) {
    // Code to execute if condition2 is true
} else {
    // Code to execute if none of the above conditions are true
}
```

**Example:**
```java
int marks = 85;
if (marks >= 90) {
    System.out.println("Grade: A+");
} else if (marks >= 80) {
    System.out.println("Grade: A");
} else if (marks >= 70) {
    System.out.println("Grade: B");
} else {
    System.out.println("Grade: C");
}
```

---

### 4. **Nested `if-else` Statement**
`if-else` statements can be nested within each other.

**Syntax:**
```java
if (condition1) {
    if (condition2) {
        // Code to execute if both condition1 and condition2 are true
    } else {
        // Code to execute if condition1 is true and condition2 is false
    }
} else {
    // Code to execute if condition1 is false
}
```

**Example:**
```java
int age = 25;
boolean hasID = true;
if (age >= 18) {
    if (hasID) {
        System.out.println("You can enter.");
    } else {
        System.out.println("ID is required.");
    }
} else {
    System.out.println("You are not old enough to enter.");
}
```

---

### 5. **Ternary Operator (`? :`)**
A shorthand for `if-else` statements.

**Syntax:**
```java
variable = (condition) ? expression1 : expression2;
```

**Example:**
```java
int age = 20;
String result = (age >= 18) ? "Adult" : "Minor";
System.out.println(result); // Output: Adult
```

---

## 🛠️ Common Mistakes and Tips

### 1. **Using `=` Instead of `==`**
- **Mistake:**
```java
if (x = 10) { // Error: Assignment instead of comparison
    // Code
}
```
- **Fix:**
```java
if (x == 10) {
    // Code
}
```

### 2. **Unnecessary Conditions**
Avoid redundant conditions that make the code less readable.

**Example:**
```java
// Inefficient
if (x > 0) {
    if (x < 10) {
        System.out.println("x is between 1 and 9");
    }
}

// Better
if (x > 0 && x < 10) {
    System.out.println("x is between 1 and 9");
}
```

### 3. **Braces for Single Statements**
Always use braces `{}` to avoid ambiguity and reduce errors.

**Example:**
```java
// Avoid this
if (x > 0)
    System.out.println("Positive");
    System.out.println("This is always executed"); // Confusing

// Better
if (x > 0) {
    System.out.println("Positive");
}
```

---

## 💡 Best Practices
- Keep conditions simple and readable.
- Use `else if` instead of nested `if` statements when possible.
- Leverage the ternary operator for concise `if-else` logic.
- Avoid deeply nested structures by refactoring logic into methods.

---

Mastering `if-else` statements allows you to build dynamic and flexible Java applications! 🚀

---

📝 **Created by ducanhduocdochu**
