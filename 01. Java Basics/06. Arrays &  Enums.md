
# Arrays and Enums

Welcome to **Day 5**! Today, we’ll dive deep into **Arrays** and **Enums** in Java. Arrays are fundamental for storing multiple values in a single variable, while Enums help you work with predefined constants in an organized way.

---

## 🧠 Arrays

### 🔹 1. Single-Dimensional Arrays

An array is a collection of variables of the same type stored in a contiguous memory location. A **single-dimensional array** is like a list of items.

#### Declaration and Initialization:

```java
int[] numbers = {1, 2, 3, 4, 5};
System.out.println(numbers[0]);  // Accessing first element (prints 1)
```

- **Access elements** using an index (0-based).
- Arrays are fixed in size once created.

### 🔹 2. Multi-Dimensional Arrays

A **multi-dimensional array** can be thought of as an array of arrays. A common use case is for grids or matrices (e.g., 2D arrays for a table of values).

#### Example:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println(matrix[1][2]);  // Accesses element in 2nd row, 3rd column (prints 6)
```

- You can think of it like a table or a grid. 
- It allows you to store and manipulate data in a structured way.

### 🔹 3. Iteration Techniques

**Iterating** over arrays allows you to access and process each element.

#### Using `for` Loop:

```java
int[] numbers = {1, 2, 3, 4};
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);  // Prints each number in the array
}
```

#### Using `for-each` Loop:

```java
for (int num : numbers) {
    System.out.println(num);  // Prints each element using the enhanced for loop
}
```

- The **`for-each` loop** is simpler when you don’t need the index of the elements.

#### Using `Arrays.stream()` (Java 8+):

```java
Arrays.stream(numbers).forEach(System.out::println);  // Prints all elements using streams
```

- The **`Arrays.stream()`** method allows for functional-style operations on arrays (e.g., sorting, filtering).

---

### 🔹 4. Varargs (Variable Arguments)

Varargs (Variable Arguments) allows methods to accept a variable number of arguments. This is useful when you don’t know how many parameters will be passed.

#### Example:

```java
public static void printNumbers(int... numbers) {
    for (int num : numbers) {
        System.out.println(num);  // Prints each number passed to the method
    }
}
```

- **Usage**: Varargs can be used in methods where the number of arguments is not fixed, like the `System.out.println()` method in Java.

---

## 🔄 Practice Exercises on Arrays

1. **Create an array to store 10 integers** and print each one using a `for` loop.
2. **Create a 2D array (matrix)** to store multiplication tables. Print it in a table format.
3. **Reverse an array** (without using the built-in `reverse()` method).
4. **Find the largest and smallest element** in an array and print them.
5. **Create a method that accepts varargs** to print any number of integers passed to it.

---

## 🧠 Enums

### 🔹 1. What is an Enum?

An **enum** (short for "enumeration") is a special class in Java that represents a fixed set of constants. It helps to define variables that can only take a limited set of values.

#### Example:

```java
enum Days {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}
```

- **Enums are typesafe**, meaning only predefined values from the enum can be assigned to variables.

---

### 🔹 2. Enum Creation and Usage

Enums allow you to create a custom data type with a fixed set of possible values. You can use it just like any other type in your code.

#### Example:

```java
enum Color {
    RED, GREEN, BLUE
}

public class EnumExample {
    public static void main(String[] args) {
        Color color = Color.RED;
        System.out.println(color);  // Prints RED
    }
}
```

- Enums are useful for representing things like `Days`, `Months`, or `Seasons`.

---

### 🔹 3. Enum with Methods

Enums can also contain methods and fields, making them more powerful than just simple constants. You can add custom functionality within your enums.

#### Example with Methods:

```java
enum Month {
    JANUARY("January"), FEBRUARY("February"), MARCH("March");

    private final String monthName;

    Month(String monthName) {
        this.monthName = monthName;
    }

    public String getMonthName() {
        return monthName;
    }
}

public class EnumMethodExample {
    public static void main(String[] args) {
        System.out.println(Month.JANUARY.getMonthName());  // Prints January
    }
}
```

- Enums can contain constructors, fields, and methods.
- In this example, we have an enum `Month` with a method that returns the full month name.

---

## 🎯 Practice Exercises on Enums

1. **Create an enum for `TrafficLight`** with constants `RED`, `YELLOW`, and `GREEN` and print their meaning (e.g., "RED" means "Stop").
2. **Write a method to return the total number of days** in a given month using an enum (e.g., `JANUARY` has 31 days).
3. **Create an enum `BookGenre`** (e.g., `FICTION`, `NON_FICTION`, `SCIENCE_FICTION`) and implement a method to get a short description of each genre.

---

## 🧠 Summary

| Concept           | Explanation                                            | Example                                                   |
|-------------------|--------------------------------------------------------|-----------------------------------------------------------|
| **Array**         | A collection of elements, all of the same type         | `int[] numbers = {1, 2, 3};`                              |
| **Iteration**     | Looping over an array to access or process elements    | `for (int i = 0; i < numbers.length; i++) { ... }`        |
| **Varargs**       | Method accepts a variable number of arguments          | `public static void printNumbers(int... numbers)`         |
| **Enum**          | A special class to define a fixed set of constants     | `enum Days { MONDAY, TUESDAY, ... }`                       |
| **Enum Methods**  | Enums can have fields and methods for additional functionality | `Month.JANUARY.getMonthName()`                            |

---

📌 **Next Topic**: Object-Oriented Programming – Classes and Objects
```
