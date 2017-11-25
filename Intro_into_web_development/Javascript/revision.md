[W3schools link](https://www.w3schools.com/js/js_intro.asp)
# JavaScript Can Change HTML Content

One of many JavaScript HTML methods is getElementById().

This example uses the method to "find" an HTML element (with id="demo") and changes the element content (innerHTML) to "Hello JavaScript":
```
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change HTML content.</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>Click Me!</button>

</body>
</html>
```
# The <script> Tag
  
In HTML, JavaScript code must be inserted between <script> and </script> tags.

# External JavaScript

External scripts are practical when the same code is used in many different web pages. 

JavaScript files have the file extension .js.

To use an external script, put the name of the script file in the src (source) attribute of a <script> tag:

```
<!DOCTYPE html>
<html>
<body>

<script src="myScript.js"></script>

</body>
</html> 
```
You can place an external script reference in <head> or <body> as you like. The script will behave as if it was located exactly where the <script> tag is located.
  
**External JavaScript Advantages**

Placing scripts in external files has some advantages:

- It separates HTML and code

- It makes HTML and JavaScript easier to read and maintain

- Cached JavaScript files can speed up page loads

To add several script files to one page  - use several script tags

# JavaScript Display Possibilities

JavaScript can "display" data in different ways:

- Writing into an HTML element, using innerHTML. For testing purposes, it is convenient to use document.write()

- Writing into the HTML output using document.write(). Using document.write() after an HTML document is fully loaded, will delete all existing HTML

- Writing into an alert box, using window.alert(). You can use an alert box to display data

- Writing into the browser console, using console.log(). For debugging purposes, you can use the console.log() method to display data.
