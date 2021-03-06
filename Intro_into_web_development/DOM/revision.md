# What is the DOM?

The DOM is a W3C (World Wide Web Consortium) standard.

The DOM defines a standard for accessing documents:
```
"The W3C Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document."
```
The W3C DOM standard is separated into 3 different parts:

- Core DOM - standard model for all document types

- XML DOM - standard model for XML documents

- HTML DOM - standard model for HTML documents

# What is the HTML DOM?
The HTML DOM is a standard object model and programming interface for HTML. It defines:

- The HTML elements as objects

- The properties of all HTML elements 

- The methods to access all HTML elements

- The events for all HTML elements

In other words: The HTML DOM is a standard for how to get, change, add, or delete HTML elements.

# Video notes

- Representation of  HTML (and similar languaages)

- Allows interaction with HTMl

- Organises the nodes (elements) of an HTMl page in a tree structure

**Document**

- We can access the DOM in JavaScript through the document object

- Also gives us access to page properties

- Can call methods on document to access page elements (nodes)

**index.html**
```
<script>
  # Selecting by Id
  var nav = document.getElementById("main_nav");  # Select by Id. Returns a single element(cos id). Selects the first elemt with that id (if more than one id of the same name, which there shouln't be as it should use a class insted)
  console.log(nav); #print out to the command line
  
  # Selecting by class
  var centred = document.getElementByClassName("centre"); # Selects everything with the class "centre". getElements- returns an array as more than one element might have the same class
  for(var i = 0; i < centred.length; i++){
      console.log(centred[i]);
  }
  
 # Selecting by tag name eg.<p>
 var p = document.getElementByTagName("p");  #Selects everything with the <p> tag
 for(var i = 0; i < p.length; i++) {
    console.log(p[i]);
 }
</script>
```

**Example 2**
```
<script>
  var body = document.getElementByTagName("body")[0]  # [0] is used to get the first element in the array
  
  var img = document.createElement("img");    # Creates an <img> tag
  img.src = "url";   # Adds a url to the <img> tag
  
  body.appendChild(img);  # Appends the image to the body
  
  var text = document.createTextNode("here is a paragraph");   # Creates a sting of text
  var para = document.createElement("p");  # Creates a <p> tag
  
  para.appendChild(text); # Appends the text sting to the <p> element
  body.appendChild(para); # Appends the <p> element containing the text string to the body
</script>
```
# Events

- When 'things' happen (see below) on out web pages, the browser generates events

- Can respond to events using JavaScript

element.addEventListener(type, listener, [capture]);

**Event types**

Examples of some type of events:

- Mouse Events (mousedown, mouseup, click, dbclick, mouseover)

- Touch Events (touchstart, touchend)

- Keyboard Events (keydown, keyup, keypress)

- Form Events (focus, change, submit)

- Window Events (scroll, resize)

```
var header = document.getElementById("my_header");
header.addEventListener('click', output_element);
```

Events travel thought the DOM in three phases:
```
element.addEventListener(type, listener, [capture]);
```
- Capture- event moves down the DOM tree. Any eventListeners registered with 'useCapture=true' are called

- Target- event reaches the target

- Bubbling- events move back up the DOM tree. Any eventListeners registered with 'useCapture=false' are called

