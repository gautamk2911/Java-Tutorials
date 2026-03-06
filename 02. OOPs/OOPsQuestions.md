
# OOP Coding Questions (Java)

## 1. Student Grade System (Encapsulation)

**Scenario:**
A school wants to maintain student records and automatically determine the student's grade based on their marks.

**Task:**
Create a `Student` class with the following private variables:

* `name`
* `marks`

Use **getter and setter methods** to access these variables.
Implement a method `calculateGrade()` that returns the grade based on the following criteria:

| Marks        | Grade |
| ------------ | ----- |
| 90 and above | A     |
| 75 – 89      | B     |
| 60 – 74      | C     |
| Below 60     | D     |

**Sample Input**

```
Enter Name: Rahul
Enter Marks: 82
```

**Sample Output**

```
Student: Rahul
Marks: 82
Grade: B
```

---

# 2. Bank Account System (Encapsulation + Methods)

**Scenario:**
A bank wants to implement a simple system where customers can deposit and withdraw money from their accounts.

**Task:**
Create a class `BankAccount` with the following attributes:

* `accountHolder`
* `balance`

Implement the following methods:

* `deposit(amount)`
* `withdraw(amount)`
* `displayBalance()`

**Rule:**
Withdrawal should not be allowed if the withdrawal amount exceeds the current balance.

**Sample Input**

```
Deposit: 5000
Withdraw: 2000
```

**Sample Output**

```
Balance after deposit: 5000
Balance after withdrawal: 3000
```

---

# 3. Employee Salary System (Inheritance)

**Scenario:**
A company employs two types of employees:

* Full-time employees
* Part-time employees

Each type has a different salary calculation method.

**Task:**

Create a base class `Employee` containing:

* `name`
* `calculateSalary()` method

Create two derived classes:

**FullTimeEmployee**

* `monthlySalary`

**PartTimeEmployee**

* `hoursWorked`
* `hourRate`

The salary for part-time employees is calculated as:

```
salary = hoursWorked × hourRate
```

**Sample Input**

```
Employee Type: PartTime
Hours Worked: 5
Rate per Hour: 200
```

**Sample Output**

```
Employee Salary: 1000
```

---

# 4. Shape Area Calculator (Polymorphism)

**Scenario:**
Create a program that calculates the area of different geometric shapes using polymorphism.

**Task:**

Create a base class `Shape` with a method:

```
area()
```

Create the following derived classes:

* `Circle`
* `Rectangle`
* `Triangle`

**Area Formulas**

| Shape     | Formula             |
| --------- | ------------------- |
| Circle    | π × r²              |
| Rectangle | length × width      |
| Triangle  | 0.5 × base × height |

**Sample Input**

```
Shape: Circle
Radius: 7
```

**Sample Output**

```
Area of Circle = 153.94
```

---

# 5. Vehicle Management System (Inheritance + Polymorphism)

**Scenario:**
A transport company manages multiple types of vehicles. Each vehicle starts differently.

**Task:**

Create a base class `Vehicle` with the following methods:

* `start()`
* `stop()`

Create derived classes:

* `Car`
* `Bike`
* `Truck`

Override the `start()` method in each class.

**Sample Output**

```
Car starts with key ignition
Bike starts with self-start
Truck starts with heavy engine ignition
```

---

# 6. Library Book System (Classes and Objects)

**Scenario:**
A library wants to store and display information about books.

**Task:**

Create a class `Book` with the following attributes:

* `title`
* `author`
* `price`

Create a method:

```
displayBook()
```

to display the book details.

**Sample Input**

```
Title: Java Programming
Author: James Gosling
Price: 500
```

**Sample Output**

```
Book Title: Java Programming
Author: James Gosling
Price: 500
```

---

# 7. Payment System (Interface + Polymorphism)

**Scenario:**
An online shopping platform supports multiple payment methods.

**Task:**

Create an interface:

```
Payment
```

with a method:

```
pay()
```

Implement the following classes:

* `CreditCardPayment`
* `UPIPayment`
* `CashPayment`

Each class should implement the `pay()` method.

**Sample Output**

```
Payment done using Credit Card
Payment done using UPI
Payment done using Cash
```

---

# 8. Online Shopping Cart (Aggregation)

**Scenario:**
A shopping cart can contain multiple products, and the system must calculate the total cart value.

**Task:**

Create class `Product` with:

* `name`
* `price`

Create class `Cart` with methods:

* `addProduct()`
* `calculateTotal()`

**Sample Input**

```
Product 1: Laptop 50000
Product 2: Mouse 500
```

**Sample Output**

```
Total Cart Value: 50500
```

---

# 9. Employee Bonus System (Abstract Class)

**Scenario:**
A company provides bonuses to different employees based on their roles.

**Task:**

Create an abstract class:

```
Employee
```

with an abstract method:

```
calculateBonus()
```

Create the following derived classes:

* `Manager`
* `Developer`
* `Intern`

Each class should implement its own bonus calculation.

**Sample Output**

```
Manager Bonus: 10000
Developer Bonus: 5000
Intern Bonus: 1000
```

---

# 10. ATM Simulation (Encapsulation + Methods)

**Scenario:**
Create a simple ATM system that allows users to deposit, withdraw, and check their balance.

**Task:**

Create a class `ATM` with:

* `balance`

Implement methods:

* `deposit(amount)`
* `withdraw(amount)`
* `checkBalance()`

**Sample Input**

```
Deposit: 10000
Withdraw: 3000
```

**Sample Output**

```
Remaining Balance: 7000
```

---

