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
make = "Tesla"
capacity = 80000
year = 2016

print(make == "Tesla" or make == "Tesla")
print(make == "Tesla" and make == "Tesla")
print(capacity < 80000 and capacity > 60000)
print(capacity > 60000 or capacity < 100000 and year == 2014 or year == 2016)
```
True, True, False, True
