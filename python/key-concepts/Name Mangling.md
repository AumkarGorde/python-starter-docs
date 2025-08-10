# Name Mangling
- If you define an attribute or method with two leading underscores (**__**) and no trailing underscores, the interpreter changes (mangles) its name internally to include the class name with it.
- This not the way of making truly private
```
class Parent:
    def __init__(self):
        self.__secret = "this secret"
    
    def reveal(self):
        print(self.__secret)
    
a1 = Parent()

print(a1.reveal())
print(dir(a1))
print(a1.__secret)
```
```
Output:
this secret
AttributeError: 'Parent' object has no attribute '__secret'
```
- If we check the actual attribute names by doing `dir(a1)` you can see `__secret` is changed to `_Parent__secret`
- This is not true private because that attribute still can be accessed if we do `a1._Parent__secret` without any error
- This is applicable to methods as well , by adding double underscore at start of the method name
- The real use of this is to avoid accidental name collision in subclasses
```
class Parent:
    def __init__(self):
        self.secret = "parent secret"
    
    def reveal(self):
        print(self.secret)
    
class Child(Parent):
    def __init__(self):
        super().__init__()
        self.secret = "child secret" # Overwrites parent's version


c1 = Child()

c1.reveal()
```
```
Output:
child secret
```
- Here name mangling helps to solve the above problem so that the parent will have different secret and child has different secret variable specific to there instance
```
class Parent:
    def __init__(self):
        self.__secret = "parent secret"
    
    def reveal(self):
        print(self.__secret)
    
class Child(Parent):
    def __init__(self):
        super().__init__()
        self.__secret = "child secret"


c1 = Child()

c1.reveal()
```
```
Output: 
parent secret
```