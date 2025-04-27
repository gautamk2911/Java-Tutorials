# 🔗 JDBC (Java Database Connectivity) - Workshop Notes

---

# 📚 Introduction to JDBC

**JDBC** (Java Database Connectivity) is a **Java API** to connect and interact with databases (like MySQL, Oracle, PostgreSQL).

It allows Java applications to:
- Send SQL queries
- Retrieve data from database
- Insert, update, delete records
- Manage database transactions

---

# 🛠️ Basic JDBC Architecture

```plaintext
Java Application
      ↓
JDBC API
      ↓
JDBC Driver Manager
      ↓
Database-Specific Driver
      ↓
Database
```

✅ JDBC acts like a **bridge** between Java programs and the Database.

---

# 🔹 Steps to Connect Java with Database using JDBC

1. **Import JDBC packages**
2. **Register the Driver**
3. **Create a Connection**
4. **Create a Statement**
5. **Execute SQL Query**
6. **Process the Results**
7. **Close the Connection**

---

# 🧩 Code Example: Connecting to MySQL

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class JDBCExample {
    public static void main(String[] args) {
        try {
            // 1. Load and register driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // 2. Create connection
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/testdb", "root", "password");

            // 3. Create statement
            Statement stmt = con.createStatement();

            // 4. Execute query
            ResultSet rs = stmt.executeQuery("SELECT * FROM students");

            // 5. Process results
            while (rs.next()) {
                System.out.println(rs.getInt(1) + " " + rs.getString(2));
            }

            // 6. Close connection
            con.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

# 🛠️ Important JDBC Classes/Interfaces

| Class/Interface | Purpose |
|-----------------|---------|
| DriverManager   | Manages database drivers |
| Connection      | Establishes connection with DB |
| Statement       | Executes simple SQL queries |
| PreparedStatement | Executes pre-compiled queries |
| ResultSet       | Holds data retrieved from DB |
| SQLException    | Handles database errors |

---

# 🔹 PreparedStatement (Prevent SQL Injection)

Better, safer than `Statement`. Helps prevent SQL Injection.

```java
PreparedStatement pstmt = con.prepareStatement("INSERT INTO students VALUES(?, ?)");
pstmt.setInt(1, 101);
pstmt.setString(2, "John");
pstmt.executeUpdate();
```

✅ Parameters (`?`) are filled dynamically.

---

# 🔹 JDBC Driver Types

| Driver Type | Description |
|-------------|-------------|
| Type 1 | JDBC-ODBC Bridge |
| Type 2 | Native API Driver |
| Type 3 | Network Protocol Driver |
| Type 4 | Thin Driver (Pure Java, best choice) |

➡️ **Type 4** Driver is most common today (`com.mysql.cj.jdbc.Driver`).

---

# 📈 JDBC Flowchart

```plaintext
Start
  ↓
Load Driver
  ↓
Establish Connection
  ↓
Create Statement/PreparedStatement
  ↓
Execute Query (SQL)
  ↓
Process ResultSet
  ↓
Close Connection
  ↓
End
```

---

# ⚡ Mini Lab Practice Ideas

| Task | Challenge |
|-----|------------|
| Create a table "Employees" |
| Insert multiple employee records |
| Retrieve all employee details |
| Update employee salary |
| Delete an employee by ID |

---

# 🛑 Common JDBC Errors and Solutions

| Error | Cause | Solution |
|------|------|---------|
| `ClassNotFoundException` | JDBC Driver not found | Add driver jar to project |
| `SQLException` | Wrong SQL syntax or DB issues | Check query carefully |
| `Access Denied` | Wrong DB username/password | Check credentials |

---

# 📝 Quick Summary

| Key Concept | Short Description |
|-------------|--------------------|
| JDBC | Java API for DB operations |
| DriverManager | Connects Java and DB |
| Statement | Executes simple queries |
| PreparedStatement | Executes secure queries |
| ResultSet | Handles query results |

---

# 🚀 Final Tip

> "**Mastering JDBC is your first big step toward understanding full-stack backend development!**"  
>  
> 🌟 Always close the Connection, Statement, and ResultSet in `finally` block or use **try-with-resources**!

---
