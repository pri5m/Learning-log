# 2_coding

[Link to the pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4448826-dt-content-rid-7828721_2/courses/1718-CM6114/2_Coding.pdf)


snake_case- All lower case words should be separated by underscores

[PEP 8- A python style guide](https://www.python.org/dev/peps/pep-0008/)



# Variables

- none- Suggesting the use of the variable, might not hold  value yet

- id function- returns the memory adress. Unique identifier

**Don't use these words as var names as they are python keyword**

*False class finally is return
continue for lambda try True
def from nonlocal while and
del global not with as
elif if or yield assert
else import pass break except
in raise None*

Strongly typed means no adding differet types together

dynamically typed means yes to changing the type of a var

**What is REPL?**

Read–Eval–Print Loop

Also known as an interactive toplevel or language shell, is a simple, interactive computer programming environment that takes single user inputs (i.e. single expressions), evaluates them, and returns the result to the user; a program written in a REPL environment is executed piecewise.

**What does strongly typed?**

It keeps track of what type of variale it is

**What does dynamically typed mean?**

Statically typed programming languages do type checking (the process of verifying and enforcing the constraints of types) at compile-time as opposed to run-time. Dynamically typed programming languages do type checking at run-time as opposed to Compile-time.

**What is a literal**

Anything. Any value

**Useful links on python variables**
1)  [Link](http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html#other-languages-have-variables)

2)  [Link](http://anh.cs.luc.edu/python/hands-on/3.1/handsonHtml/variables.html)

3)  [Link](http://foobarnbaz.com/2012/07/08/understanding-python-variables/)

4)  [Link](http://www.diveintopython.net/native_data_types/declaring_variables.html)

# Type

Tells you what var type it is

[Jupyter notebook](http://localhost:8888/notebooks/My_code/Types.ipynb)

# Escapes

Backslash and then the symbol you want to escape


**Different ways of solving the same problem**
```
print("""Morty:\"I mean, why would a pop-Tart what to live in a toaster, Rick? I mean, that would be like the scariest place
     for them to live. You know what I mean?\" """)

print('Morty:"I mean, why would a pop-Tart what to live in a toaster, Rick? I mean, that would be like the scariest place for them to live. You know what I mean?" ')

print("Morty:\"I mean, why would a pop-Tart what to live in a toaster, Rick? I mean, that would be like the scariest place for them to live. You know what I mean?\" ")
```
# Numbers

```
print(10 % 3) #Modulo
# output = 1
```
# Functions

help() - gives a brief summary of a function **Don't forget to quit by resetting the kernal**

len()- returns the number of items in a container. eg. returns the number of items in a list

def (don't forget the colon)
