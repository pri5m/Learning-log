[Lesson pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4477816-dt-content-rid-8082837_2/courses/1718-CM6114/8_Dictionaries_Tuples_Recursion.pdf)
```
empty_dict = {}
print(type(empty_dict))

#output
<class 'dict'>
```

```
movie = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

print(movie)
print(movie["Title"])

# Output
{'Director': 'James Cameron', 'Title': 'Avatar', 'Genre': 'Fantasy', 'Year': '2009'}
Avatar
```
**Note**- Don't forget the comma at the end of the line

**Keys are on the right and values are on the left**

eg. "Title"- key   "Avatar"- value
```
movies = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

print(movies.values())
print(movies.keys())

#output
dict_values(['Fantasy', '2009', 'Avatar', 'James Cameron'])
dict_keys(['Genre', 'Year', 'Title', 'Director'])
```

```
movies = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

for key in movies:
    print(key)
for key,val in movies.items():
    print("{} => {}". format(key, val))

for key in movies:
    if len(key) > 4:
        print(movies.get(key))
        
#output
Genre
Year
Title
Director
Genre => Fantasy
Year => 2009
Title => Avatar
Director => James Cameron
Fantasy
Avatar
James Cameron
```

Using the methods you found, write a function that has a dictionary as an argument and loops
through the values to return the first value that is of type int
```
movies = {
        "Title":"Avatar",
        "Year": 2009,
        "Genre":"Fantasy",
        "Director":"James Cameron"
    }

def intvalue(adict):
    for a in movies.values():
        if type(a) == int:
            print(a)
            return a
        
intvalue(movies)

# Output
2009
```

```
for i, k in enumerate(movies):
    print(i, k)
    
#output
0 Genre
1 Year
2 Title
3 Director
```
# Removing items

Much like lists, we can pop elements from a dict, but the way this is done is slightly different:

pop() - One must provide the key of the item to be removed and the value is returned. An
error is given if nothing was found

popitem() - This works much like pop on a list, removing the last item in the dict and providing
the key and the value.

Find out how to use del.

```
movies = {
        "Title":"Avatar",
        "Year": 2009,
        "Genre":"Fantasy",
        "Director":"James Cameron"
    }

print(movies)
movies.pop("Title") # Returns the value from the key
print(movies)
movies.popitem() # Returns the last item from the dictionary
print(movies)

# Output
{'Genre': 'Fantasy', 'Year': 2009, 'Title': 'Avatar', 'Director': 'James Cameron'}
{'Genre': 'Fantasy', 'Year': 2009, 'Director': 'James Cameron'}
{'Year': 2009, 'Director': 'James Cameron'}
```
# Tuples

Immutable lists. Tuples support the same sequence operations as strings

Can access them like lists:
```
my_tuple = 1, 2
print(my_tuple)
print(type(my_tuple))
new_tuple = 3, "a", 6
print(new_tuple)
print(new_tuple[1])

#Output
(1, 2)
<class 'tuple'>
(3, 'a', 6)
a
In [ ]:
```
What are tuples good for?

Functions can return one single value.

Using tuples we can group as many values as we want.

```
def number_and_power(x):
    return x, x**x

number_and_power(3)

#Output
(3, 27)
```
```
def histogram(s):  #s-string
    d = dict()  # Creates an empty dictionary
    for c in s:  #c- character, for the character in the string
        if c not in d:  # If the character is not already contained in the dictionary:
            d[c] = 1  # The character becomes a key with that particular name and is assigned a value of 1
        else:
            d[c] += 1  # If the character is already in the list, then increase it increases value by 1, increment
    return d

histogram("Zoumpoulaki")

#Output
{'Z': 1, 'a': 1, 'i': 1, 'k': 1, 'l': 1, 'm': 1, 'o': 2, 'p': 1, 'u': 2}
```

# Dictionaries and tuples ex
```
student = {
    "Name": "Holly",
    "Surname": "Smith",
    "marks": (23, 93, 82),
    "year_of_study": 1
}

sum = 0
tmp = []

for m in student["marks"]:
    if m > 40:
        sum = sum + m
    else:
        tmp.append(m)
        
if tmp == []:
    print(sum / len(student["marks"]))
else:
    print(tmp)
```
# Searching dictionaries
```
students = {
    1234: "Gary",
    4567: "Jen"
}

print("1. {}". format(1234 in students))
print(1234 in students.keys())
print("Jen" in students)
print("Gary" in students.values())
print("Gary" in students.items())
print((1234, "Gary") in students.items)
```

# Recursion

An iterative function is a function that loops to repeat a block of code.

A recursive function is a function that calls itself (until a condition is met).


What will this print?
```
def countdown(n):
    if n <= 0:
        print('Blastoff!')
    else:
    print(n)
    return countdown(n-1)
    
countdown(3)
```
**What is Happening Here?**

Python sees our call to the function and executes it.

Recursion Level

• n = 3 Is n <=0 ? No

print(3)

Return countdown(2)

• n = 2 Is n <=0 ? No

print(2)

Return countdown(1)

• n=1 Is n <=0 ? No

print(1)

Return countdown(0)

• Is n <=0 ? Yes

print("Blast off")

# Factorials
Iterative
```
def facto_iterative(num):
    mult = 1
    for i in range(1, num + 1):
        mult = mult*i     
    return mult

facto_iterative(3)
```

Recursive
```
def recursive_factorial(n):
    if n == 1:
        return 1
    else:
        return n * recursive_factorial(n-1)
```

# Recursion vs. Iteration

You have seen both, which is better/faster/more optimal?
Have you ever heard of stack overflow? What does it mean?

While recursive approaches are typically shorter and easier to read. However, it also results in
slower code because of all the funtion calls it results in, as well as the risk of a stack overflow
when too many calls are made.

Typically, math-based apparoaches will use recursion and most software engineering code will
use iteration. Basically, most algorithms will use recursion so you need to understand how it
works.

# When Should You Use It?

Recursion is often seen as some mythical beast but the breakdown is quite simple.
However, most (not all) languages are not tuned for recursion (unfortunately python is one of
them) and, in performance terms, iteration is often vastly quicker.

*Will be in the exam- know exactly what it is evaluating*

# Why the Difference?

To understand this, we need to understand a little bit about how programs are run.
Two key things are the **stack** and the **heap**

Stack is used for static memory allocation and Heapfor dynamic memory allocation.


**timeit**- Times how long it takes to execute a section of code

