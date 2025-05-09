# 🧵 Java Threads – Complete Guide

Threads in Java allow for **parallel execution** of two or more parts of a program, which can improve efficiency and responsiveness, especially in programs that perform many tasks at once (e.g., I/O operations, background computations).

---

## 🔸 What is a Thread?

- A **Thread** is a lightweight subprocess, the smallest unit of processing.
- Java supports multithreading, which allows concurrent execution of two or more threads.
- Each thread shares the same memory space but has its own execution stack.

---

## 🔹 Why Use Threads?

- Improve **application performance** on multi-core systems.
- Perform **background tasks** without freezing the UI (especially in GUIs).
- Efficient **use of system resources** for I/O operations.
- Handle **independent tasks** simultaneously (e.g., downloading and rendering).

---

## 🧪 Ways to Create a Thread

### 1. **Extending the `Thread` Class**
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running using Thread class.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); // start() creates a new thread and calls run()
    }
}
````

### 2. **Implementing the `Runnable` Interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread running using Runnable interface.");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

### ✅ Which is better?

> Prefer `Runnable` when you need to extend another class (since Java doesn't support multiple inheritance of classes).

---

## 🔁 Thread Lifecycle

```plaintext
NEW → RUNNABLE → RUNNING → BLOCKED → TERMINATED
```

| State           | Description                                          |
| --------------- | ---------------------------------------------------- |
| NEW             | Thread object created but not started                |
| RUNNABLE        | Thread is ready to run and waiting for CPU           |
| RUNNING         | Thread is actively executing                         |
| BLOCKED/WAITING | Thread is paused, waiting for monitor/another thread |
| TERMINATED      | Thread has completed execution                       |

---

## 🛠️ Important Thread Methods

| Method             | Purpose                                         |
| ------------------ | ----------------------------------------------- |
| `start()`          | Starts the thread, invokes `run()` internally   |
| `run()`            | Entry point for the thread's task               |
| `sleep(ms)`        | Pauses thread for specified time (milliseconds) |
| `join()`           | Waits for another thread to finish              |
| `isAlive()`        | Checks if thread is still running               |
| `setName(name)`    | Set thread name                                 |
| `getName()`        | Get thread name                                 |
| `setPriority(int)` | Set thread priority (1 to 10)                   |

---

## 🚦 Thread Example with Sleep and Join

```java
class MyThread extends Thread {
    public void run() {
        for (int i = 1; i <= 3; i++) {
            System.out.println(i + " from " + Thread.currentThread().getName());
            try {
                Thread.sleep(500); // 0.5 second
            } catch (InterruptedException e) {
                System.out.println("Interrupted!");
            }
        }
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();

        t1.start();
        t1.join(); // Wait for t1 to finish

        t2.start(); // Starts after t1 finishes
    }
}
```

---

## ⚠️ Thread Safety and Synchronization

### Race Condition:

When two threads access shared data and try to change it at the same time.

### Solution: `synchronized` keyword

```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}
```

---

## 💡 Thread Priorities

* Range: 1 (MIN\_PRIORITY) to 10 (MAX\_PRIORITY), default is 5.
* JVM may use this as a scheduling hint.

```java
t1.setPriority(Thread.MAX_PRIORITY);
t2.setPriority(Thread.MIN_PRIORITY);
```

---

## 📚 Real-Life Use Cases

* Web servers handling multiple requests.
* Background data processing (e.g., analytics, logging).
* Chat applications.
* Download managers.
* Game loops and animations.

---

## ✅ Quick Quiz

1. Can you start a thread by calling `run()` directly?
2. What does `join()` do?
3. What's the difference between `Thread` and `Runnable`?
4. What problem does synchronization solve?

---

## 🧪 Practice: Simple Thread Example

```java
class NumberPrinter extends Thread {
    public void run() {
        for(int i = 1; i <= 5; i++) {
            System.out.println(i + " - " + Thread.currentThread().getName());
        }
    }

    public static void main(String[] args) {
        NumberPrinter t1 = new NumberPrinter();
        NumberPrinter t2 = new NumberPrinter();
        t1.setName("Printer-1");
        t2.setName("Printer-2");
        t1.start();
        t2.start();
    }
}
```

---
