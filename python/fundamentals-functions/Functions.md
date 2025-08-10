# Functions
- Block of code runs when it is called 
- You can pass data via the parameters into a function
- A function can return data as well
```
def my_function(fname, lname):
  print(fname + " " + lname)

my_function("Omkar", "Gorde")
```
```
Output:
Omkar Gorde
```

### Arbitary argument (* args)
- If you do not know how mant arguments that will be passed to function, add `*` before the parameter name in the function defination
- The function will receive a tuple of arguments and can be accessed accordingly
```
def my_function(*fruits):
  print(type(fruits))
  print(fruits)
  print("Your favourite fruit is " + fruits[2])

my_function("orange", "banana", "cherry")
```
```
Output:
<class 'tuple'>
('orange', 'banana', 'cherry')
TYour favourite fruit is cherry
```

### Arbitary Keyword Argument (** kwargs)
- If you do not know how many keyword arguments that will be passed into your function, add two asterisk: `**` before the parameter name in the function definition.
- This way the function will receive a `dictionary` of arguments, and can access the items accordingly:
```
def my_function(**personalInfo):
  print("His last name is " + personalInfo["lname"])

my_function(fname = "Omkar", lname = "Gorde`s")
```
```
Output:
His last name is Gorde`s
```

### Keyword Arguments (Python) vs Named Arguments (C#)

| Feature                      | Python Keyword Arguments                                                                                    | Named Arguments                                                                                                                                |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Official term**            | Keyword Arguments                                                                                           | Named Arguments                                                                                                                                |
| **Syntax**                   | `func(param=value)`                                                                                         | `Method(param: value)`                                                                                                                         |
| **Order flexibility**        | Yes, can appear in any order                                                                                | Yes, can appear in any order                                                                                                                   |
| **Mix with positional args** | Yes, positional first then keyword args                                                                     | Yes, named and positional can be mixed, but positional must come first unless all are named                                                    |
| **Parameter names**          | Must match exactly the function definition                                                                  | Must match exactly the method signature                                                                                                        |
| **Optional parameters**      | Works with default values in function definition                                                            | Works with optional parameters defined using default values                                                                                    |
| **Language behavior**        | Part of Python's function call syntax                                                                       | Part of C# method call syntax                                                                                                                  |
| **Common use case**          | Improve readability, pass only some optional params                                                         | Improve readability, skip parameters you don’t need to change                                                                                  |

### Positional-only Argument
`, /` is used after the argument to specify that it is only positional arguments
```
def my_function(x, /):
  print(x)

my_function(3)
```

### Combine Positional and Keyword
- Any argument before `/ ,` are postional-only, and any argument after the `*, ` are keyword-only
```
def my_function(a, b, /, *, c, d):
  print(a + b + c + d)

my_function(5, 6, c = 7, d = 8)
```
```
Output:
26
```
