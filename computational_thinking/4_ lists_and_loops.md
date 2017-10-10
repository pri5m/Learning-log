[Lesson pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4459785-dt-content-rid-7897048_2/courses/1718-CM6114/4_Lists_and_Loops_InClass.pdf)

# Review
Write a function get_number that takes two arguments a string and a number and prints the string
if the number is positive else returns 0. Then use the input function to get a string and a number
from the user. Call the function for the values that the user has given.
```
def get_number(num, the_string):
    return

num = int(input("Type in a number here: "))
the_string = input("Type in a string here: ")

get_number(num, the_string)
    
if num % 2 == 0:
    print(the_string)
else:
    print("0")
```
# Lists
```
list_one = ['Rick', 'Morty', 'Beth', 'Summer']
list_two = list_one
list_two.append('Jerry')
print(list_one)
print(list_two)
```
**output**
```
['Rick', 'Morty', 'Beth', 'Summer', 'Jerry']
['Rick', 'Morty', 'Beth', 'Summer', 'Jerry']
In [ ]:
```
Think of it in 3D space, two points of a triangle converge to one point. List_one converges to the same point as list_two as list_one = list_two. Pointing to the same place, so even if one of the lists is changed, the other is changed as well. They are **mutible**

*Will be a question on mulibility in the exam*

```
a = [1,2,3]
b = [1,2,3]
print(a is b)
a = b
print(a is b)
a.append(45)
print(a is b)
```
Output
```
False
True
True
```

Lists a and b have different names but refer to the same object. The are called **aliased.**

Aliasing can be undesirable.
Copying or cloning mutable objects.

a = b[:]
or
a = b.copy()

Both options create a new list. Changing a will not affect b.
