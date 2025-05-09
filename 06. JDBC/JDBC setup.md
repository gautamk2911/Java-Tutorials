# Guide to Setup JDBC

### ✅ **Pre-requisites**

* **Java installed** (JDK 8 or above).
* **MySQL installed** and running on your system.
* **MySQL JDBC Connector** (`mysql-connector-java-X.X.X.jar`).
* (Optional) **MySQL Workbench** for GUI database management.

---

### 📦 **Download JDBC Connector**

* Go to: [https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/)
* Download the `.zip` file and extract it.
* Find the `.jar` file: `mysql-connector-java-8.0.xx.jar`.

---

### 🧩 **Add JDBC Connector to Project**

**If using Eclipse/IntelliJ:**

* Right-click project → *Build Path* → *Library* → *Add External JARs* → Select `.jar` file.

**If using terminal (CLI):**

* Compile:

  ```bash
  javac -cp .:mysql-connector-java-8.0.xx.jar YourFile.java
  ```
* Run:

  ```bash
  java -cp .:mysql-connector-java-8.0.xx.jar YourFile
  ```

> (Use `;` instead of `:` on Windows for classpath)

---

### 🗃️ **Basic Database Setup**

```sql
CREATE DATABASE sampledb;

USE sampledb;

CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100)
);
```

---

### 🔐 **Create a User (Optional)**

```sql
CREATE USER 'testuser'@'localhost' IDENTIFIED BY 'testpass';
GRANT ALL PRIVILEGES ON sampledb.* TO 'testuser'@'localhost';
FLUSH PRIVILEGES;
```

---

### 🔗 **Sample JDBC Connection Code**

```java
Connection conn = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/sampledb", "testuser", "testpass");
```

---

### 🚨 **Common Issues**

| Issue                        | Solution                           |
| ---------------------------- | ---------------------------------- |
| ClassNotFoundException       | JAR not added to classpath         |
| SQLException - Access denied | Wrong credentials or no privileges |
| Unknown database             | DB not created or wrong name       |
| Connection refused           | MySQL not running or wrong port    |

---
