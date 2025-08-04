Below are the built in data types

| Type                |                              |
| ------------------- | ---------------------------- |
| Text \| [[Strings]] | str                          |
| [[Numeric]]         | int, float, complex          |
| Sequence            | [[List]], tuple, range       |
| Mapping             | dict                         |
| Set                 | set, frozenset               |
| [[Boolean]]         | bool                         |
| Binary              | bytes, bytearray, memoryview |
| None                | NoneType                     |

Print the data type of a variable
```
x = 5
print(type(x))
```

Data type is set when a variable is assigned a value

| Type       | Example                                       |
| ---------- | --------------------------------------------- |
| str        | x =  "abc"                                    |
| int        | x = 34                                        |
| float      | x = 6.5                                       |
| complex    | x = 2 + 3j                                    |
| list       | x = ["red", "orange", "green ]                |
| tuple      | x = ("India", "USA", "Spain")                 |
| range      | x = range(6)                                  |
| dict       | x = {"name" : "Omkar", "age" : 28}            |
| set        | x = {"lion", "tiger", "wolf"}                 |
| frozenset  | x = frozenset({"dell", "apple", "microsoft"}) |
| bool       | x = True                                      |
| byte       | x = b"Hello"                                  |
| bytearray  | x = bytearray(5)                              |
| memoryview | x = memoryview(bytes(5))                      |
| NoneType   | x = None                                      |

Data Types can be specified by constructor function
```
x = str("Hello World")
x = dict(name = "Omkar", age = 28)
```
