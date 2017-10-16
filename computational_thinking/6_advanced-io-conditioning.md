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
Password for alex: ········
Got alex mypassword
```
