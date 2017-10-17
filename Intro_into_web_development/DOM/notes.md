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
