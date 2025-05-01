
# Java Collections: Null and Duplicate Values Support

| Collection Type   | Allows Null Values | Allows Duplicate Values | Allows Multiple Nulls |
|-------------------|--------------------|--------------------------|------------------------|
| `ArrayList`       | ✅ Yes              | ✅ Yes                   | ✅ Yes                 |
| `LinkedList`      | ✅ Yes              | ✅ Yes                   | ✅ Yes                 |
| `Vector`          | ✅ Yes              | ✅ Yes                   | ✅ Yes                 |
| `Stack`           | ✅ Yes              | ✅ Yes                   | ✅ Yes                 |
| `HashSet`         | ✅ Yes              | ❌ No                    | ❌ Only one null       |
| `LinkedHashSet`   | ✅ Yes              | ❌ No                    | ❌ Only one null       |
| `TreeSet`         | ❌ No (throws NPE)  | ❌ No                    | ❌ No                  |
| `PriorityQueue`   | ❌ No (throws NPE)  | ✅ Yes                   | ❌ No nulls allowed    |
| `ArrayDeque`      | ❌ No (throws NPE)  | ✅ Yes                   | ❌ No nulls allowed    |
| `HashMap`         | ✅ Yes (1 null key) | ✅ Yes (values)          | ✅ Multiple null values|
| `LinkedHashMap`   | ✅ Yes (1 null key) | ✅ Yes (values)          | ✅ Multiple null values|
| `TreeMap`         | ❌ No (throws NPE)  | ✅ Yes (values)          | ✅ Multiple null values|


---

### ✅ Explanation:

- **Null Values**: Refers to whether the data structure allows inserting `null` entries.
- **Duplicate Values**: If the structure can hold the same value more than once.
- **Multiple Nulls**: Specifically, whether more than one `null` can be stored (e.g., multiple `null` elements in a list, or multiple `null` values in a map).

---
