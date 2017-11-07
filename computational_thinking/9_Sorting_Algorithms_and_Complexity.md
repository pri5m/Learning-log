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

# What types of problems do algorithms solve?
**Routing problems.**
- information packages select routes between any nodes on a computer network?

- What is the optimal set of routes for a fleet of vehicles to traverse in order to deliver to a given set of customers?

- shortest route?

**Search problems**

- find pages where information resides

**Cryptography e.t.c.**

# What types of problems do algorithms solve?

**Optimisation problems:**
We usually are looking to find "the largest, smallest, fastest, cheapest" solution while a set of constraints are applied. 
For example you might be looking to get the maximum grade on an assigment while spending less than 5 hours on doing it. 
The first part is called the objective function that we are looking to maximise (or minimise) and the second part is the set of constraints, which can be empty.

# Theoritical analysis

**How do we evaluate algorithms?**

- time complexity (speed)

- space complexity (storage)

The order of growth of the running time of an algorithm:

- provides a metric of the efficiency of the algorithm

- allows to compare the perfomance across different algorithms

Many notations exist to describe this.
They describe worst-case running time as a function of the size of input.

# O-Notations

O(X) --> 'of the order X'

Argorithm's time or space requirments grows proportionaly to X
```
for x in range(n):
    print(x)
```

Now the operations depend on the size of N, so we call this O(n)

**What about this?**
```
for x in range(n):
    for y in range(n):
        print(x)
```
Now the run time depends on the size of N but it loops through N within N? This makes the complexity O(n^2) or O(n*n)

O(n^2)represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(n^3),O(n^k)


