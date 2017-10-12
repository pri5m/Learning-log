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

**Command prompt**

eg.
```
pip install termcolor

```
eg. termcolor package
```
import sys
from termcolor import colored, cprint #https://pypi.python.org/pypi/termcolor/1.1.0

cprint('Hello world', 'red', attrs=['reverse', 'blink'])

text = colored('Hello world!', "red", attrs=['bold'])
print (text)
```
# Virtual Environments (virtual env)
Picture this: You are given a project to work on in a team. You install some packages, write some
code and push it to git. Your team-mates say they cannot get it to run.

Why can they not get it to run?
• Modules not installed
• Modules won’t install
6
• Different operating system
• Different Python version
Any number of these and more.

# VirtualEnv

pip installs packages globally by default. This means your Python code is always affected by the
current state of your system. If you upgrade a package to the latest version that breaks what you
are working on, it will also break every other project that uses that system.
VirtualEnv aims to address this. This package creates an isolated Python environment in a
directory with your name of choice.

From here you can, specify Python versions, install packages and run code.
virtualenv <environment_name>

That is how you get started. Do not type this yet!

**Command prompt**
```
Microsoft Windows [Version 10.0.14393]
(c) 2016 Microsoft Corporation. All rights reserved.

C:\Users\c1712480>pip install <termcolor>
The syntax of the command is incorrect.

C:\Users\c1712480>pip install termcolor
Collecting termcolor
  Downloading termcolor-1.1.0.tar.gz
Building wheels for collected packages: termcolor
  Running setup.py bdist_wheel for termcolor ... done
  Stored in directory: C:\Users\c1712480\AppData\Local\pip\Cache\wheels\de\f7\bf\1bcac7bf30549e6a4957382e2ecab04c88e513117207067b03
Successfully built termcolor
Installing collected packages: termcolor
Successfully installed termcolor-1.1.0

C:\Users\c1712480>cd Desktop

C:\Users\c1712480\Desktop>cd Semester_1
The system cannot find the path specified.

C:\Users\c1712480\Desktop>cd Semester_1
The system cannot find the path specified.

C:\Users\c1712480\Desktop>virtualenv comp_thinking
'virtualenv' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\Desktop>pip install virtualenv
Collecting virtualenv
  Downloading virtualenv-15.1.0-py2.py3-none-any.whl (1.8MB)
    100% |################################| 1.8MB 546kB/s
Installing collected packages: virtualenv
Successfully installed virtualenv-15.1.0

C:\Users\c1712480\Desktop>virtualenv comp_thinking
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\Desktop\comp_thinking\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\Desktop>Scripts\activates
The system cannot find the path specified.

C:\Users\c1712480\Desktop>cd comp_thinking

C:\Users\c1712480\Desktop\comp_thinking>cd scripts

C:\Users\c1712480\Desktop\comp_thinking\Scripts>cd activate
The directory name is invalid.

C:\Users\c1712480\Desktop\comp_thinking\Scripts>activte
'activte' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\Desktop\comp_thinking\Scripts>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\Desktop\comp_thinking\Scripts

12/10/2017  12:04    <DIR>          .
12/10/2017  12:04    <DIR>          ..
12/10/2017  12:04             2,213 activate
12/10/2017  12:04               784 activate.bat
12/10/2017  12:04             8,325 activate.ps1
12/10/2017  12:04             1,137 activate_this.py
12/10/2017  12:04               508 deactivate.bat
12/10/2017  12:04            98,189 easy_install-3.5.exe
12/10/2017  12:04            98,189 easy_install.exe
12/10/2017  12:04            98,161 pip.exe
12/10/2017  12:04            98,161 pip3.5.exe
12/10/2017  12:04            98,161 pip3.exe
12/10/2017  12:04            42,136 python.exe
12/10/2017  12:04         3,942,552 python35.dll
12/10/2017  12:04            42,136 pythonw.exe
12/10/2017  12:04            98,168 wheel.exe
              14 File(s)      4,628,820 bytes
               2 Dir(s)  135,513,509,888 bytes free

C:\Users\c1712480\Desktop\comp_thinking\Scripts>cd ..

C:\Users\c1712480\Desktop\comp_thinking>Scripts\activate

(comp_thinking) C:\Users\c1712480\Desktop\comp_thinking>deactivate
C:\Users\c1712480\Desktop\comp_thinking>
C:\Users\c1712480\Desktop\comp_thinking>Scripts\activate

(comp_thinking) C:\Users\c1712480\Desktop\comp_thinking>pip install colorama
Collecting colorama
  Downloading colorama-0.3.9-py2.py3-none-any.whl
Installing collected packages: colorama
Successfully installed colorama-0.3.9

(comp_thinking) C:\Users\c1712480\Desktop\comp_thinking>pip freeze\ requirments.txt
ERROR: unknown command "freeze\" - maybe you meant "freeze"

(comp_thinking) C:\Users\c1712480\Desktop\comp_thinking>pip freeze requirments.txt
colorama==0.3.9

(comp_thinking) C:\Users\c1712480\Desktop\comp_thinking>
```
