# Polymorphism
- Polymorphism allows different objects to be accessed through the same interface, with each object to be accessed through the same interface, with each object responding differently based on its own implementation
## Types of Polymorphism
### Duck Typing
- You don't check the object type
	- `If it walks like a duck and quaks like a duck. it's a duck`
```
class Dog:
    def make_sound(self):
        print("Bark, bark !!")

class Cat:
    def make_sound(self):
        print("Meow, meow !!")

def animal_sound(animal):
    animal.make_sound()

animal_sound(Dog())
animal_sound(Cat())
```
```
Output:
Bark, bark !!
Meow, meow !!
```
### Method Overriding
- When a child class provides a specific implementation of a method already defined in its parent class it's called method overriding
```
class Animal:
    def make_sound(self):
        print("Unknown sound")

class Dog(Animal):
    def make_sound(self):
        print("Bark, bark !!")

class Cat(Animal):
    def make_sound(self):
        print("Meow, meow !!")

animals = [Dog(), Cat()]

for animal in animals:
    animal.make_sound()
```
```
Output:
Bark, bark !!
Meow, meow !!
```
### Operator overloading
- You can redefine the behviour of built-in operators for your classes by implementing special methods
```
class Point:
    def __init__(self,x,y):
        self.x = x
        self.y = y

    def __add__(self, obj):
        return Point(self.x + obj.x, self.y + obj.y)
    
    def __str__(self):
        return f"x: {self.x}, y: {self.y}"
    
p1 = Point(6, 6)
p2 = Point(1, 1)

print(p1+p2)
```
```
x: 7, y: 7
```
### Function Overloading
- Python does not have traditional function overloading, that is same function name and different parameter.
```
def sum_num(x,y):
    return x+y

def sum_num(x,y,z):
    return x+y+z

print(sum_num(2,3))
print(sum_num(1,2,3))
```
```
Output:
 sum_num() missing 1 required positional argument: 'z'
```
