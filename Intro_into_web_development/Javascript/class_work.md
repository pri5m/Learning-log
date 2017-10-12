# Class work

Class slides: Documents/Semester_1/Intro%20to%20web%20development/Javascript/JavaScript_Slides.pdf

# 0 Hello world
```
<html>
  <head>
    <title>JS HelloWorld</title>
  </head>
  <body>
    <h1> HelloWorld in JS</h1>
    <p> ... but this is written in html?!?<br>
      open the console in the browser to see the js output</p>
    <script>
      console.log('Hello World');
      console.log('Hello World');
      console.log('Hello World');
      console.log('Hello World');
    </script>
  </body>
</html>

```
**Problems with using console.log**

- Takes longer to execute

- Tend to use it as a debug tool but is visible to everyone who visits the page. Should be careful

# Basics

- camelCase

- Semicolons at the end ofeach statement line

- Indentation not strict (but do it anyway)
```
<html>
<head>
  <title>JS Basics</title>
</head>
<body>
  <h1> JavaScript Basics</h1>
  <p> open the console in the browser</p>

<script>
    var x = 0;
    console.log(x);
    x+=4;
    console.log(x);
    x+='5';
    console.log(x);

</script>
</body>
</html>
```
# 1 Fundamentals

- Literals (100, 'Holly')

- Variables (best practice to put var when variable used- although not nessecary for code to run)

- Operators ( eg. + * ect.)

```
<html>
<head>
  <title>JS Fundamentals</title>
</head>
<body>
  <h1>Fundamentals</h1>

<script>
  var name = 'Ian ';
  console.log(name+ 'Cooper');
  var x = 100;
  console.log(x+x);  	//what is x now? //Will print 200 but x will still be 100
  console.log(x*2); 	//what is x now? //Prints 200 but x is still 100
  x+=4;				//what is x now? //X will now be 400 as it is assigned
  var a = 4;
  console.log(a); //4
  console.log(a++); // use a and then increment it //4
  console.log(a); //5
  console.log(++a); //increment a and then use it //6

</script>
</body>
</html>
```

# 2 Basic rules

- JS: dynamically, weakly typed language

- Python: dynamically, strongly typed language

- Java: statically, strongly typed language

**Dynamic**- Literals have a type

**Static**- Vars have a type

**Weak**- the type of value (literal) may change

**Strong** - type of a value (literal) can't change

# 3 Arrays

Arrays are list like structures

```
<html>
<head>
  <title>JS Arrays</title>
</head>
<body>
  <h1>Arrays</h1>

<script>
  var myArray = ['foo', 'bar', 'baz'];
  console.log(myArray);
  myArray.push('qux');
  console.log(myArray);
  console.log(myArray.pop());
  console.log(myArray);
  console.log(myArray.pop());
  console.log(myArray);
  console.log(myArray.pop());
  console.log(myArray);


</script>
</body>
</html>
```
**Debugger tools**
Double click on the array in the console and right click and can watch it in the watch list to keep an eye on what the variables are doing.

[MDN Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

- array.shift(...) The shift() method removes the first element from an array and returns that element.

- array.unshift(...) The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.

- array.indexOf(...) The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.

- array.splice(...) The splice() method changes the contents of an array by removing existing elements and/or adding new elements.

# 4 equality

```
<html>
<head>
  <title>JS Equality</title>
</head>
<body>
  <h1>Equality</h1>
  <p> there are two types of equality in js, </p>

  <p></p>
  <script>
    var a = 'foo';  //primitive
    var b = 'foo';  // primitive
    var c = new String('foo');  //object
    var d = new String('foo');  //object
    console.log(a==b);  // true
    console.log(a==c);  // true

    console.log(a===b);  // true
    console.log(a===c);  // false
    console.log(d===c);  // false

  </script>
</body>
</html>
```

# 5 Loops

```
<html>
<head>
  <title>JS Loops</title>
</head>
<body>
  <h1>Loops and the debugger</h1>
  <p> Use the debugger to view the variables during each iteration of the loop.</p>
  <p> ?? In this loop, for each element in the array,  pop off an element. ?? </p>
  <p> ?? after the loop, log the array (which should be empty). ?? </p>
  <p> Why does this not work? Use the debugger tools to investigate. </p>

  <p></p>
  <script>
    var array1 = ['h','e','l','l','o']
    // this works as expected
    for(var i=0;i<array1.length;i++){
          console.log(array1[i]);
    }
    // use the debugger to work out why this doesn't
    for(var i=0;i<array1.length;i++){
      console.log(array1.pop());
    }
    // Two reasons:
    // As i is increasing and the list is decreasing
    // Writing it in reverse
    
    // Get rid of the i ++
    // Before the loop, store the length
    // While loops ect.
    console.log(array1);
  </script>
</body>
</html>
```
Can set a var and is an index. Use i the index of the value you are looking at so must explicitly ask for the index.

# 6 Functions

A block of code that can be called multiple times and preforms a particular task. Takes an input, preforms some operations, and (generally) returns an output.

```
<html>
<head>
  <title>Functions</title>
</head>
<body>
  <h1>Functions</h1>
  <p> </p>
  <script>
    function myFunc(){
      var b='foo';
      console.log(b);
      return b;
    }

    function double(input){
      return input *2;
    }

    console.log(myFunc());
    // console.log(b);   //It will error as it is not defined. It is only applicable within the function- it does not exist. The scope                              of var b is limited as it is only available within the function.
    console.log(double(5));

  </script>
</body>
</html>
```
Always decide what scope you want your var to be- global or local

# 7 Scope

```
<html>
<head>
  <title>JS Scope</title>
</head>
<body>
  <h1>Scope</h1>
  <p>JavaScript does not have block scope (like python) so variables declared within a
    block ( {between the curly braces} ) are scoped to the containing function or script.  </p>

  <p>Unlike python, variables declares without the var keyword are,
    if not already declared at an outer scope,
     declared within global scope.  </p>
  <script>
// a is in a {} but not a function so is global
    for(i=0;i<10;i++){
      // a=i*10;
      var a=i*10;
      console.log(a);
    }
    console.log(a*10);

// b is within a function so is local to that function
    var myFunc = function(){
      var b='foo';
      // b='foo';
      console.log(b);
    }
// var b='bar';
    myFunc();
    console.log(b);

  </script>
</body>
</html>
```



