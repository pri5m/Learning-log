# Class work

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
# Fundamentals

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
  console.log(a++); // use it and then increment it //4
  console.log(a); //4
  console.log(++a); //increment a and then use it //5

</script>
</body>
</html>
```

