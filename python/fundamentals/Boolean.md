# Boolean 
Boolean represents two values
- True
- False
*True and False - both have T and F capital, python does not support true and false*

###  Evaluate Values and Variables
- bool() method helps us to evaluate any value and give True or False
```
print(bool(True))
print(bool(12))
print(bool("Hi"))
print(bool(("apple","orange")))
print(bool(["apple", "cherry", "banana"]))
print(bool({"Name":"Luke", "age": 28}))
print("----------------")
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(""))
print(bool(()))
print(bool([]))
print(bool({}))
```
```
Output:
True
True
True
True
True
True
----------------
False
False
False
False
False
False
False
```