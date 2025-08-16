# Inheritance
- It allows child class to reuse and extend the funtionality of the parent class
- `Basic Syntax`
```
class Parent:
	pass

class Child(Parent):
```
- Method overriding
	- If child class contain a method with same name as the parent's the child version is used
```
class Animal:
    def __init__(self, name):
        print("inside parent")
        self.name = name

    def make_sound(self):
        print("Making sound")

class Dog(Animal):
    def __init__(self):
        print("inside dog")

    def make_sound(self):
        print("bark bark")

a1 = Dog()
a1.make_sound()
```
```
Output:
inside dog
bark bark
```
- The `super` keyword lets you call methods from the parent class without naming it explicitly
	- Here `super` keyword is not used so no parent invocation
```
class Animal:
    def __init__(self, name):
        print("inside parent")
        self.name = name

class Dog(Animal):
    def __init__(self):
        print("inside dog")

a1 = Dog()
```
```
Output:
inside dog
```
- When we use the super method it will invoke the parent method as well
- This applys to all the method in the parent class, if you want to call them call by using super keyword
```
class Animal:
    def __init__(self, name):
        print("inside parent")
        self.name = name

class Dog(Animal):
    def __init__(self,name):
        super().__init__(name)
        print("inside dog")

a1 = Dog("Bruno")
```
```
inside parent
inside dog
```
- Different types of inheritance in python
	- Single Inheritance 
		- A child class inherits from a single parent class
	- Multiple Inheritance
		- A child class inheruts from more than one parent class
		- Example child herits from mother and father. Child(Mother, Father)
	- Multilevel Inheritance
		- Inheritance happen in chain - child inherits deom a parent and the another child inherits from that child
		- Example : GrandParent -> Parent(GrandParent) -> Child(Parent)
	- Hirarchical Inheritance
		- Multiple child class inherit from the same parent
		- Example : Parent -> Child_1(Parent) and Child_2(Parent)
	- Hybrid Inheritance
		- A combination of multiple inheritcance 
		- Python uses C3 linearization algo. for MRO to handle these cases

### Inheitance vs Composition
- `Is-a` vs `has-a`
- In inheritance a child class inherits the properties and behaviour of the child class
- In composition a class contains an instance of another class and uses it to provide functionality
