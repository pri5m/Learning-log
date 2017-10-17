# DOM- Document Object Model

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. This document can be either displayed in the browser window, or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

# DOM  tree

Structured representation of a document

**Up** Parent node

**Down** children/child nodes, first child, last child

**Side** previous sibling/ next sibling

# positioning

The DOM script must be at the end of the body. It had to be executed last.

```
<html>
  <head>
    <title>DomRendering</title>
    <!-- Move this -->
    <script>
      console.log(document.getElementById('header'));
    </script> <!--Does not work here-->
  </head>
  <body>
    <h1 id="header">Why does this not work?</h1>
    <script>
      console.log(document.getElementById('header'));
    </script> <!-- Works here-->
  </body>
</html>
```
Can put it in the head and then call at the bottom of the body, this will also work:
```
<html>
  <head>
    <title>DomRenderingWorking</title>
    <script>
      function loaded() {
        //why does this work?
        console.log(document.getElementById('header'))
      };
    </script>
  </head>
  <body onload="loaded()">
    <h1 id="header">Heads Up</h1>
  </body>
</html>
```

# What commands have we used so far?
• document.body.childNodes is an array of nodes

• document.body.firstChild is the first child

• document.body.lastChild is the last child

• document.getElementById('header'); returns the first

• [someElement].innerHTML = “…” sets the html of a given element
--------------------------------------------------------------------------
# Similar Commands:
• document.getElementByClassName('myClass'); returns the first

• document.getElementsByClassName('myClass'); returns array of elements

• document.querySelector(".myclass"); uses css queries, returns the first

• document.querySelectorAll(".myclass"); uses css queries, returns array

# New commands: Creation of new content

• document.createElement(" div "); returns an element

• document.createTextNode(" some text "); returns a text node

• [someElement].appendChild(newElement); adds newElement to end of someElement

```
// create a p element <p></p>
var newP = document.createElement("p");
// add a text node to our new element <p>HelloWorld</p>
newP.appendChild(document.createTextNode("HelloWorld"));
// add the new element to an existing element in the DOM
document.getElementById('myDiv').appendChild(newP);
```

# DOM manipulation

```
<!DOCTYPE HTML>
<html>
  <body>
    <h1 id="header1">Im marvulus wiv speling. </h1>
    <h1 id="header2">And OK at JS </h1>

    <script>
      setTimeout(function callback() {
        document.getElementById('header1').innerHTML = "I'm marvellous at spelling.";
      }, 3000);

      setTimeout(function callback() {
        document.getElementById('header2').innerHTML = "And great with JS";
      }, 5);
    </script>
  </body>
</html>
```

# Accessing form data 2 ways

**We already have an idea about IDs:**
• document.getElementById("data")

• We can get the value by using .value;

document.getElementById("data").value

```
<form>
Comments:
<input type="text" id ="data" >
</form>
```
```
var x = document.getElementById("data").value
```
  
**Better way:**
• forms["myForm"]["data"]
```
<form name = "myForm">
Comments:
<input type="text" name ="data" >
</form>
```
```
var x = document. forms["myForm"]["data"].value
```

# Ex1 Line Reader
```
<!DOCTYPE HTML>
<html>
  <head>
    <title>lineReader</title>
  </head>
  <body>
    <h1>Article</h1>

    <button onclick="nextLine()">Next Line</button>    //Linking the html to the function
    <article id="newsArticle"></article>

    <script>
      var lines = ['line1', 'line2', 'line3', 'line4'];  //Hard coded list of words
      var count = 0;    //Counter to keep track of how many items of the list have been called. Set to 0 here

      function nextLine() {    //Function that displays an element from thhe list when the button is pressed
        if (count < lines.length){  //check so that the code only executes if the count is less than the length of the array, if not                                            then it stops
          var p = document.createElement('p');    // A variable (p) that creates an element called p
          p.appendChild(document.createTextNode(lines[count]));    
                //Adds a child element to p. p creates a text node from the list according to the line count, which is increasing each                   time the button is pressed, displaying the next element in the list each time
          document.getElementById('newsArticle').appendChild(p);  
          // Puts the variable 'p' into the newsArticle, which displays after the button is pressed
        }
        else {
            return;   // If there are no more elements to display because the count < lines.length statement is no longer true, then                              nothing will be executed
        }
        count = count + 1;    // increases the count increment by one everything the button is pressed

      }
      // don't forget to link the html to the js function
    </script>
  </body>
</html>
```
Prints out elements from the hard coded list one at a time when the button is pressed

# Events
• onclick="f1(event)"

• function f1(e){…}

• Sets Window as the context for ‘this’.

• [Element].onclick = f2;

• function f2(e){…}

• Sets ‘this’ context at the calling element. 

# Event listeners: more versatile way to add event listener
Use:
• [element].addEventListener( <listenerType>, function);
  
• Different Listener types:

• click

• mouseover

• mouseout

- dblclick  : double click

```
document.getElementById('head1').addEventListener('click', f1);
document.getElementById('head2').addEventListener('mouseover', f2);
document.getElementById('head3').addEventListener('mouseout', f3);
document.getElementById('head3').addEventListener('dblclick', f3);
```
# Events: bubbling

• When an event is triggered on an element, the event bubbles up the DOM.

• If listeners are attached to parent elements, they will be executed.

• The event can be stopped: *e.stopPropagation();*

```
<ul id='ul'>
<li>one</li>
<ul id='ul_ul'>
<li id='ul_ul_li'>one.one</li>
<li>one.two</li>
<li>one.three</li>
</ul>
<li>two</li>
</ul>
```

# Events: capturing/trickling

For bubbling:

• [El].addEventListener('click', f1);

• Events can also trickle down.

For trickling:

• addEventListener('click', f1, true);

```
<ul id='ul'>
<li>one</li>
<ul id='ul_ul'>
<li id='ul_ul_li'>one.one</li>
<li>one.two</li>
<li>one.three</li>
</ul>
<li>two</li>
</ul>
```

# Validation

Can use HTML5 Form validation:
• Attributes like:
•     Required
•     Pattern
• Email element.
https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Data_form_validation

• Automatic form validation not in all browsers (IE9)

https://www.netmarketshare.com/browser-marketshare.aspx?qprid=2&qpcustomd=0&qpcustom=

• Can use JS for Validation

• Make it more specific

```
<html>
  <body>
    <form>
      <p> using the builtin html5 patern attributes: match to regexp.
        red or blue? <input type ='textbox' required pattern="red|blue"> </input><br>
        6 digit no. <input type ='textbox' required pattern="[0-9]{6}"> </input><br>
      email <input type ='email' required> </input><br>
      <input type='submit'value='non scripted submit'>
    </form>

    <form>
      name <input id = 'name' type ='textbox'> </input><br>
      <input type='submit'value='scripted submit' onclick="validate()">
    </form>

    <script>
      function validate(){
        var fail = true;
        var name = document.getElementById('name').value;
        if (name.length>10){
          alert('too long');
        }
        // Deal with form submission.
      }
    </script>
  </body>
</html>
```

# JS Form Validation:

• onsubmit states whether the form will be sent or not

– true or false.

• return validate()

• Is the return value from the validate function. 
```
<form onsubmit ="return validate()” name = "myForm">
Description (max length 10 words) <br>
<input type = 'text' name="ta"> <br>
<input type = 'submit'>
</form>
```
```
function validate(){
var pass = true;
var text = (document.forms[myForm][ta].value);
var words = text.split(" ");
console.log(words);
if (words.length>10){
alert('too long');
pass = false;
}
return pass;
}
```
