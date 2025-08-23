
### 1. **Regular `dict`**

* Standard dictionary in Python.
* Accessing a key that does **not exist** will raise a `KeyError`.
* You need to manually check for a key or initialize it.

```python
# Regular dict example
d = {}

# Adding a key-value
d['a'] = 1

# Accessing an existing key
print(d['a'])  # Output: 1

# Accessing a missing key
# print(d['b'])  # KeyError!
```

* To avoid `KeyError`, you can do this:

```python
if 'b' not in d:
    d['b'] = 0
d['b'] += 1
```

---

### 2. **`defaultdict`**

* Comes from `collections` module.
* Automatically **initialises a missing key** with a default value (given by a function like `int`, `list`, or `set`).
* Very handy for counting, grouping, or building nested structures.

```python
from collections import defaultdict

# defaultdict with int
dd = defaultdict(int)

dd['a'] += 1  # 'a' was not there, automatically initialized to 0, then incremented
print(dd['a'])  # Output: 1

# defaultdict with list
dd_list = defaultdict(list)
dd_list['fruits'].append('apple')  # 'fruits' initialized as empty list
print(dd_list['fruits'])  # Output: ['apple']
```

---

### 3. **Key Differences**

| Feature            | `dict`            | `defaultdict`                    |
| ------------------ | ----------------- | -------------------------------- |
| Missing key access | Raises `KeyError` | Creates key with default value   |
| Initialization     | Manual            | Automatic via factory function   |
| Use cases          | General mapping   | Counting, grouping, nested dicts |

---

✅ **Summary:**
Use `dict` for general-purpose key-value storage. Use `defaultdict` when you want to **avoid `KeyError`** and automatically initialise missing keys (common in counting or grouping tasks).

