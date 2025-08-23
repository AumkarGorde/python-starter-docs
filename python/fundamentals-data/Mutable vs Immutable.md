## **Mutable vs Immutable

### **1. Mutable**

* **Definition:** Objects whose **contents can be changed after creation**.
* **Key property:** You can **modify, add, or remove elements** without creating a new object.

**Common mutable types:**

| Type   | Example Operations                                 |
| ------ | -------------------------------------------------- |
| `list` | `append()`, `remove()`, change element `lst[0]=10` |
| `dict` | `d['key']=value`, `pop()`, `update()`              |
| `set`  | `add()`, `remove()`                                |

**Example:**

```python
lst = [1, 2, 3]
lst.append(4)    # lst becomes [1, 2, 3, 4]
lst[0] = 10      # lst becomes [10, 2, 3, 4]
```

---

### **2. Immutable**

* **Definition:** Objects whose **contents cannot be changed after creation**.
* **Key property:** Any operation that “changes” the value **creates a new object** instead.

**Common immutable types:**

| Type    | Example     |
| ------- | ----------- |
| `int`   | 5, 10       |
| `float` | 3.14        |
| `str`   | `"hello"`   |
| `tuple` | `(1, 2, 3)` |

**Example:**

```python
x = 5
x = x + 1  # x now points to a new int 6; original 5 is unchanged

s = "hello"
s = s + " world"  # s now points to a new string "hello world"
```

**Important:**

* Even if you reassign the variable (`x = x + 1`), the **original object** remains unchanged.
* Tuples and strings cannot be modified in place; you have to create a **new object** to “change” them.

---

### **Quick Tip for Dictionary Keys**

* **Keys must be immutable** (like tuple, string, int) because Python uses a **hash** of the key.
* Mutable objects like lists **cannot be dictionary keys**.

```python
res = {}
count = (1, 0, 2)  # tuple → valid key
res[count] = "value"
```