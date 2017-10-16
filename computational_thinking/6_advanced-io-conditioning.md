[PDF lesson plan](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4468702-dt-content-rid-7950270_2/courses/1718-CM6114/6_Advanced_IO_Conditioning.pdf)

# argv

allarguements.py

```
from sys import argv

print(argv)
length = len(argv)

print("Number of arguements: {}" .format(length) )

print("The arguements are: {}" .format(argv))

```
**output**
```
PS C:\Users\c1712480\Documents\Semester_1\Computational_thinking\Work\My_code> python allarguements.py hey, awesome, coo
lio
['allarguements.py', 'hey', 'awesome', 'coolio']
Number of arguements: 4
The arguements are: ['allarguements.py', 'hey', 'awesome', 'coolio']
PS C:\Users\c1712480\Documents\Semester_1\Computational_thinking\Work\My_code>

```
# Split

Getting single values using the input() function. But what if we want to process different parts of
the user’s input? We could use some of the String built in functions like : S.split()
````
In [1]: many_values = input('> ')
print (many_values)
```
> this is a test input
this is a test input
```
In [2]: words = many_values.split(' ')
print(words)
```
['this', 'is', 'a', 'test', 'input']
python words = many_values.split(',') print (words)
What will it print? **Nothing**


# Supressing stdout

The input function prints whatever is inputted to the console. This can be unwanted.
Can you think such a senario?
```
In [3]: import getpass
user = input("Username:")
passwd = getpass.getpass("Password for " + user + ": ")
print("Got", user, passwd)
```
**Output**
```
Username:alex
Password for alex: ........
Got alex mypassword
```

```
import math
def log_num(num, base = 10, print_val = False):
    temp = math.log(num, base)
    if print_val:
        print('{} to base {} is:{}' .format(num, base, temp))
    return temp
log_num(3, 9, True)
log_num(10)
```

**Output**
```
3 to base 9 is:0.5
1.0
```
# Optional inputs
```
import datetime
def print_message_date (message, when=None):
if when is None:
when = datetime.date.today()
print('{}: {}'.format(when, message))
In [5]: print_message_date("my message")
print_message_date("my message","2016-08-15")
```

**Output**
```
2017-10-12: my message
2016-08-15: my message
```
# Functions can take functions as inputs:
```
def my_sum(x,y):
    return x+y

def my_mult(x,y):
    return x*y
def my_power(x, y):
    return x**y

def process_nums(myfun,var1,var2):
    temp = myfun(var1,var2)
    fun_name = myfun.__name__
    print('{} result = {}'.format(fun_name, temp))
    return temp

process_nums(my_sum,4,5)
process_nums(my_mult,4,5)
process_nums(my_power,3,7)
```

**Output**
```
my_sum result = 9
my_mult result = 20
my_power result = 2187
Out[16]:
2187
```

In [5]: def list_from_nowhere(l = []):
l.append(3)
return l
In [ ]: print(list_from_nowhere())
In [6]: print(list_from_nowhere())
[3]
What if we call it again?
In [7]: print(list_from_nowhere())
[3, 3]
A new list is created once when the function is defined, and the same list is used in each
successive call.
Python’s default arguments are evaluated once when the function is defined, not each time the
function is called. This means that if you use a mutable default argument and mutate it, you will
and have mutated that object for all future calls to the function as well.

# Reading/Writting at files

Function open() takes arguments as input: 1. filename 2. a string: w for write, r for read, a append
and r+ for read-write mode
In [ ]: f = open('workfile.txt', 'r')
print(f.read())
f.close()
In [ ]: f = open('workfile.txt', 'w')
f.write('\nThis is line 4')
f.close()
