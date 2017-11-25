# JSON

JSON: JavaScript Object Notation.

JSON is a syntax for storing and exchanging data.

JSON is text, written with JavaScript object notation.

**Exchanging Data**

When exchanging data between a browser and a server, the data can only be text.

JSON is text, and we can convert any JavaScript object into JSON, and send JSON to the server.

We can also convert any JSON received from the server into JavaScript objects.

This way we can work with the data as JavaScript objects, with no complicated parsing and translations.

JSON uses JavaScript syntax, but the JSON format is text only.

Text can be read and used as a data format by any programming language.

# Sending data

If you have data stored in a JavaScript object, you can convert the object into JSON, and send it to a server:

```
var myObj = { "name":"John", "age":31, "city":"New York" };
var myJSON = JSON.stringify(myObj);
window.location = "demo_json.php?x=" + myJSON;
```

# Recieving data

If you receive data in JSON format, you can convert it into a JavaScript object:

```
var myJSON = '{ "name":"John", "age":31, "city":"New York" }';
var myObj = JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj.name; 
```

# AJAX

AJAX is a developer's dream, because you can:

- Read data from a web server - after the page has loaded

- Update a web page without reloading the page

- Send data to a web server - in the background

# AJAX Example Explained
```
HTML Page
<!DOCTYPE html>
<html>
<body>

<div id="demo">
  <h2>Let AJAX change this text</h2>
  <button type="button" onclick="loadDoc()">Change Content</button>
</div>

</body>
</html>
```
The HTML page contains a <div> section and a <button>.
  
The <div> section is used to display information from a server.
  
The <button> calls a function (if it is clicked).
  
The function requests data from a web server and displays it:
```
Function loadDoc()
function loadDoc() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
     document.getElementById("demo").innerHTML = this.responseText;
    }
  };
  xhttp.open("GET", "ajax_info.txt", true);
  xhttp.send();
} 
```
# What is AJAX?


AJAX = Asynchronous JavaScript And XML.

AJAX is not a programming language.

AJAX just uses a combination of:

- A browser built-in XMLHttpRequest object (to request data from a web server)

- JavaScript and HTML DOM (to display or use the data)

*AJAX is a misleading name. AJAX applications might use XML to transport data, but it is equally common to transport data as plain text or JSON text.*

AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

[See how AJAX works image](https://www.w3schools.com/js/js_ajax_intro.asp)
