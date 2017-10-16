[PDF lesson plan](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4468702-dt-content-rid-7950270_2/courses/1718-CM6114/6_Advanced_IO_Conditioning.pdf)

# argv

allarguements.py

```
from sys import argv

print(argv)
length = len(argv)

print("Number of arguements: {}" .format(length) )

print("The arguements are: {}" .format(argv))

```
**output**
```
PS C:\Users\c1712480\Documents\Semester_1\Computational_thinking\Work\My_code> python allarguements.py hey, awesome, coo
lio
['allarguements.py', 'hey', 'awesome', 'coolio']
Number of arguements: 4
The arguements are: ['allarguements.py', 'hey', 'awesome', 'coolio']
PS C:\Users\c1712480\Documents\Semester_1\Computational_thinking\Work\My_code>

```
