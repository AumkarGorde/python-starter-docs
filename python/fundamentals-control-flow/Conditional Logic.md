# Conditional Logic

### If Else
- Short hand if is used, when you have one statement to execute/
	- `if a>b: print("A is greater than B")`
- Short hand if else or ternary condition
	- `print("A") if a>b else print("B")`
- `and` keyword is used to combine conditional statement
	- `if a>b and a>c print("A is greater")`
- `or` keyword is used to combine conditional statement
	- `if a>b or a>c print("A is greater")`
- `not` key word is used to reverse the result of the conditional statement
	- `if not a>b print("A is not greater")`
- `pass` keyword is to avoid getting error if you have `if` statement with no content
```
if a>b:
	pass
```

### Match Case aka Switch Case
- `match` is nothing but a switch case in most of programming language
- It selects one of the many code blocks to be executed
```
day = 4
match day:
  case 1:
    print("Monday")
  case 2:
    print("Tuesday")
  case 3:
    print("Wednesday")
  case 4:
    print("Thursday")
  case 5:
    print("Friday")
  case 6:
    print("Saturday")
  case 7:
    print("Sunday")
```
```
Output:
Thrusday
```
- `_` is used as default case in case none of the condition matched it will fall to this
```
day = 1
match day:
  case 6:
    print("Today is Saturday")
  case 7:
    print("Today is Sunday")
  case _:
    print("Wrong choice ")
```
```
Output:
Wrong choice
```
- `|` character is used if you have  same condition for multiple match cases
```
day = 4
match day:
  case 1 | 2 | 3 | 4 | 5:
    print("Today is a weekday")
  case 6 | 7:
    print("I love weekends!")
```
```
Today is a weekday
```
- Adding `if` statement with condtion as an extra check
```
month = 5
day = 4
match day:
  case 1 | 2 | 3 | 4 | 5 if month == 4:
    print("A weekday in April")
  case 1 | 2 | 3 | 4 | 5 if month == 5:
    print("A weekday in May")
  case _:
    print("No match")
```
```
Output:
A weekday in May
```

### While Loop
- Same as most programming languages.
- `break` `continue` `if else`are the most used keywords with while loop

### For Loop
- `for` and `in` are the keywords used to create simple for loop in python
```
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x) 
```
```
Output:
apple  
banana  
cherry
```
- `range(6)` is not values from 0 to 6 but 0 to 5
- `rang(2,6)` values start from 2 to 6 (does not include 6)
- range(2,30,3) values start from 2 to 30, with jump of 3 (does not include 30)
- `for ... else` loop
	- Run the `else` block if the loop ended naturally (i.e loop went through all iterations without hitting a break)
	- if the loop is interrupted with `break`, the `else` block is skipped entirely
```
for x in range(6):
  print(x)
else:
  print("Finally finished!")
```
```
Output:
0  
1  
2  
3  
4  
5  
Finally finished!
```
```
for x in range(6):
  if x == 3: break
  print(x)
else:
  print("Finally finished!")

#If the loop breaks, the else block is not executed.
```
```
Output:
0  
1  
2
```
- `for` loops cannot be empty, but if you for some reason have a for loop with no content, put in the `pass` statement to avoid getting an error.
```
for x in [0, 1, 2]:
  pass
```