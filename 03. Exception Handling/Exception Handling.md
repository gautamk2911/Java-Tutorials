# 📚 Java Exception Handling – Complete Notes with Examples

## 🎯 Objectives
- Understand exception hierarchy
- Handle errors using try-catch-finally
- Use multiple catch blocks and custom exceptions
- Apply throw and throws keywords
- Explore try-with-resources and assertions

---

## 🚨 What is an Exception?
An **exception** is an event that occurs during the execution of a program and disrupts the normal flow of instructions.

### 🔹 Categories:
- **Checked Exceptions**: Known to compiler (e.g., IOException, SQLException)
- **Unchecked Exceptions**: Occur at runtime (e.g., ArithmeticException, NullPointerException)

### 🔹 Java Exception Hierarchy
```
Throwable
 ├── Error (not meant to be caught)
 └── Exception
      ├── Checked Exceptions
      └── Unchecked Exceptions (RuntimeException)
```

---

## ✅ Try-Catch-Finally

### 📌 Syntax:
```java
try {
    // risky code
} catch (ExceptionType e) {
    // handle exception
} finally {
    // cleanup code (always runs)
}
```

### 💡 Example:
```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            System.out.println("Finally block executed.");
        }
    }
}
```

---

## 🔁 Multiple Catch Blocks

```java
public class MultipleCatch {
    public static void main(String[] args) {
        try {
            int[] arr = new int[2];
            arr[5] = 50;
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Exception");
        } catch (Exception e) {
            System.out.println("Generic Exception");
        }
    }
}
```

---

## 🛠 Custom Exception

### 🔸 Step 1: Create a custom class
```java
class AgeException extends Exception {
    public AgeException(String message) {
        super(message);
    }
}
```

### 🔸 Step 2: Use it in logic
```java
public class CustomExceptionDemo {
    static void checkAge(int age) throws AgeException {
        if (age < 18) {
            throw new AgeException("Not eligible to vote");
        }
        System.out.println("Eligible to vote");
    }

    public static void main(String[] args) {
        try {
            checkAge(16);
        } catch (AgeException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

---

## 💣 throw & throws

```java
public class ThrowThrowsDemo {
    static void validate(int marks) throws IllegalArgumentException {
        if (marks < 0) {
            throw new IllegalArgumentException("Marks cannot be negative");
        }
        System.out.println("Valid marks: " + marks);
    }

    public static void main(String[] args) {
        try {
            validate(-5);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

---

## 🧼 Try-with-Resources

```java
import java.io.*;

public class TryWithResourcesDemo {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {
            System.out.println(br.readLine());
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

> Automatically closes resources. No need for `finally` to close.

---

## ✅ Assertions

```java
public class AssertionDemo {
    public static void main(String[] args) {
        int age = -1;
        assert age > 0 : "Age must be positive";
        System.out.println("Age: " + age);
    }
}


---

## 📌 Summary Table
| Concept             | Use Case                                  |
|---------------------|--------------------------------------------|
| try-catch           | Catch runtime errors                       |
| finally             | Always execute cleanup code                |
| multiple catch      | Handle different error types               |
| custom exceptions   | Define domain-specific error conditions    |
| throw               | Throw an exception manually                |
| throws              | Declare possible exceptions in a method    |
| try-with-resources  | Auto-close I/O resources                   |
| assert              | Developer-level condition check            |

---

## 🧪 Practice Tasks

1. Write a program to handle divide-by-zero error.
2. Create a method that throws a custom exception when a number is negative.
3. Read a file using try-with-resources and handle exceptions.
4. Use assertions to ensure a positive number input.

---

> "Exception handling makes code more robust, secure, and user-friendly."
