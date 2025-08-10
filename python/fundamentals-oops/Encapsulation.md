# Encapsulation
- It means bundling data and the methods that operate on it within a class and control access to that data.
	- data hiding
	- controlled access (via getters, settters, properties)
### Access modifiers
- Python does not have `private` or `protected` keywords, but it uses name mangling and naming conventions.
#### Public Attribute
- No underscore prefix
- Can be accessed anywhere
```
class Foo:
    def __init__(self):
        self.data = 42  # public
```
#### Protected Attributes
- Prefix with a single underscore `_`
- It only signals `for internal use only` it does not mean you can't access or you will get any error
- Also, during an import `from some_module import *` python will skip any names starting with `_` but can explicitly import it like this : `from some_module import some_function`
```
class Foo:
    def __init__(self):
        self._cache = {}

```
#### Private Attributes 
- Prefix with double underscore `__`
- It is internally named as `_ClassName__attrName`
- Prevents accidental overrides by using the concept of [[Name Mangling]] 
```
class Foo:
    def __init__(self):
        self.__secret = "hidden"

```

### Properties
- Instead of exposing the attributes directly, Python allows `@property` decorators for encapsulated access
- Properties can be created in **Two** ways:
	- Using property() function
	- Using **@property** decorator (modern proffered way)
- Why use properties:
	- Add more validation, that is to reject bad values
	- Transform or sanitise data before storing it
	- Compute values on fly instead of storing them
	- Make an attribute read-only or write-once
	- Log or trigger actions whenever it's accessed/changed/deleted
```
class Person:
    def __init__(self, name, gender):
        self.gender = gender
        self._name = name

    @property                       # getter
    def name(self):
        return f"Hello {self._name} !!"
    
    @name.setter                    # setter should be @{property_name}.setter
    def name(self,value):
        print(f"Changing name in setter")
        if self.gender == "Male":
            self._name = f"Mr. {value}"
        else:
            self._name = f"Mrs. {value}"

    @name.deleter                   # deleter should be @{property_name}.deleter
    def name(self):
        print(f"Deleted : {self._name}")
        del self._name


p1 = Person("Omkar","Male") # this does not call the setter just calls __init__
print(p1.name)              # this calls the getter
p1.name = "Joe"             # this calls the setter
print(p1.name)              # this calls the getter again
del p1.name                 # this calls the deleter
```
 