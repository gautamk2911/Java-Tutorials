
# 🗄️ Java Database Connectivity (JDBC)

The **Java Database Connectivity (JDBC)** API allows Java programs to connect to relational databases like MySQL, Oracle, and PostgreSQL.  
It enables you to execute SQL queries directly from Java applications for **CRUD** (Create, Read, Update, Delete) operations.

---

## 🧠 Overview
**JDBC (Java Database Connectivity)** is a standard API from the `java.sql` package.  
It provides a bridge between a **Java application** and a **database**.

```text
Java Application  →  JDBC API  →  JDBC Driver  →  Database
````

JDBC allows Java developers to:

* Connect to a database
* Send SQL queries
* Retrieve, update, or delete data

---

## 🗂️ Architecture

![JDBC Architecture](jdbc-architecture.png)

### 🔹 Components

| Component                         | Description                                     |
| --------------------------------- | ----------------------------------------------- |
| **DriverManager**                 | Manages database drivers and connections        |
| **Connection**                    | Represents an active connection to the database |
| **Statement / PreparedStatement** | Executes SQL queries                            |
| **ResultSet**                     | Stores query results                            |
| **SQLException**                  | Handles database errors                         |

---

## ⚙️ JDBC Classes

| Class / Interface   | Purpose                                    |
| ------------------- | ------------------------------------------ |
| `DriverManager`     | Establishes connection                     |
| `Connection`        | Represents the session between Java and DB |
| `Statement`         | Executes static SQL queries                |
| `PreparedStatement` | Executes parameterized queries             |
| `ResultSet`         | Holds the data returned by a query         |

---

## 🪜 Connection Steps

| Step | Description           | Example                                                          |
| ---- | --------------------- | ---------------------------------------------------------------- |
| 1️⃣  | Load the Driver Class | `Class.forName("com.mysql.cj.jdbc.Driver");`                     |
| 2️⃣  | Establish Connection  | `Connection con = DriverManager.getConnection(url, user, pass);` |
| 3️⃣  | Create Statement      | `Statement stmt = con.createStatement();`                        |
| 4️⃣  | Execute SQL Query     | `ResultSet rs = stmt.executeQuery("SELECT * FROM students");`    |
| 5️⃣  | Close Connection      | `con.close();`                                                   |

---

## 💻 Examples

### 1️⃣ **Select Query**

```java
import java.sql.*;

public class JdbcSelectDemo {
    public static void main(String[] args) {
        try {
            // Step 1: Load Driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Step 2: Connect
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/college", "root", "password");

            // Step 3: Create Statement
            Statement stmt = con.createStatement();

            // Step 4: Execute Query
            ResultSet rs = stmt.executeQuery("SELECT * FROM students");

            // Step 5: Process Result
            while (rs.next()) {
                System.out.println(rs.getInt(1) + " " + rs.getString(2));
            }

            con.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

### 2️⃣ **Insert / Update / Delete**

```java
import java.sql.*;

public class JdbcCrudDemo {
    public static void main(String[] args) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/college", "root", "password");

            Statement stmt = con.createStatement();

            // Insert
            stmt.executeUpdate("INSERT INTO students VALUES (4, 'Ravi')");

            // Update
            stmt.executeUpdate("UPDATE students SET name='Amit' WHERE id=4");

            // Delete
            stmt.executeUpdate("DELETE FROM students WHERE id=4");

            con.close();
            System.out.println("CRUD operations executed successfully!");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

### 3️⃣ **PreparedStatement**

```java
import java.sql.*;

public class JdbcPreparedDemo {
    public static void main(String[] args) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/college", "root", "password");

            String query = "INSERT INTO students (id, name) VALUES (?, ?)";
            PreparedStatement ps = con.prepareStatement(query);

            ps.setInt(1, 5);
            ps.setString(2, "Neha");
            ps.executeUpdate();

            con.close();
            System.out.println("Record inserted using PreparedStatement!");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

✅ **Advantages of PreparedStatement**

* Prevents SQL Injection
* Reusable and precompiled
* Supports parameters (`?` placeholders)

---

## 🧾 ResultSet Methods

| Method                          | Description              |
| ------------------------------- | ------------------------ |
| `next()`                        | Moves cursor to next row |
| `getInt(int columnIndex)`       | Returns integer value    |
| `getString(String columnLabel)` | Returns string value     |
| `close()`                       | Closes the ResultSet     |

---

## 🧮 Driver Types (for reference)

| Type       | Description                 | Example                                     |
| ---------- | --------------------------- | ------------------------------------------- |
| Type 1     | JDBC–ODBC Bridge (obsolete) | Old systems                                 |
| Type 2     | Native API                  | Oracle OCI                                  |
| Type 3     | Network Protocol Driver     | Middleware server                           |
| **Type 4** | **Thin Driver (Pure Java)** | ✅ Modern standard (e.g., MySQL Connector/J) |

---

## ⚡ Best Practices

* Always close `Connection`, `Statement`, and `ResultSet`.
* Prefer **PreparedStatement** over Statement.
* Use `try-with-resources` for auto-closing connections.
* Handle `SQLException` with detailed messages (`getMessage()`, `getErrorCode()`).
* Keep credentials outside source code (use config files).

---

## ✅ Sample Output

```
1 Amit
2 Karan
3 Riya
Record inserted using PreparedStatement!
```
