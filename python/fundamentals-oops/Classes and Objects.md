# Classes and Objects

- Python is OOP language, almost everting in Python is an object with its methods and properties

### Class
- `class` keyword is used to create a class.
- `__init__()` this same as constructor in c#, always executed when a class initiated
	- Mostlty used to assign values to properties inside the class.
- `self` parameter is a reference to the current instance of the class, and used to access the variables that belong to the class 
	- You can call whatever you want instead of `self`, but it has to be first parameter of the `__init__()` function
```
class Person:
  def __init__(self, name, age):
    print("Inside init")
    self.name = name
    self.age = age

p1 = Person("Omkar", 28)

print(p1.name)
print(p1.age)

p2 = Person("Jorey", 36)

print(p2.name)
print(p2.age)
```
```
Output:
Inside init
Omkar
28
Inside init
Jorey
36
```
- `__str__()` this methods controls what to return when the object is presented as string
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age
  
  def __str__(self):
  	return f"{self.name}:{self.age}"

p1 = Person("Omkar", 28)

print(p1)
```
```
Output:
Omkar:28
```
- `del` keyword is used to delete the object created
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age
  
  def __str__(self):
  	return f"{self.name}:{self.age}"

p1 = Person("Omkar", 28)

del p1
print(p1)
```
```
Traceback (most recent call last):
  File "./prog.py", line 12, in <module>
NameError: name 'p1' is not defined
```

### Instance and Class variables
- Instance variable
	- These variables are unique to each object of the class
	- It is stored inside the object's won data
	- It is created usually inside `__init__` or other instance methods
	- It can be accessed by the specific object and the instance methods
		- Instance methods means methods which has self as first param.
	- Each instance gets its `own unique copy` - changing it on one object does not change other objects
```
class Car:
    def __init__(self, color):
        self.color = color  # instance variable

car1 = Car("red")
car2 = Car("blue")

car1.color = "green"   # changes only car1
print(car1.color)  # green
print(car2.color)  # blue
```
```
Output:
green
blue
```
- Class variable
	- These variables are shared by all instances of a class
	- It is stored in class itself and `not in self`
	- It is created directly inside class body
	- All instances and the class can access this variable
	- Change in one effects all the objects
```
class Car:
    wheels = 4  # class variable

    def __init__(self, color):
        self.color = color  # instance variable

car1 = Car("red")
car2 = Car("blue")

print(car1.wheels)  # 4
print(car2.wheels)  # 4

Car.wheels = 6  # changes for all

print(car1.wheels)  # 6
print(car2.wheels)  # 6
```
- It is bad practice to do something like this `car2.wheels = 8`
- Here, `car2.wheels` does not change the class variable - it just create a new instance variable that shadows the class one for that object only
```
class Car:
    wheels = 4  # class variable

    def __init__(self, color):
        self.color = color  # instance variable

car1 = Car("red")
car2 = Car("blue")

print(car1.wheels)  # ?
print(car2.wheels)  # ?

Car.wheels = 6  # changes for all

car2.wheels = 8  # creates instance variable on car2 only

print(car1.wheels)  # ?
print(car2.wheels)  # ?
print(Car.wheels)   # ?
```
```
Output:
4
4
6
8
6
```

### Instance and Class Methods
- Instance method:
	- First parameter is the `self` : which refers to a instance of the object
	- Works with specific instance of the class
	- It can access both : `instance and class variables`
	- No decorator needed
```
class Dog:
    def bark(self):
        print("Woof!")
Dog().bark()
```
```
Output:
Woof!
```
- Class method:
	- First parameter is class
	- It works with class level data.
	- It can access only : `class variables`
		- It cannot access instance specific data unless passed explicitly
	- It requires `@classmethod` decorator
```
class Dog:
    dogs_created = 0

    @classmethod
    def increment_count(cls):
        cls.dogs_created += 1

print(Dog.dogs_created)
Dog.increment_count()
print(Dog.dogs_created)
```
```
Output:
0
1
```
- Calling a **class method** from an instance will **never** create or change that that instance's own variables - it will operate on class level
- See below example:
```
class Car:
    wheels = 4

    @classmethod
    def set_wheels(cls, num):
        cls.wheels = num

c1 = Car()
c2 = Car()

c2.set_wheels(8)  # changes class var
print(c1.wheels, c2.wheels)  # 8 8

c2.wheels = 10    # creates instance var for c2 only
print(c1.wheels, c2.wheels)  # 8 10
```
- Instance method and variable should be accessed directly from class not by it instance as part of right practice
### Static methods
- `@staticmethod` decorator is used to declare a method as static in a class
- It does not have `self` or `cls` as first parameter, it gets not special first argument
- It belongs to the class namespace
- It cannot access self or class variables directly it needs to passed to them
- Global variable can accessed
- It is used for logical related helper functions
- It can be called on both instance and class, no difference in behaviour
- If you try to access class variable without class. or cls. that variable is considered as local variable of that static method
```
class Car:
    wheels = 4  

    def __init__(self, color):
        self.color = color  
        
    @staticmethod
    def test_static():
        wheels = 10
        print(f"inside static class variable: {Car.wheels}")
        print(f"inside static local variable: {wheels}")
        
car1 = Car("red")

print(Car.wheels)

Car.test_static()

print(Car.wheels)

```
```
4
inside static class variable: 4
inside static local variable: 10
4
```