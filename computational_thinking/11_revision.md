[TSP.ibpn](https://learningcentral.cf.ac.uk/webapps/streamViewer/streamViewer?cmd=view&streamName=alerts&globalNavigation=false#)

[Exam example ibpn](https://learningcentral.cf.ac.uk/webapps/streamViewer/streamViewer?cmd=view&streamName=alerts&globalNavigation=false#)
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

A **greedy algorithm** is an algorithmic paradigm that follows the problem solving heuristic of making the locally optimal choice at each stage with the hope of finding a global optimum.

