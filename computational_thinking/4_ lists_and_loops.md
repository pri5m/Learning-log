[Lesson pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4459785-dt-content-rid-7897048_2/courses/1718-CM6114/4_Lists_and_Loops_InClass.pdf)

[Lesson part b pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4462166-dt-content-rid-7908167_2/courses/1718-CM6114/4_Lists_and_Loops_InClass_b.pdf)

[Lesson work link](http://localhost:8888/notebooks/Work/My_code/4_lesson_work.ipynb)

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
**Output**
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

**Numbering**
```
movie_list = ['Blade Runner', 'AI', 'I Robot', 'Matrix', 'Terminator']

print(movie_list[0])

'Blade Runner'
```

```
movie_list = ['Blade Runner', 'AI', 'I Robot', 'Matrix', 'Terminator']

print(movie_list[0])

print(len(movie_list))

print (movie_list[-1])

print (movie_list[-2])
```
**Output**
```
Blade Runner
5
Terminator
Matrix
```
**Exercise**

• Instantiate a list with 3 elements inside
• Print the first element
• Change the first element to c-137
• Print the whole list
• Print the length of the list
• Print the second to last element
• Create an empty list
• What happens when you try and print the second element?
• What about when you assign a literal to the first element?

```
my_list = ['c-137', 'Hi!', 'Nice to meet you']

print(my_list[0])

print(my_list)

print(len(my_list))

print (my_list[-2])
```
**Output**
```
c-137
['c-137', 'Hi!', 'Nice to meet you']
3
Hi!
```

```
my_empty_list = []

print (my_empty_list[1])
```
Error message: list index out of range

```
alphabet = ['a','b', 'c', 'd', 'e', 'f']
print(alphabet[1:3])

[b, c]
```
[1:3] Up to 3 so position 1 and  2 will be printed


Lists, like all Python objects, have methods built into them. We can find these out by using the dir
function:
```
alphabet = ['a','b', 'c', 'd', 'e', 'f']
print(alphabet[:3])
dir([])
```

**Append**
```
movie_list = ['Blade Runner', 'AI', 'I Robot', 'Matrix', 'Terminator']
movie_list.append ('Back to the Future')
movie_list.append ('Indiana Jones')
print(movie_list)


['Blade Runner', 'AI', 'I Robot', 'Matrix', 'Terminator', 'Back to the Future', 'Indiana Jones']
```
**Create the list above. Using the dir and help functions, do the following:**

- Copy the list to a new list and call it great_movies
- Pop the last element off the new list
- Find a method to count the number of occurrences of an item in a list
- Print the number of occurrences of Rambo 4
- Find the index of movie "The room" in both of the lists
```
great_movies = ['Avatar', 'Spirited away', 'Your name', 'Your name', 'Your name', 'Blade runner', 'Shawn of the dead']

print(great_movies.pop())

print(great_movies.count('Avatar'))

print(great_movies.count('Your name'))

print(great_movies.index('Blade runner'))
```
**Output**
```
Shawn of the dead
1
3
5
In [ ]:
```
# Stacks and queues

LIFO- Last in First Out

FIFO- First in First Out

**Last In First Out -- STACK**

Think of a shopping cart that you fill as you go around a supermarket. Assuming you are organised
and fill from the bottom up, then you will empty the cart at the checkout with the last items
you put in there first.

**First In First Out -- QUEUE**

Now think of the conveyor belt that you put the shopping on. When the checkout assistant (or
robot that will soon replace them) gets to scan the items.

*Which of the examples are FIFO and which are LIFO?*

• Backpack-LIFO

• Supermarket Queue- FIFO

• Smarties packet - LIFO

• Baggage carousel - FIFO

# Loops

**For loops**
```
great_movies = ['Avatar', 'Spirited away', 'Your name', 'Your name', 'Your name', 'Blade runner', 'Shawn of the dead']

for item in great_movies:
    print(item)

for item in great_movies:
    print(great_movies.index(item))

temp = 0
    
for item in great_movies:
    print("{}:{}".format(temp,item))
    temp += 1 
```
**Output**
```
Avatar
Spirited away
Your name
Your name
Your name
Blade runner
Shawn of the dead
0
1
2
2
2
5
6
0:Avatar
1:Spirited away
2:Your name
3:Your name
4:Your name
5:Blade runner
6:Shawn of the dead
```
**Pythonic**
```
great_movies = ['Avatar', 'Spirited away', 'Your name', 'Your name', 'Your name', 'Blade runner', 'Shawn of the dead']

for index in range(len(great_movies)):
    print(index)
    
#PYTHONIC
print('--------')
for index, value in enumerate(great_movies):
    print(index, value) #Access both key and value

print('--------')
for value in great_movies: #Called a For in or a For each loop
    print(value) # Access just value but NO index
```
**Output**
```
0
1
2
3
4
5
6
--------
0 Avatar
1 Spirited away
2 Your name
3 Your name
4 Your name
5 Blade runner
6 Shawn of the dead
--------
Avatar
Spirited away
Your name
Your name
Your name
Blade runner
Shawn of the dead
```
3 ways to access a list:

- 
- 
- 

Given the list [31,45,12,300,40000,2]
Write a for loop to calculate the sum of all the values and print out the mean of all values

```
numbers = [31, 45, 12, 300, 40000, 2]

total = 0

for n in  numbers:
    total = total + n
    print("total: {}".format(total))
    print("number: {}".format(numbers))
    print('--------')
```
**Output**
```
total: 31
number: [31, 45, 12, 300, 40000, 2]
--------
31
total: 76
number: [31, 45, 12, 300, 40000, 2]
--------
45
total: 88
number: [31, 45, 12, 300, 40000, 2]
--------
12
total: 388
number: [31, 45, 12, 300, 40000, 2]
--------
300
total: 40388
number: [31, 45, 12, 300, 40000, 2]
--------
40000
total: 40390
number: [31, 45, 12, 300, 40000, 2]
--------
```
# Breaking loops

Sometimes, we may only want to execute when certain elements match some criteria we define.
Like in the example above, we can use if statements for this, but there are some other keywords

24.0.1 **break**

Using the break keyword, we can break out of our loop before it has finished. Why might this be
useful?

24.0.2 **continue**

The continue keyword passes over the current iteration and heads straight for the next one. For
example, if a value matches a value we do not want.
The difference here is that the loop does not stop. The loop continues until the end and just
skips when continue is used.
```
for i in range(0,5):
    if i == 2:
        continue #head back to the top and go to the next value for i
    print(i) #if i == 2 then this line is not executed
```
```
0
1
3
4
In [ ]:
```
## Part B

# Review no. 2
```
user_nums = []
total = 0
for i in range(0,5):
    user_input = input("enter a pos int please: ")
    if user_input.isdigit():
        user_nums.append(user_input)
        total += int(user_input)
    else:
        print("I said a positive number")
if len(user_nums) == 5:
    print(total/len(user_nums))
```
**Output**
```
enter a pos int please: 4
enter a pos int please: 4
enter a pos int please: 4
enter a pos int please: 4
enter a pos int please: 4
4.0
```
# Review no. 3
```
user_string = input()
vowels = ['a', 'e', 'i', 'o', 'u']
for letter in user_string:
    if letter in vowels:
        continue
    print(letter,end='')
```
**Output**
```
this is cool
ths s cl
```
