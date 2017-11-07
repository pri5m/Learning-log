# Intro exercise
Exercise: 
Write a recursive and iterative function to reverse a string
```
def recursiveStringInterval(x):
    res = ""
    for i in range((len(x)),0,-1):
        res=res+x[i-1]
    return res

print(recursiveStringInterval("Hey"))

#Output... yeH
```
*will be two questions like that in the exam, on explaining recursive code*

# Algorithms

Algorithm is computational procedure that takes some values, or set of values, as input and prodcuses some value, or set of values as ouput. An algorithm thus is a sequence of computational steps that transforms the input into output. 
[Cormen,2009]

In general an algorithm is used as a tool to solve computational problems. The problem specifies a desired input/output relationship and the algorithm specifies a step by step procedure to achieve this relationship.

A correct algorithm will produce the correct output for each input. Some times incorect algorithms are acceptable if the error rate is "acceptable".

