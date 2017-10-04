# 1_introduction

[link to the pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4448637-dt-content-rid-7827944_2/courses/1718-CM6114/1_Introduction.pdf)

*Computational Thinking is the thought processes involved in formulating problems and their
solutions so that the solutions are represented in a form that can be effectively carried
out by an information-processing agent.*
~Jeannette Wing

**Running IPYNB Notebooks**
1. Download (save link as) the lecture/homework from learning central
2. Save into the appropriate directory
3. Shift + Right click on the folder and click ’Open Command Window here’
4. Type jupyter notebook
5. If a browser does not open then go to: http://localhost:8888
6. Open the file or create a new one.
7. Use markdown for text and code for Python
8. Run code with the Play button (or shift+enter)

**Homework**
```python
name = "<YOUR NAME HERE>"
current_year = 2016
years_to_graduate = 2019
print("Hello")
print(name)
print("You have: " + str(years_to_graduate - current_year ) + " awesome years of knowledge ahead of you")
```

Run the above code using python age.py in your command prompt/terminal
**When will the above code be wrong?** 

The code will be incorrect next year as the dates are currently fixed in defining the variables.
How would you fix that? ```python from datetime import date
current_year = date.today().year
years_to_graduate = date.today().year + 3 ```

**Why is there a + between "You are" and the age?**
To combine the string and the variable into one line.

**What do you think the str stands for on the last line? Why is it there?**
String Create a new string object from the given object. If encoding or errors is specified, then the object must expose a data buffer that will be decoded using the given encoding and error handler. Otherwise, returns the result of object.str() (if defined) or repr(object). encoding defaults to sys.getdefaultencoding(). errors defaults to 'strict'. -python -m pydoc str

**Find the documentation for print**
print(*objects, sep=’ ‘, end=’\n’, file=sys.stdout, flush=False)
*Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments.
*All non-keyword arguments are converted to strings like str() does and written to the stream, separated by sep and followed by end. Both sep and end must be strings; they can also be None, which means to use the default values. If no objects are given, print() will just write end.
*The file argument must be an object with a write(string) method; if it is not present or None, sys.stdout will be used. Since printed arguments are converted to text strings, print() cannot be used with binary mode file objects. For these, use file.write(...) instead.
Whether output is buffered is usually determined by file, but if the flush keyword argument is true, the stream is forcibly flushed.


**ADVANCED:** Call the print method with 3 arguments
```python
from datetime import date

name = "<YOUR NAME HERE>"
current_year = date.today().year #Source: https://stackoverflow.com/questions/11206489/how-to-print-next-year-from-current-year-in-python
years_to_graduate = date.today().year + 3

print("Hello")
print(name)
print("You have: " + str(years_to_graduate - current_year) + " awesome years of knowledge ahead of you")
```

Try to make some changes to the file and generate some errors.
i.e. remove one " from the name 
what happens?
``` 
 name = "<YOUR NAME HERE>
                           ^
SyntaxError: EOL while scanning string literal
```
