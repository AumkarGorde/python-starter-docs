**Created:** 2025-08-03

### Creation
- No type declaration is required.
- A variable is created when you first assign a value to it.
```
x = "omkar"
y = 28
```

### Assign Multiple Values
- Number of variables matches number of values
` x, y, z = "John", "Tony", "Thor" `

### Assign One Value To Multiple Variables
` x = y = z = "Tony" `

### Unpack a Collection
- Extract values into variables, if they are in list, tuple.
```
x, y, z = ["red", "orange", "black"]
```

### Global Variables
- Variables created outside the function are known as global variables
- Global variables are used inside and outside the function
```
x = "Won"

def match_status():
	print(f"India match status : {x}")

match_status()
```
```
Output:
India match status : Won
```
- A same name variable is inside the function, that will be a local variable and it will be used inside that function only.
- The global variable will remain as it is with the original value.
```
x = "Won"

def match_status():
	x = "Lost"
	print(f"India match status : {x}")

match_status()
print(f"India match status : {x}")
```
```
Output:
India match status : Lost
India match status : Won
```
- If you want to change the name of the global variable use the **global** keyword
```
x = "Won"

def match_status():
	global x
	x = "Lost"
	print(f"India match status : {x}")

match_status()
print(f"India match status : {x}")
```
```
Output:
India match status : Lost
India match status : Lost
```
- If global and local variables are same and you still want to use the global variable without changing it.
```
x = "Won"

def match_status():
	x = "Lost"
	print(f"India match status : {x}")
	print(f"India match status : {globals()['x']}")

match_status() --> India match status : Lost 
print(f"India match status : {x}") --> India match status : Lost
```
```
Output:
India match status : Lost
India match status : Won
India match status : Won
```
⚠️  Avoid naming same local and global variable names.

