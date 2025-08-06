# Tuples
- Tuples are used to store multiple items in a single variable
- Tuples allows duplicate values
- Tuple is ordered and unchangeable (immutable)
	- Ordered - Elements stay in the same order as inserted
	- Unchangeable - You cannot change, add or remove elements
		- `my_tuple[0] = 10` -> this is not allowed

### Access Tuple Items
- Tuple can be accessed by refering the index
- Negative indexing work with tuple
```
my_tuple = ("apple", "banana", "cherry", "cat", "lion")

print(my_tuple[1])
print(my_tuple[-1])
print(my_tuple[1:4])
```
```
Output:
banana
lion
('banana', 'cherry', 'cat')
```

### Updates in Tuple
- Tuples are immutable or unchangeable 
- You cannot directly update the tuple, in an indirect way you need to convert that tuple to a list do the updates and then again convert to tuple
- You cannot delete an item in tuple
- You can delete the tuple completely by using `del` keyword
- We can add tuple to tuple
	- `tuple_1 += tuple_2`

### Unpack Tuple
- Unpacking refers to extract values from tuple to variable
```
animals = ("tiger","deer","fox")

(a1,a2,a3) = animals

print(a1)
print(a2)
print(a3)
```
```
Output:
tiger
deer
fox
```
- `Use of *` if number of variable are less at unpacking the rest of the variable is assigned to variable marked with `*`
```
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")

(green, yellow, *red) = fruits

print(green)
print(yellow)
print(red)
```
```
Output:
apple
banana
['cherry', 'strawberry', 'raspberry']
```
```
fruits = ("apple", "mango", "papaya", "pineapple", "cherry")

(green, *tropic, red, black) = fruits

print(green)
print(tropic)
print(red)
print(black)
```
```
apple
['mango', 'papaya']
pineapple
cherry
```

### Looping
- Looping in tuple is same as looping in list

### Join in Tuple
- We can join tuple by using `+`
	- tup = tup_1 + tup_2
### Multiply In Tuple
```
fruits = ("apple", "banana", "cherry")
mytuple = fruits * 2
print(mytuple)

num = (2,3,4)
mul_num = num * 2
print(mul_num)

```
```
Output:
('apple', 'banana', 'cherry', 'apple', 'banana', 'cherry')
(2, 3, 4, 2, 3, 4)
```

### Tuple Methods
- `count()` Returns number of times a specific value is present in tuple
	- `v1 = my_tup.count(2)`
- `index()` Returns the first occurence in tuple and return its position
	- x = my_tup.index(3)


📝 When creating a tuple with only one item, remember to include a comma after the item, otherwise it will not be identified as a tuple.


