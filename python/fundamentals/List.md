# List
- List are the built in data type in python
- List are created using square brackets
```
fruits = ["apple", "banana", "oranges"]
print(fruits)
```
```
Output
['apple', 'banana', 'oranges']
```

- In python, lists are:
	- Ordered
	- Mutable (Changeable)
	- Allow Duplicates
```
# Create a list
my_list = ["apple", "banana", "cherry", "banana"]

# 1. Ordered: Items have a fixed order
print("First item:", my_list[0])

# 2. Changeable: You can modify items
my_list[1] = "blueberry"
print("Modified list:", my_list)

# 3. Allow duplicates: 'banana' appears twice
my_list[1] = "banana"
print("List with duplicates:", my_list)
```
```
Output
First item: apple
Modified list: ['apple', 'blueberry', 'cherry', 'banana']
List with duplicates: ['apple', 'banana', 'cherry', 'banana']
```

- In python you can only assign value to existing indices
```
# Create a list
my_list = ["apple", "banana", "cherry", "banana"]

# Try to add data to 4 index which not yet created
my_list[4] = "banana"
print("List with duplicates:", my_list)
```
```
Output:
IndexError: list assignment index out of range
```

### Important points on list 
- To know how many elements are in list use the len() function
```
my_list = ["apple", "banana", "cherry", "banana"]
print(len(my_list))
```
```
Output:
4
```
- List can items can be of any data types
```
l1 = ["apple", "banana", "cherry"]
l2 = [1, 5, 7, 9, 3]
```
- Python list can contain multiple data types (like string and integers together) `['apple', 'banana', 1, 'banana']`
- By default python lists are not type restricted - they are flexible and can contain any combination of data types
- To enforce type there are some options
	- Use custom wrapper or a validation logic
	- Use **Type Hints + Static Checker** (mypy, pyright)
		- ‼️ Type hints help **during development** but won't stop mixed types at runtime unless you add manual checks.
	```
	from typing import List
	
	def process_fruits(fruits: List[str])
		for fruit in fruits
			print(fruit.upper())

	process_fruits(["apple", "banana"]) --> OK
	process_fruits(["apple", 1])        --> Not Ok, my or pyright will flag this
	```
	- Use NumPy arrays for strict types - great for numeric operations (only for int , float or objects)
	```
	import numpy as np

	arr = np.array([1, 2, 3], dtype=int)
	print(arr)  --> Output: [1 2 3]
	
	```
	- Use Python 3.12+ **type** parameter in list. (still not enforced at runtime, but helps to catch type issues via tools)
```
def get_str_list() -> list[str]:
	return ["apple", "banana", "grapes"]

# -> list[str]
	# This is a return type hint which means the finction returns a list of strings
```

### Access Items From List
- Access via index: `my_list[1]`
- Access via negative index: `my_list[-1]`
- Access by specifying range: `my_list[2:5]`
```
my_list = ["Ironman", "Antman", "Spiderman", "Thor", "Hulk", "Black Widow", "Jarvis"]
print(my_list[1])
print(my_list[-1])
print(my_list[2:5])
print(my_list[:4])
print(my_list[2:])
print(my_list[-4:-1])

```
```
Output: 
Antman
Jarvis
['Spiderman', 'Thor', 'Hulk']
['Ironman', 'Antman', 'Spiderman', 'Thor']
['Spiderman', 'Thor', 'Hulk', 'Black Widow', 'Jarvis']
['Thor', 'Hulk', 'Black Widow']
```

### Check item in list
- Use **in** to check if present and **not in** for vice versa
```
my_list = ["Ironman", "Antman", "Spiderman", "Thor", "Hulk"]

if("Antman" in my_list):
	print("Antman is present")

if("Jarvis" not in my_list):
	print("Jarvis is not present")
	
```
```
Output:
Antman is present
Jarvis is not present
```

### Change Items From List
- Change of **single** value can be done by **index**
- Change of **multiple** values can be done by substituting it by giving range
- `insert()` function help to insert values at specific index without replacing existing values, it returns the inserted item.
```
my_list = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]

my_list[1] = "blackcurrant"
print(my_list)

my_list[1:3] = ["dog", "cat"]
print(my_list)

my_list[4:5] = ["fox", "sheep"]
print(my_list)

my_list[1:3] = ["tiger"] #replace [1] and [2] with "tiger"
print(my_list)

my_list.insert(2, "camel")
print(my_list)
```
```
Output:
['apple', 'blackcurrant', 'cherry', 'orange', 'kiwi', 'mango']
['apple', 'dog', 'cat', 'orange', 'kiwi', 'mango']
['apple', 'dog', 'cat', 'orange', 'fox', 'sheep', 'mango']
['apple', 'tiger', 'orange', 'fox', 'sheep', 'mango']
['apple', 'tiger', 'camel', 'orange', 'fox', 'sheep', 'mango']
```

### Append Items To List
- `append()` function adds the item to the end of the list
- `extend()` function appends element from another list to current list
	- `extend()` can append any iterable object
```
my_list = ["apple", "banana", "cherry"]

my_list.append("cat")
print(my_list)

my_list.insert(1,"camel")
print(my_list)

my_list_2 = ["Ironman", "Hulk"]
my_list.extend(my_list_2)
print(my_list)

```
```
['apple', 'banana', 'cherry', 'cat']
['apple', 'camel', 'banana', 'cherry', 'cat']
['apple', 'camel', 'banana', 'cherry', 'cat', 'Ironman', 'Hulk']
```
### Remove Items From List
- `remove()` function removes specified item
	- if there is more than one item (duplicates) it removes the first occurrence
- `pop()` used to remove a item at a specified index.
	- If no index is specified in `pop()` by default it removes the last item.
-  `del` keyword also removes the specified item
	- `del` keyword can also delete the list completely
- `clear()` method empties the list
```
my_list = ["apple", "banana", "cherry", "cat"]

my_list.remove("cat")
print(my_list)

my_list.pop(1)
print(my_list)

my_list_2 = ["Ironman", "Hulk", "Black Widow", "Thor"]
del my_list_2[2]
print(my_list_2)


my_list.clear()
print(my_list)

del my_list_2
print(my_list_2)

```
```
Output:
['apple', 'banana', 'cherry']
['apple', 'cherry']
['Ironman', 'Hulk', 'Thor']
[]

NameError: name 'my_list_2' is not defined.

```

### Looping in List
- Loop through a list using `for` loop
```
my_list = ["apple", "banana", "cherry", "cat"]

for x in my_list:
	print(x)
```
```
Output:
apple
banana
cherry
cat
```
- Loop through index number by using: `range() and len()`
```
my_list = ["apple", "banana", "cherry", "cat"]

for x in range(len(my_list)):
	print(my_list[x])
```
```
apple
banana
cherry
cat
```

### List Comprehension
- Provides a shorter syntax when you create a new list based on value of an existing list
	- Eg: get a new list of fruits that contains letter `a`
```
fruits = ["apple","banana","cherry","kiwi","mango"]
fruits_new = []

for fruit in fruits:
	if "a" in fruit:
		fruits_new.append(fruit)

print(fruits_new)
```
```
Output:
['apple', 'banana', 'mango']
```
- Now with list comprehension : `new_list = [expressoion for item in list if condition == True]`
```
fruits = ["apple","banana","cherry","kiwi","mango"]

fruits_new = [fruit for fruit in fruits if "a" in fruit]

print(fruits_new)
```
```
Output:
['apple', 'banana', 'mango']
```
- Few examples
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x.upper() for x in fruits]

print(newlist)
```
```
Output:
['APPLE', 'BANANA', 'CHERRY', 'KIWI', 'MANGO']
```
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = ['hello' for x in fruits]

print(newlist)

```
```
Output:
['hello', 'hello', 'hello', 'hello', 'hello']

```
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x if x != "banana" else "orange" for x in fruits]

print(newlist)

```
```
Output:
['apple', 'orange', 'cherry', 'kiwi', 'mango']
```

### Sorting In List
- `sort()` sorts everything in ascending order
- sort(reverse=True) sorts un descending order
```

```