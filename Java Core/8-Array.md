# 📋 Java Arrays: Comprehensive Guide

## 📌 What is an Array?
An array in Java is a container object that holds a fixed number of values of a single type. The length of an array is established when the array is created, and it cannot be changed afterward.

---

## 🌟 Features of Arrays
- **Fixed Size**: Once defined, the size of the array cannot change.
- **Indexed**: Each element can be accessed using its index, starting from `0`.
- **Homogeneous**: Arrays store elements of the same type.
- **Memory-efficient**: Provides a way to store multiple values in a single data structure.

---

## 🛠️ Syntax for Declaring Arrays
```java
// Declaration
int[] numbers;
String[] names;

// Initialization
numbers = new int[5];
String[] cities = {"New York", "London", "Tokyo"};
```

---

## 📚 Types of Arrays
### 1. **Single-dimensional Arrays**
A linear array where elements are stored in a single row.
```java
int[] arr = new int[5]; // Declare an array of integers
arr[0] = 10; // Assign value
System.out.println(arr[0]); // Access value
```

### 2. **Multi-dimensional Arrays**
Arrays within arrays, commonly used for matrices or grids.
```java
int[][] matrix = new int[3][3]; // 3x3 matrix
matrix[0][0] = 1; // Assign value
System.out.println(matrix[0][0]); // Access value
```

---

## 🔍 Common Operations

### 1. **Traversing an Array**
Using loops to access elements.
```java
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

### 2. **Sorting an Array**
Using built-in utility classes like `Arrays`.
```java
import java.util.Arrays;

int[] numbers = {5, 3, 1, 4, 2};
Arrays.sort(numbers); // Sort in ascending order
System.out.println(Arrays.toString(numbers));
```

### 3. **Copying an Array**
```java
int[] original = {1, 2, 3};
int[] copy = Arrays.copyOf(original, original.length);
System.out.println(Arrays.toString(copy));
```

---

## 🚀 Advanced Topics
### 1. **Dynamic Arrays**
While traditional arrays are fixed-size, `ArrayList` in `java.util` package can be resized dynamically.
```java
import java.util.ArrayList;

ArrayList<Integer> list = new ArrayList<>();
list.add(1); // Add element
list.add(2);
System.out.println(list);
```

### 2. **Arrays with Objects**
```java
class Person {
    String name;
    Person(String name) {
        this.name = name;
    }
}

Person[] people = {new Person("Alice"), new Person("Bob")};
System.out.println(people[0].name); // Access object property
```

---

## ⚡ Common Pitfalls
1. **ArrayIndexOutOfBoundsException**: Accessing an index beyond the array's range.
   ```java
   int[] numbers = {1, 2, 3};
   System.out.println(numbers[3]); // Error
   ```

2. **NullPointerException**: Using uninitialized arrays.
   ```java
   int[] numbers = null;
   System.out.println(numbers.length); // Error
   ```

---

## 🛡️ Best Practices
- Always check array bounds before accessing elements.
- Use `Arrays.toString()` for a readable representation of arrays.
- Prefer `ArrayList` for dynamic collections.

---

## 📖 Useful References
- [Java Arrays Documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
- [Java ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html)

---

🔗 **Happy Coding with Arrays!** 🎉

---

📝 **Created by ducanhduocdochu**
