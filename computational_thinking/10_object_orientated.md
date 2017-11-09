[Classes- pydoc](https://docs.python.org/3/tutorial/classes.html)

The instantiation operation (“calling” a class object) creates an empty object. Many classes like to
create objects with instances customized to a specific initial state.
__init__(), allows to create Objects with different values:

```
class Pet:
    def __init__(self, petClass):
        self.petClass = petClass
    
    def show_class(self):
        print("This is a {}".format(self.petClass))

guineaPig = Pet("Guinea Pig")
hamster = Pet("Hamster")
dog = Pet("Dog")
cat = Pet("Cat")

print(guineaPig)
print(hamster)
```
Classes have variables attached to them and there are two key types we look at here:

- Instance variables

- Class variables

# Class attributes

Attributes that are attached to a class and shared across all instances.
```
class Person:
    person_count = 0
    
    def __init__(self):
        Person.person_count += 1
```
In java we would call such variables *static.*

