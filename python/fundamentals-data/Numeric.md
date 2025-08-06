There are three numeric types
- int
	- It can be a whole number, positive or negative, without decimal, unlimited length
- float
	- It is a number, positive or negative containing a decimal
	- It can also have scientific numbers with an "e" to indicate power of 10
		```
		x = 35e5
		z = 12E4
		```
- complex
	- It contains a "j" as the imaginary part
	```
	x = 1+9j
	y = 6j
	```
	
### Type Conversion
Conversion from one to another is done with int(), float() and complex() methods:
```
x = float(1)
y = int(7.4)
z = complex(6)

print(x)
print(y)
print(z)
```
```
Output
1.0
7
(0+6j)
```

### Check Type
```
x = 7
y = 9j

print(type(x))
print(type(y))
```
```
Output:
<class 'int'>
<class 'complex'>
```