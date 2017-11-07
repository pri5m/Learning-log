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

# The sorting problem

Input: A sequence of n numbers  [a1,a2,...,an][a1,a2,...,an] 

Output: A permutation(reordering)  [a′1,a′2,...,a′n][a1′,a2′,...,an′]  of the input sequence so that  [a′1<=a′2...<=a′n][a1′<=a2′...<=an′]

# Popular sorting algorithms
- Bubble

- Insertion

- Selection

- Merge sort

- Quick sort

# Bubble sort

The bubble sort algorithm got its name from the way bubbles rises to the surface.
The largest bubble will reach the surface first.
The second largest bubble will reach the surface next.
e.t.c.

It makes multiple passes through a list. It compares adjacent items and swaps them if they are out of order.

**Psuedo code**

```
bubbleSort( A ):
    swapped = True
    WHILE swapped 
        swapped = False 
        FOR j<- 0 to length(A) -1
            IF A[i] > A [A+1] then
                swap (A[i], A[A+1])
                swapped = True
            end IF
        end FOR
end bubblesort
```
**My actual code**

```
my_list = [1,4,5,1,1,3,2]

def bubbleSort(my_list):
    swapped = True
    while swapped:
        swapped = False
        for i in range(0, len(my_list)-1):
            if my_list[i] > my_list [i +1]:
                my_list[i], my_list[i+1]= my_list[i+1], my_list[i]
                swapped = True
    return None

print(my_list)
bubbleSort(my_list)
print(my_list)
```

**Output**
```
[1, 4, 5, 1, 1, 3, 2]
[1, 1, 1, 2, 3, 4, 5]
```

# Insertion Sort

Insertion sort is similar to sorting playing cards by hand. Imagine a deck of cards facing down on your right hand. The left hand is empty. We remove one card at a time from the talbe and insert it at the right position on the left hand. To find the right position you compare it with the cards already on the left hand --from righ to left

At all times the cards on the left hand are sorted and they are the top cards from the pile. [Cormen,2009]
```
insertionsort(A):
    FOR j <- 2 to length(A)
        key = A[j]
        #insert A[j] into sorted list A[1 ... j -1 ]
        i = j -1
        WHILE j > 0 AND A[j-1] > key
            l[j+1] = l[j]
            j -= 1                       
        l[j+1] = key  
    end FOR
end insertionsort
```
# Merge sort

Merge sort is a sorting algorithm that works by splitting an array into subarrays, sorting the individual sub arrays and joining it back up into a single, sorted array.

This is known as a *divide* and *conquer* algorithm.
```
x = [1,4,5,1,1,3,2]

def merge_sort(x):
    result = []
    if len(x) < 2:
        return x
    mid = int(len(x)/2) # calculate mid point
    y = merge_sort(x[:mid]) #split up to mid point and sort
    z = merge_sort(x[mid:]) #get the rest of the mid point and sort
    i = 0
    j = 0
    while i < len(y) and j < len(z): # loop through both lists
        if y[i] > z[j]: #if left is more than right, add to result and increment index
            result.append(z[j])
            j += 1
        else: #if right is more than left, add to result and increment right index
            result.append(y[i])
            i += 1
    result += y[i:] #we can assume this is sorted, so we add the rest of the lists based on the index
    result += z[j:]
    return result

print(x)
print(merge_sort(x))
```

Cuts it in half by finding the mid point and in half again and again and then puts it back together.

[5.11. The Merge Sort](http://interactivepython.org/courselib/static/pythonds/SortSearch/TheMergeSort.html)

- It breaks the first list element by element.

# Sorting

Understandably, we do not write our own sorting implementations each time we need to sort some data.

Python has sorting methods built into its standard library.

And it is pretty good!

# TimSort
Timsort (now used in Python, Java and Android) is a combination of the Merge Sort and Insertion Sort. In simple terms, it runs like this:

1) The input list is split into smaller lists

2) Insertion Sort sorts the smaller lists

3) Merge Sort then combines the sorted lists

HOWEVER, when the list is smaller than a set size (the minrun) then it ignores the above method and just uses Insertion Sort.

This is what makes it so fast, it is known as an *Adaptive Sort*.

[Sorting algorithums gifs](https://imgur.com/gallery/voutF)

