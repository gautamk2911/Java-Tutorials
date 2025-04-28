# 📚 Java Collections Framework (JCF) 

---

# 🔥 What is Java Collections Framework?

The **Java Collections Framework (JCF)** is a **set of classes and interfaces** that implement commonly reusable **data structures** such as:

- Lists
- Sets
- Queues
- Maps

✅ It **reduces programming effort**, **increases performance**, and **provides easy-to-use interfaces** for managing groups of objects.

---

# 📦 Key Interfaces of JCF

| Interface | Description | Example Classes |
|:----------|:------------|:----------------|
| List | Ordered collection, duplicates allowed | `ArrayList`, `LinkedList` |
| Set | Unordered collection, no duplicates | `HashSet`, `TreeSet` |
| Queue | Elements processed in FIFO order | `PriorityQueue`, `ArrayDeque` |
| Map | Key-Value pairs, unique keys | `HashMap`, `TreeMap` |

---

# 🔹 Important Classes Overview

| Class | Description |
|-------|-------------|
| `ArrayList` | Dynamic array; fast access, slow inserts/removals |
| `LinkedList` | Doubly linked list; good for frequent insertions/deletions |
| `HashSet` | Stores unique elements, no order |
| `TreeSet` | Stores unique elements in sorted order |
| `HashMap` | Key-value storage, no ordering |
| `TreeMap` | Key-value storage, sorted by key |

---

# 🛠 Basic Code Examples

---

### ✅ List Example: `ArrayList`

```java
import java.util.ArrayList;

public class ListExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        list.add("C++");

        for (String lang : list) {
            System.out.println(lang);
        }
    }
}
```

---

### ✅ Set Example: `HashSet`

```java
import java.util.HashSet;

public class SetExample {
    public static void main(String[] args) {
        HashSet<Integer> set = new HashSet<>();
        set.add(10);
        set.add(20);
        set.add(10); // Duplicate not added

        for (Integer num : set) {
            System.out.println(num);
        }
    }
}
```

---

### ✅ Map Example: `HashMap`

```java
import java.util.HashMap;

public class MapExample {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Cherry");

        for (Integer key : map.keySet()) {
            System.out.println(key + " => " + map.get(key));
        }
    }
}
```

---

# 🧠 Why Use Collections?

- Dynamic in size (no need to know size at compile time)
- Built-in data manipulation methods (`sort`, `search`, `iterate`)
- Type safety with **Generics**
- Efficient performance

---

# 📈 Collections Hierarchy Diagram

```plaintext
              Collection
                  |
      ---------------------------
      |            |             |
     List         Set          Queue
      |            |             |
ArrayList    HashSet/TreeSet  PriorityQueue
LinkedList
Vector
Stack
```

---

# 🧩 Features of Java Collections Framework

✅ Ready-to-use implementations  
✅ Polymorphic (you can use interfaces for flexibility)  
✅ Algorithms like sorting, searching  
✅ Thread-safe collections available (`Collections.synchronizedList`)  

---

# 🚀 Java Collections Utility Class: `Collections`

The `Collections` class provides **static methods** like:

```java
import java.util.ArrayList;
import java.util.Collections;

public class CollectionsExample {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(2);
        list.add(8);

        Collections.sort(list); // Sort the list

        System.out.println(list);
    }
}
```

---

# 🛑 Differences at a Glance

| Feature | List | Set | Map |
|---------|-----|-----|-----|
| Duplicates | Allowed | Not Allowed | Keys Unique |
| Ordering | Maintained | Not Guaranteed (HashSet) | Depends on Implementation |
| Example | `ArrayList` | `HashSet` | `HashMap` |

---

# 📚 Real-World Use Cases

| Scenario | Collection Used |
|----------|-----------------|
| To-do list app | `ArrayList` |
| Attendance (no duplicates) | `HashSet` |
| Word meaning dictionary | `HashMap` |
| Priority task scheduler | `PriorityQueue` |

---

# 📝 Quick Summary Table

| Topic | Details |
|------|---------|
| List | Ordered, allows duplicates |
| Set | Unique elements only |
| Map | Key-Value pairs |
| ArrayList | Resizable array |
| HashSet | Fast unordered set |
| HashMap | Fast key-value store |

---

# 🎯 Pro Tip:

> "**Always prefer interfaces (`List`, `Set`, `Map`) over implementation classes (`ArrayList`, `HashSet`, `HashMap`) when declaring variables!**"  
>  
> This makes your code more flexible for changes in the future!

---

# 🛠️ Small Practice Tasks:

✅ Create a `List` of student names and sort them.  
✅ Create a `Set` of roll numbers to avoid duplicates.  
✅ Create a `Map` of employee ID and employee name.

---

# 🛡️ Final Mindset

- Collections are the heart of Java programming.
- Master **List**, **Set**, **Map** first — then move to **advanced topics** (Queues, Deques, Navigable Maps).
- Practice is key! 🔥

---
