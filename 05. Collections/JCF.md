
# 📚 Java Collections Framework (JCF) 

---

## 🧭 Collections Hierarchy Diagram

![Java Collections Hierarchy](collections-hierarchy.png)
Source: Starter Tutorials

---

## 🔑 Core Interfaces and Their Descriptions

| Interface | Description |
|-----------|-------------|
| **Collection** | The root interface representing a group of objects, known as elements. |
| **List** | An ordered collection that can contain duplicate elements. |
| **Set** | A collection that cannot contain duplicate elements. |
| **Queue** | A collection designed for holding elements prior to processing. |
| **Deque** | A double-ended queue that allows insertion and removal at both ends. |
| **Map** | An object that maps keys to values; cannot contain duplicate keys. |

---

## 📦 Key Classes and Their Descriptions

| Class | Implements | Description |
|-------|------------|-------------|
| **ArrayList** | List | Resizable-array implementation of the List interface. |
| **LinkedList** | List, Deque | Doubly-linked list implementation of the List and Deque interfaces. |
| **Stack** | List | Last-in, first-out stack of objects. |
| **Queue** | Queue | Interface for a queue data structure. |
| **PriorityQueue** | Queue | Priority queue based on a priority heap. |
| **HashMap** | Map | Hash table-based implementation of the Map interface. |
| **HashSet** | Set | Hash table-based implementation of the Set interface. |
| **TreeSet** | NavigableSet | Tree-based implementation of the NavigableSet interface. |
| **Deque** | Deque | Double-ended queue supporting element insertion and removal at both ends. |

---

## 🛠️ Method Summary Tables for Key Data Structures

### 📋 ArrayList

| Method | Description |
|--------|-------------|
| `add(E e)` | Appends the specified element to the end of this list. |
| `add(int index, E element)` | Inserts the specified element at the specified position. |
| `get(int index)` | Returns the element at the specified position. |
| `set(int index, E element)` | Replaces the element at the specified position. |
| `remove(int index)` | Removes the element at the specified position. |
| `size()` | Returns the number of elements in the list. |
| `clear()` | Removes all elements from the list. |
| `contains(Object o)` | Returns true if the list contains the specified element. |

### 🔗 LinkedList

| Method | Description |
|--------|-------------|
| `addFirst(E e)` | Inserts the specified element at the beginning. |
| `addLast(E e)` | Appends the specified element to the end. |
| `removeFirst()` | Removes and returns the first element. |
| `removeLast()` | Removes and returns the last element. |
| `getFirst()` | Returns the first element. |
| `getLast()` | Returns the last element. |
| `offer(E e)` | Adds the specified element as the tail. |
| `poll()` | Retrieves and removes the head of the list. |

### 🧱 Stack

| Method | Description |
|--------|-------------|
| `push(E item)` | Pushes an item onto the top of the stack. |
| `pop()` | Removes and returns the top item of the stack. |
| `peek()` | Looks at the top item without removing it. |
| `isEmpty()` | Tests if the stack is empty. |
| `search(Object o)` | Returns the 1-based position from the top of the stack. |

### 📬 Queue

| Method | Description |
|--------|-------------|
| `add(E e)` | Inserts the specified element into the queue. |
| `offer(E e)` | Inserts the specified element, returning false if full. |
| `remove()` | Retrieves and removes the head of the queue. |
| `poll()` | Retrieves and removes the head, or returns null if empty. |
| `element()` | Retrieves, but does not remove, the head. |
| `peek()` | Retrieves, but does not remove, the head, or returns null if empty. |

### 🎯 PriorityQueue

| Method | Description |
|--------|-------------|
| `add(E e)` | Inserts the specified element into the priority queue. |
| `offer(E e)` | Inserts the specified element, returning false if full. |
| `poll()` | Retrieves and removes the head of the queue. |
| `peek()` | Retrieves, but does not remove, the head. |
| `remove(Object o)` | Removes a single instance of the specified element. |
| `contains(Object o)` | Returns true if the queue contains the specified element. |

### 🗺️ HashMap

| Method | Description |
|--------|-------------|
| `put(K key, V value)` | Associates the specified value with the specified key. |
| `get(Object key)` | Returns the value to which the specified key is mapped. |
| `remove(Object key)` | Removes the mapping for the specified key. |
| `containsKey(Object key)` | Returns true if the map contains the specified key. |
| `containsValue(Object value)` | Returns true if the map maps one or more keys to the specified value. |
| `keySet()` | Returns a Set view of the keys. |
| `values()` | Returns a Collection view of the values. |
| `entrySet()` | Returns a Set view of the mappings. |

### 🔒 HashSet

| Method | Description |
|--------|-------------|
| `add(E e)` | Adds the specified element to the set if not already present. |
| `remove(Object o)` | Removes the specified element from the set. |
| `contains(Object o)` | Returns true if the set contains the specified element. |
| `size()` | Returns the number of elements in the set. |
| `clear()` | Removes all elements from the set. |
| `isEmpty()` | Returns true if the set contains no elements. |

### 🌲 TreeSet

| Method | Description |
|--------|-------------|
| `add(E e)` | Adds the specified element to the set. |
| `remove(Object o)` | Removes the specified element from the set. |
| `first()` | Returns the first (lowest) element. |
| `last()` | Returns the last (highest) element. |
| `ceiling(E e)` | Returns the least element greater than or equal to the given element. |
| `floor(E e)` | Returns the greatest element less than or equal to the given element. |
| `higher(E e)` | Returns the least element strictly greater than the given element. |
| `lower(E e)` | Returns the greatest element strictly less than the given element. |

### 🔄 Deque

| Method | Description |
|--------|-------------|
| `addFirst(E e)` | Inserts the specified element at the front. |
| `addLast(E e)` | Inserts the specified element at the end. |
| `removeFirst()` | Removes and returns the first element. |
| `removeLast()` | Removes and returns the last element. |
| `peekFirst()` | Retrieves, but does not remove, the first element. |
| `peekLast()` | Retrieves, but does not remove, the last element. |
| `offerFirst(E e)` | Inserts the specified element at the front. |
| `offerLast(E e)` | Inserts the specified element at the end. |

---

## 📘 Summary

- **List**: Ordered collection (e.g., `ArrayList`, `LinkedList`).
- **Set**: Unordered collection with no duplicates (e.g., `HashSet`, `TreeSet`).
- **Queue**: FIFO structure (e.g., `Queue`, `PriorityQueue`).
- **Deque**: Double-ended queue (e.g., `Deque`, `LinkedList`).
- **Map**: Key-value pairs (e.g., `HashMap`).

---
