# Lambda
- It is small anonymous function,
- It can take any number of arguments, but can only have one expression.
- `lambda arguments : expression`
```
x = lambda a : a * 2
print(x(3))
```
```
Output:
6
```
- lambda can take multiple argument
```
x = lambda n1, n2 : n1 * n2
print(x(4,5))
```
```
Output:
20
```
- Complex example, using lamda inside a function
```
def myfunc(n):
  print(f"n:{n}")
  return lambda a : a * n

mydoubler = myfunc(2)

print(mydoubler(11))
```
```
Output:
n:2
22
```