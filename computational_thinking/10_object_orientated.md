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

```
class Person:
    personCount = 0
    
    def __init__(self):
        Person.personCount += 1
    
print(Person.personCount)
p = Person()
p1 = Person()
p2 = Person()
print(Person.personCount)
print(p2.personCount)
```

Output
```
0
3
3
```
Define a class, which have a class variable and have a same instance variable.
Write a method to return (NOT PRINT) the instance variable.
Create instances of the class and print out both.

This is bad practice:
```
class Test:
    a = 0
    def __init__(self, x):
        self.a = x

one = Test(2)
print(Test.a)
print(one.a)
```
