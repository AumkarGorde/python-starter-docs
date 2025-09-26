# Dictionary
- Store data value in key:value pairs
- It is a collection which is `ordered📝, changeable and do not allow duplicates`
📝 Python 3.7, dict are ordered. In Python 3.6 and earlier, they were unordered
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}
```
- Python does not gives error if a key is present twice or more times rather it quietly overwrites the previous value for that key with the most recent one
```
my_dict = {
    "key": "value1",
    "key": "value2"  # This will overwrite the previous one
}
```
-  Values in dictionary items can be of any data type
```
thisdict = {  
  "brand": "Ford",  
  "electric": False,  
  "year": 1964,  
  "colors": ["red", "white", "blue"]  
}
```

### Access Items In Dictionary
- Items in the dictionary are accessed by refering the key name in square brackets
- `get()` method will also give the same result
	- `x = my_dict.get("model")`
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}
print(my_dict["model"])
```
```
Output:
Avenger
```
- `keys()` method will return all the keys in dictionary
	- `x = my_dict.keys()`
- `values()` method will return all the values in dictionary
- Add a new item to dictionary or update a new item in dictionary is done in the same way
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}

my_dict["model"] = "Pulsar"
print(my_dict)

my_dict["speed"] = 120
print(my_dict)
```
```
Output:
{'brand': 'Bajaj', 'model': 'Pulsar', 'year': 2001}
{'brand': 'Bajaj', 'model': 'Pulsar', 'year': 2001, 'speed': 120}
```
- `items()` method will return each item in a dictionary as a tuple in a list
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}

print(my_dict.items())
```
```
Output:
dict_items([('brand', 'Bajaj'), ('model', 'Avenger'), ('year', 2001)])
```
- We can check if a key exsists in the dictionary by using `in` keyword
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}

if "year" in my_dict:
	print("Year is present")
```
```
Output:
Year is present
```
- `update()` method will update the dictionary with the items from the given argument, provided the argument must be a dictionary or an iterable with key:value pair
- `update()` method will add the item if not exist in dict.
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}
my_dict.update({"year":2012})
print(my_dict)
```
```
Output:
{'brand': 'Bajaj', 'model': 'Avenger', 'year': 2012}
```

### Remove Item From Dictionary
- `pop()` method removes the item with the specified key name
	- `my_dict.pop("model")`
- `popitem()` will remove the last inserted element (in version 3.7 and before random item is removed)
- `del` keyword removes the item with the specified key name
```
my_dict = {
	"brand":"Bajaj",
	"model":"Avenger",
	"year":2001
}
my_dict.update({"year":2012})
print(my_dict)
```
```
Output:
{'brand': 'Ford', 'year': 1964}
```
- `del` keyword can also delete the complete dictionary
- `clear()` method empties the dictionary
```
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
thisdict.clear()
print(thisdict)
```
```
Output:
{}
```

### Loops In Dictionary
- By default looping a dict will only gives keys
- To get values we need to fetch key inside the for loop like this : `my_dict[x]` where x is a key
	- or we can do `for x in my_dict.values()`
- We can loop both keys and values by using `items()` method
```
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
for x, y in thisdict.items():
  print(x, y)
```
```
Output:
brand Ford  
model Mustang  
year 1964
```

### Copy Dictionary
- `copy()` is used to copy a dictionary to a new dictionary
- For dict we cannot do my_dict = my_dict_old, as this is referecr to old dict and changes in old dict will also change new dict
- `dict()` method can also be used to create a new copy

### Nested Dictionary
- A dictionary can contain another dictionary


## Get
```
dict.get('a',19)
Gets the value from the dictionary if not present it returns 19
```