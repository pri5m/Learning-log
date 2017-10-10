[Lesson pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4459785-dt-content-rid-7897048_2/courses/1718-CM6114/4_Lists_and_Loops_InClass.pdf)

# Review
Write a function get_number that takes two arguments a string and a number and prints the string
if the number is positive else returns 0. Then use the input function to get a string and a number
from the user. Call the function for the values that the user has given.
```
def get_number(num, the_string):
    return

num = int(input("Type in a number here: "))
the_string = input("Type in a string here: ")

get_number(num, the_string)
    
if num % 2 == 0:
    print(the_string)
else:
    print("0")
```
