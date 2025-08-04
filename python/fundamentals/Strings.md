String array of elements which are also a string.  (One character is also termed as string with length 1)
```
b = "Hello World"
print(type(b))
 print(type(b[2]))
```
```
Output:
<class 'str'>
<class 'str'>
```

### Looping
```
for x in "tiger"
	print(x)
```

### Length
```
x = "Antartica"
print(len(x))
```

### Check
To check certain phrase or character present in string
```
txt = "The best things in life are free!"
print("free" in txt)
print("free" not in txt)
```
```
Output:
True
False
```

### Slicing
Slice syntax [:] is used to return a range of characters
If txt is a string and we do txt[::].
Breakdown
- Start from the begining, **start** is omitted and default is 0
- Go all the way to the end, **stop*** is omitted and default is len(str)
- Step by 1 step is omitted and defaults to 1

| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| H   | E   | L   | L   | O   |     | W   | O   | R   | L   | D   |
| -11 | -10 | -9  | -8  | -7  | -6  | -5  | -4  | -3  | -2  | -1  |

```
b = "HELLO WORLD"
print(b[2:5])
print(b[:5])
print(b[2:])
print(b[-5:-2])
print(b[:])
print(b[::2])
print(b[2::2])
print(b[::-2])
print(b[::-1])
print(b[8::-1])
print(b[8:1:-1])
```
```
Output:
LLO
HELLO
LLO WORLD
WOR
HELLO WORLD
HLOWRD
LOWRD
DRWOLH
DLROW OLLEH
ROW OLLEH
ROW OLL
```

### Replace
Replace a string with another string using replace() method
```
x = "Hello, Luke"
print(x.replace("Luke", "Jacob"))
print(x.replace("L", "J"))
```
```
Output
Hello, Jacob
Hello, Juke
```

### Split
The split() method provides the list by spliting the string provided in split method
```
x = "Hello, Luke. How are you ?"
print(x.split(","))
print("o")
```
```
Output
x = "Hello, Luke. How are you ?"
print(x.split(","))
print("o")
```

### Concatenate
```
a = "hello"
b = "luke"
print(a + b)
```
```
Output:
helloluke
```

Different [string methods](https://www.w3schools.com/python/python_ref_string.asp)
