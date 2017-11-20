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

# Practice Q2
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
