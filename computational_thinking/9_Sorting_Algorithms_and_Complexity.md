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
*will be in exam**
