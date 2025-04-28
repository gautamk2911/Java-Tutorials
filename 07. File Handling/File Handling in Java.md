# 📚 Java File Handling

---

# 🔥 Introduction to File Handling

**File Handling** in Java means performing **create**, **read**, **update**, and **delete** operations on files and folders.

Java provides a rich set of **classes and methods** under the package **`java.io`** and **`java.nio.file`** to handle files easily.

---

# 📦 Key Classes for File Handling

| Class | Purpose |
|:------|:--------|
| `File` | Create, delete, check file or directory properties |
| `FileReader` | Reading data from a file (character by character) |
| `FileWriter` | Writing data to a file (character by character) |
| `BufferedReader` | Reading text efficiently (line by line) |
| `BufferedWriter` | Writing text efficiently |
| `PrintWriter` | Writing formatted text to file |
| `Scanner` | Reading file content easily |
| `Files` (java.nio) | Modern file operations (copy, move, delete) |

---

# 🛠️ Basic Operations with Files

---

## ✅ 1. Creating a New File

```java
import java.io.File;
import java.io.IOException;

public class CreateFileExample {
    public static void main(String[] args) {
        try {
            File file = new File("sample.txt");
            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            } else {
                System.out.println("File already exists.");
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

---

## ✅ 2. Writing to a File

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteFileExample {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("sample.txt");
            writer.write("Hello, Java File Handling!");
            writer.close();
            System.out.println("Successfully written to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

---

## ✅ 3. Reading from a File

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ReadFileExample {
    public static void main(String[] args) {
        try {
            File file = new File("sample.txt");
            Scanner reader = new Scanner(file);
            while (reader.hasNextLine()) {
                String data = reader.nextLine();
                System.out.println(data);
            }
            reader.close();
        } catch (FileNotFoundException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

---

## ✅ 4. Deleting a File

```java
import java.io.File;

public class DeleteFileExample {
    public static void main(String[] args) {
        File file = new File("sample.txt");
        if (file.delete()) {
            System.out.println("Deleted the file: " + file.getName());
        } else {
            System.out.println("Failed to delete the file.");
        }
    }
}
```

---

# 📈 Flowchart: Java File Handling

```plaintext
Start
  ↓
Create File / Open Existing File
  ↓
Perform Read / Write / Update / Delete
  ↓
Close file or resources
  ↓
End
```

---

# 🔥 BufferedReader and BufferedWriter Example

Buffered classes are faster because they read/write in bulk.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BufferedReaderExample {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("sample.txt"));
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

# 🛡️ Exception Handling in File Operations

Always use `try-catch-finally` or **try-with-resources** to avoid resource leakage!

✅ Example using try-with-resources:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class TryWithResourcesExample {
    public static void main(String[] args) {
        try (BufferedReader reader = new BufferedReader(new FileReader("sample.txt"))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

# 📚 File Methods You Must Know

| Method | Description |
|--------|-------------|
| `createNewFile()` | Creates a new empty file |
| `delete()` | Deletes a file |
| `exists()` | Checks if file exists |
| `getName()` | Returns name of file |
| `getAbsolutePath()` | Returns absolute path |
| `length()` | Returns file size |
| `mkdir()` | Creates directory |
| `list()` | Returns array of files/directories inside |

---

# 🧩 Small Tasks to Practice

- Create a new file and write a few lines into it.
- Read content from a file line by line.
- Copy content from one file to another.
- Count the number of words in a file.
- Create a directory and list all files inside.

---

# ⚡ Mini Project Idea

✅ Build a **Simple Student Record System**:  
Store student details (name, roll number) in a file.  
Provide options to Add / View / Delete student records!

---

# 🎯 Quick Summary Table

| Topic | Code/Use |
|------|---------|
| Create File | `File.createNewFile()` |
| Write to File | `FileWriter.write()` |
| Read File | `Scanner`, `BufferedReader` |
| Delete File | `File.delete()` |
| Best Practice | Use `try-with-resources` |

---

# 🌟 Final Tip

> "**In real-world projects, File Handling + Exception Handling always go together. Master this and you’ll build strong backend skills!**" 🚀

---
