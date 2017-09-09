# A
**Arguments**

**argv** -Argument variable. This variable holds the arguments you pass to your Python script when you run it.
# B
# C
**close()** -Close a file

**Command**
# D
**def** -Create a function 'def'
# E
**Escape symbols** -Used so that punctuation and grammar can be used and not mistaken as being 'code' symbols
# F
**Float** -A number containing a decimal point eg. 3.6234232

**float(raw_input())** -Input a float number

**Functions** -They name pieces of code the way variables name strings and numbers. They take arguments the way your scripts take argv. Using 1 and 2 they let you make your own "mini-scripts" or "tiny commands."
# H
# I
**Import** -This is how you add features to your script from the Python feature set. Rather than give you all the features at once, Python asks you to say what you plan to use. This keeps your programs small, but it also acts as documentation for other programmers who read your code later.

**input()** -The input() function will try to convert things you enter as if they were Python code, but it has security problems so you should avoid it.

**int(raw_input())** -Converts a string to a number. Does not work for floating numbers
# J
# K
# L
# M
**Modifiers**

**Modules** -little things you import to make your Python program do more. eg. the sys module. They are also called 'libraries' by some programmers

**Modulo** -They tell Python to take the variable on the right and put it in to replace the %s with its value. eg. %d, %s, %r. %r is used for debugging and %s is used for displaying to the user. Also known as formatters
# N
**Number** -Sometimes numbers have to be converted from a string into a number
# O
**open()** -Open a file

**Operations**
# P
**Parameter**

**Parenthesis** -() Used to separate out bits of code or to contain extra information in a function

**print** -Displays the line in a terminal

**Pydoc** -Used in the terminal, provides information on functions and other python features. eg. python -m pydoc raw_input
# Q
# R
**raw_input** -Takes an input from a user

**readline()** -The readline() function returns the \n that's in the file at the end of that line. Add a , at the end of your print function calls to avoid adding double \n to every line. Inside readline() is code that scans each byte of the file until it finds a \n character, then stops reading the file to return what it found so far. The file f is responsible for maintaining the current position in the file after each readline() call, so that it will keep reading each line.

**round()** -A function that rounds floating point numbers
# S
**seek()** -Deals with bytes

**String** -How you make something that might be given to a human. Numbers can be written in a string but will not act as a number
# T
**Terminal** -eg. Powershell
# U
# V
**Variable**
# W
# X
# Y
# Z

## Symbols
: colon- use after the closing parenthesis in an argument

**^** (caret)- Points to where the problem is in the terminal

**#** (hash)- Used for creating a comment in the code

**+** Add

**-** Subtract

* Multiplication

**/** Divide

**%** Percent

**>** Greater than

**<** Less than

== Tests if two things are true

= Assigns a value eg. for variables

+= That means x = x + y is the same as x += y

**<=** Less than or equal to

**>=** Greater than or equal to


| Escape        | What it does  |
| ------------- | ------------- |
| \\            | Backslash \   |
| \'            | Single-quote  |
| \"            | Double-quote  |
| \a            | ASCII bell (BEL)|
| \b	          | ASCII backspace (BS)|
| \f	          | ASCII formfeed (FF)|
| \n	          | ASCII linefeed (LF)|
| \N{name}	    | Character named name in the Unicode database (Unicode only)|
| \r	          | Carriage Return (CR)|
| \t	          | Horizontal Tab (TAB)|
| \uxxxx	      | Character with 16-bit hex value xxxx (u'' string only)|
| \Uxxxxxxxx	  | Character with 32-bit hex value xxxxxxxx (u'' string only)|
| \v	          | ASCII vertical tab (VT)|
| \ooo	        | Character with octal value ooo|
| \xhh	        | Character with hex value hh|


| Command        | What it does  |
| -------------- | ------------- |
| close          | Closes the file. Like File->Save.. in your editor.|
| read           | Reads the contents of the file. You can assign the result to a variable.|
| readline       | Reads just one line of a text file.|
| truncate       |Empties the file. Watch out if you care about the file.|
| write('stuff') |Writes "stuff" to the file.|
