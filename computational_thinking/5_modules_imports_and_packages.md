# Ex 1
```
import random

def dice ():
    return(random.randrange(1, 7))

dice()
```

use a random.seed(0)

Use the same starting point for generating random numbers. Keeps it consistent between systems. Use in assignments

```
Specifying a seed value allows reproducability of results.
In [3]: random.seed(0)
print(f'{dice()} {dice()} {dice()}')
random.seed(0)
print(f'{dice()} {dice()} {dice()}')
print(f'{dice()} {dice()} {dice()}')
random.seed(0)
print(f'{dice()} {dice()} {dice()}')
print(f'{dice()} {dice()} {dice()}')
4 4 1
4 4 1
3 5 4
4 4 1
3 5 4
```
