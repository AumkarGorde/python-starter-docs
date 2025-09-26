# Sets
- Used to store multiple items in single variable
- It is a collection which is `unordered, unchangeable📝, and unindex`
	- Set items can appear in a different order every time you use them, and cannot be referred to by index or key.
- Sets cannot have two items with same values, duplicates are not allowed
- True and 1 are considered the same value
- False and 0 are considered the same value
📝 Sets items are unchangeable, but you can remove items and add new items.
- Sets use `{}`

### Access Items
- You cannot access the item by refering to an index or key
- But you can loop through a set, usinf the `in` keyword

### Add Item To Set
- Once set is created you cannot change its existing items, but you can add new items
- `add()` method is used to add item to set
	- `update()` method is used to add items form another set into current set.
	- `update()` method not only support set but any iterable like - tuple , list, dict 
```
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print(thisset)

tropical = {"pineapple", "mango", "papaya"}
thisset.update(tropical)
print(thisset)

mylist = ["cat", "dog"]
thisset.update(mylist)
print(thisset)
```
```
{'cherry', 'orange', 'apple', 'banana'}
{'apple', 'banana', 'mango', 'orange', 'papaya', 'cherry', 'pineapple'}
{'apple', 'cat', 'orange', 'papaya', 'dog', 'pineapple', 'banana', 'mango', 'cherry'}
```

### Remove Items In Set
- `remove()` method is used to remove item from set
	- `my_set.remove('dog')`
	- If item is not present in set and if try to remove it will raise an **error**
- `discard()` method is used to remove/discard item from set
	- my_set.discard('dog')
	- If item is not present in set and if try to remove it will **NOT** raise an **error**
- `pop()` method can also be used to remove items from set, but you cannot be sure which item is removed. This is because set are unordered
- `clear()` method empties the set
	- `my_set.clear()`
- `del` keyword will delete the set completely

### Loops in Set
-  Looping is same as of other collection using the `in` keyword
```
unique = set()
for item in unique:
	print(item)
```

### Check values in set 
```
item = 'abc'
unique = set()
if item in unique:
	print('Item exists')
```
### Joins In Set
- `union() or | `
- `update()`
- `intersection() or &`
- `intersection_update()`
- `difference() or -`
- `difference_update()`
- `symmetric_difference() or ^`
- `symmetric_difference_update()`
