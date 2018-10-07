# Markdown cheatsheet

# Headings

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

# Formatting

### Line formatting

Text line.
Text line with no line gap between other line merges the lines

Text line.

Text line with line above creates new paragraph.

### Text formatting

*A single star for italics*

**Double star for bold**

Link description in square brackets[] and the link in round brackets ()

[Link description](https://www.cardiff.ac.uk/study/undergraduate/courses/2018/applied-software-engineering-bsc)

### Code formatting

```
Triple ``` for generic code or text. Can be found to the left of the number 1 on your keyboard
```

Use of the ``` ``` ``` followed by the name of the coding language will cause github to auto add coloring for that code snippet (optional)


For example for SQL:

```SQL
SELECT * FROM customers;
```

Or for Python:
```Python
def fib(n):
     a, b = 0, 1
     while a < n:
         print(a, end=' ')
         a, b = b, a+b
     print()
 fib(1000)
```

# Note

There are various markdowns used and supported by different software. This is the github markdown version. Atom and Intellij use slightly different variations. So bare that in mind when creating a README.md doc. To find out the formatting supported by other software, have a google. They are all pretty similar to each other but with slight differences.
