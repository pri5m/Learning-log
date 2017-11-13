```
def mystery(a, result=None):
    if result is None:
        result = []
    
    for x in a:
        if isinstance(x, list):
            mystery(x, result)
        else:
            result.append(x)
    
    return result
```

mystery([1,2[1,2,4]])

```
#What to write in the exam:
result = [1]
result = [1,2]
    mystery([1,2,4], [1,2])
    result = [1,2,1]
    result = [1,2,1,2]
    result = [1,2,1,2,4]
    return [1,2,1,2,4]
```
# Travelling salesman problem

Permutaions- all possible orderings of a list

best_route_index = alldistance.index(min(alldistances))
