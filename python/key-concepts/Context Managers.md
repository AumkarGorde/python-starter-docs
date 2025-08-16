# Context Managers
- It is a python object that properly sets up a resource when you start using it and automatically releases/cleans up that resource when you are done even if error occurs
- `with` keyword is used for this
```
with open("data.txt". "r") as file
	contents = file.read()
```