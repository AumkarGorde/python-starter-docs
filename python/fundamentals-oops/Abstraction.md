# Abstraction
- Abstraction eans hiding complex implementation details and showing only the essential features to the user.
- Achived using abstract classes and abstract methods

#### Abstract class
- It is a class that cannot be instantiated directly.
- It contains one or more abstract methods
- It is a blueprint to other classes

##### Creation
- Python provides `abc` module (Abstract Bas Classes) to define a abstract class
- A class must inherit from `ABC` to become an abstract class
- `@abstractmethod` 
	- A decorator that declares a method is abstract 
	- Abstract methods have no implementation in the base class
	- Sub-classes must override abstract methods
- You cannot instantiate an abstract class
- Abstract methods can also be properties using `@property` with `@abstractmethod`
- Abstract methods can have concrete methods along with abstract methods
- Abstract classes can have a constructor (__ init __)
```
from abc import ABC, abstractmethod

class Animal(ABC):

    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Bark Bark !"
    
d = Dog()
print(d.make_sound())
```
```
Output:
Bark Bark !
```
