# 💡 Working with Strings

## 📘 `String` Class, Immutability, and Common Methods

### 🔹 What is a String in Java?
- A `String` is a sequence of characters.
- In Java, strings are **objects** of the `String` class located in the `java.lang` package.
- Strings are **immutable** in Java, meaning once a `String` object is created, it cannot be changed.

```java
String name = "Alice";
name = name + " Johnson"; // creates a new string, doesn't modify the original
```

### 🔐 Why are Strings Immutable?
- For **security** and **thread safety**.
- Used in **hashing**, like in `HashMap` keys.
- Enables **string pooling** for memory efficiency.

### 📌 Creating Strings
```java
String str1 = "Hello";             // string literal
String str2 = new String("World"); // using constructor
```

### 🛠️ Common String Methods

| Method | Description |
|--------|-------------|
| `length()` | Returns the length of the string |
| `charAt(int index)` | Returns character at a specific index |
| `substring(int start, int end)` | Returns substring |
| `toUpperCase()` / `toLowerCase()` | Converts case |
| `indexOf(String s)` | Returns the index of a substring |
| `equals(String s)` | Compares strings (case-sensitive) |
| `equalsIgnoreCase(String s)` | Case-insensitive comparison |
| `contains(String s)` | Checks for presence of substring |
| `trim()` | Removes leading/trailing spaces |
| `replace(oldChar, newChar)` | Replaces characters |

### ✅ Example
```java
String s = "  Java Strings  ";
System.out.println(s.trim().toUpperCase()); // JAVA STRINGS
System.out.println("Length: " + s.length()); // includes spaces
```

---

## 📘 `StringBuilder` & `StringBuffer`

### 🧵 Why use `StringBuilder` or `StringBuffer`?
- When strings need to be **modified frequently**, prefer `StringBuilder` or `StringBuffer`.
- Both are **mutable**, meaning their content can be changed without creating new objects.

### 🔄 Difference between `String`, `StringBuilder`, and `StringBuffer`

| Feature | String | StringBuilder | StringBuffer |
|--------|--------|---------------|--------------|
| Mutability | Immutable | Mutable | Mutable |
| Thread-safe | Yes | No | Yes |
| Performance | Slow if many changes | Fast | Slower than `StringBuilder` |

---

### 🛠️ Common Methods for `StringBuilder` / `StringBuffer`

| Method | Description |
|--------|-------------|
| `append()` | Adds string to the end |
| `insert(index, str)` | Inserts string at position |
| `replace(start, end, str)` | Replaces characters in range |
| `delete(start, end)` | Deletes characters in range |
| `reverse()` | Reverses the sequence |

---

### 🔧 Example using StringBuilder
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb); // Hello World
sb.insert(6, "Java ");
System.out.println(sb); // Hello Java World
sb.reverse();
System.out.println(sb); // dlroW avaJ olleH
```

---

### 🧪 Practice Tip:
> Try converting a sentence to title case using `StringBuilder`. It’ll help you master character indexing and appending logic.

---

## 📚 Summary

- Use `String` for read-only, fixed content.
- Use `StringBuilder` for fast, single-threaded string modifications.
- Use `StringBuffer` when thread safety is important.

---

## ✅ Lab Practice Ideas

1. Write a program to reverse each word in a sentence using `StringBuilder`.
2. Compare performance of `String` vs `StringBuilder` in a loop of 10,000 iterations.
3. Create a method that replaces all vowels in a sentence using `StringBuffer`.

---
