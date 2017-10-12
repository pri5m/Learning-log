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
# Modules and Packages

A Python module is just a .py file, which you can import directly.
import config (relates to config.py somewhere on your system)

A package is a collection of Python modules that you can import all of, or just import the
modules you want. 

For example:

import random (all modules in random package)
from random import randint (importing module from packages)

# Import dos and don’ts
You can (and will) import many modules in one script, PEP asks that you follow this structure:

import standard_library_modules

import external_library_modules

import local_modules

More info on this and other styles can be found here

You will also see that some people will import multiple modules in one line:
import os, sys, csv, math, random

Do not do this, it makes your code hard to read and modularise
However, it is good to import multiple modules from the same package in one line:

from random import randrange, randint

# Importing files

**City.py**
```
name = "London"
population = "Large"
country = "England"

def print_city():
    city = ('{} {} {}'.format (name, population, country))
    return city
```

**Main.py**
```
import city

print(city.print_city())
```

**Powershell -main.py**
```
London Large England
```

**Corrections**
Added brackets in first line of function

tried running city.py

returned print_city()

returned city()

removed print(print_city) from city.py

# PIP

[Explanation](https://packaging.python.org/guides/tool-recommendations/)

[PyPI](https://pypi.python.org/pypi)
