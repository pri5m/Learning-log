[Llesson pdf](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4496588_1&course_id=_381769_1&launch_in_new=true)

# Interview Q1
```
def mystery1(x,l=[]):
  for i in range(x):
    l.append(i*i)
  print(l)
  
mystery1(3)
mystery1(2,["a","b"])
mystery1(2)

```
*Not like exam q, used in python interviews*

```
mystery(3)
x=3
l=[]

for i in range (3)
i = 0
[].append[0*0]
[0].append[l*l]
i = 2
[0,1].append(2*2)

l = [0]
l = [0,1]
l = [0,1,4]
```
```
mystery(2,["a","b"]

x = 2
list = ["a","b"]

for i in range(2)
i = 0
["a","b"].append(0*0)
i = list
["a","b",0].append(1,1)

l = ["a","b",0]
l = ["a","b",0,1]
```
```
[0, 1, 4]
['a','b', 0, 1]
[0, 1, 4, 0, 1]
```

# Practice Q2

*pulled from exam*
```
def mystery2(a,b):
  if b == 0:
    return 0
  if b % 2 == 0:
    return mystery2(a+a, int(b/2) )
  else:
    return mystery2(a+a,int( b/2)) + a

mystery2(2,5)
```
Answer
```
a = 2
b = 5

if b != 0
if b%2 !=0
else 
  return mystery2(2+2, int (5/2)) +2

a = 4
b = 2

if b!= 0
if b%2 == 0
  return mystery(4+4, int(2/2))

a = 8
b = 1

if b!=0
if b%2 !=0
else
  return mystery2(8+8, int(1/2)) + 8
  
a = 16
b = 0

b == 0
  return 0

2 + 0 + 8 + 0 = 10
```
**What to write in the exam**
```
return mystery2(4,2)+2
return mystery2(8,1)
return mystery2(16,0)+8
return mystery2(0)
2+0+8 =10
```
# pygame

pip install pygame

# Practice q 3

```
def mystery(a, b):
  if a and b :
    if a[0] > b[0]:
      a, b = b, a
    return [a[0]] + mystery(a[1:], b)
  return a + b
  
mystery([2,4,5,7],[1,2,4,9])
```
**Answer**
```
a = [2,4,5,7]
b = [1,2,4,9]

a[0]>b[0]
2>1
a = [1,2,4,9]
b = [2,4,5,7]

return [1] + mystery([2,4,9], [2,4,5,7])
return [1] + [2] + mystery([4,9], [2,4,5,7])
return [1] + [2] + [2] + mystery([4,5,7], [4,9])
return [1] + [2] + [2] + [4] + mystery([5,7], [4,9])
return [1] + [2] + [2] + [4] + [4] + mystery([9], [5,7])
return [1] + [2] + [2] + [4] + [4] + [5] + mystery([7], [9])
return [1] + [2] + [2] + [4] + [4] + [5] + [7] + mystery([], [9])
return [1] + [2] + [2] + [4] + [4] + [5] + [7] + [9]
[1,2,2,4,4,5,7,9]
```
# question 4
```
def mystery2(w):
  for i in w:
    if i == 'a':
      pass
      print("print hello")
     else:
      print(i)

mystery2("a test")
```
**Answer**

```
print hello
t
e
s
t
```

# question 5

```
def mystery3(w):
ctr = 0
for n in w:
  pritn(n)
  if isinstance(n, tuple):
    break
  ctr += 1
 return(ctr)
 
mystery3([10,30,44(1,20),40,(2)])
```
Position of the first tuple in a list

Output - 3
