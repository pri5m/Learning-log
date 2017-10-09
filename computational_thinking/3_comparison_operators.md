[Lesson notes](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4458206-dt-content-rid-7878557_2/courses/1718-CM6114/3_Conditionals_Flow_Control_InClass.pdf)

# Review
Correct code
```
def good_morning (name):
    print("good morning " + name)
    return
    
good_morning("Alex")
```
good morning Alex

I wrote print = ("good morning" + name) which is wrong. 

The = is not needed as print is a function and cannot be defined.

# Identity vs comparison

```
print(a is b) # identity (True)
print(a == b) # equality (True)
```

```
make = "Tesla"
capacity = 80000
year = 2016

print(make == "Tesla" or make == "Tesla")
print(make == "Tesla" and make == "Tesla")
print(capacity < 80000 and capacity > 60000)
print(capacity > 60000 or capacity < 100000 and year == 2014 or year == 2016)
```
True, True, False, True

# Flow control

```
name = "Rincewind"
age = 32

print("My name is " + name)
print("I am " + age)

if age > 100:
    print("I am over one hundred years old!")
    print("this will only print if Rincewind is over 100") #as long as you stay indented, this is all part of the if
print("this will print regardless")
```
# Else if statements
```
pet = "Lizard"

if pet == "Dog" or pet == "Cat":
    print("four legged friend")
elif pet == "Lizard" or pet == "Dragon":
    print("Reptillian rapport")
elif pet == "Fish":
    print("Aquatic amigo")
else:
    print("What the smeg is that?!")
```

# User inputs

```
num = int(input("Type in a number: "))


if num > 20:
    print(num * 2)
else:
    print(num / 2)
```
