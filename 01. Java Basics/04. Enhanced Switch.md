
## 🔄 Traditional vs Enhanced Switch

### 🔹 Traditional `switch` (what you're using):
```java
switch(month) {
    case 1:
        monthName = "January";
        break;
    case 2:
        monthName = "February";
        break;
    default:
        monthName = "Invalid";
}
```
- Needs **break** to avoid fall-through.
- Verbose and error-prone.

---

# ✅ Enhanced `switch` (Java 14+)

### 1. **Arrow syntax (`->`)** – cleaner and no need for `break`:
```java
String monthName = switch(month) {
    case 1 -> "January";
    case 2 -> "February";
    case 3 -> "March";
    default -> "Invalid";
};
```

- **No fall-through**.
- **Expression-based**: it **returns a value**, so you can directly assign it.

---

### 2. **Multiple values in a case**:
```java
String season = switch(month) {
    case 12, 1, 2 -> "Winter";
    case 3, 4, 5 -> "Spring";
    case 6, 7, 8 -> "Summer";
    case 9, 10, 11 -> "Autumn";
    default -> throw new IllegalArgumentException("Invalid month");
};
```

---

### 3. **`yield` keyword** for complex logic:
```java
String message = switch(month) {
    case 1, 2, 3 -> {
        String result = "Quarter 1";
        yield result;
    }
    default -> "Another Quarter";
};
```

- `yield` replaces `return` inside a switch **block**.

---

## ✨ Summary:
| Feature | Traditional Switch | Enhanced Switch |
|--------|---------------------|-----------------|
| Break needed | ✅ Yes | ❌ No |
| Fall-through | ✅ Yes | ❌ No |
| Can return values | ❌ No | ✅ Yes |
| Concise syntax | ❌ No | ✅ Yes |
| Multiple case values | ❌ No | ✅ Yes |
| Complex logic (with `yield`) | ❌ No | ✅ Yes |

---
