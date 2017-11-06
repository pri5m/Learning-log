
# How (and where) could you construct dynamic content?

- Ask for webpage, construct webpage, run javascrpt goes to server, javascript used to manipulate the dom, puts content on the webpage

- HTML template loadup (one off thing), populate server side, server does all the route manipulation


**Discuss: pros and cons**

- client or server pay for time

# Creating Dynamic content: Ajax

Asynchronous JavaScript And XML

Calls a server route and continues. 
When the server route returns
 execute the onload(e) function. 

xhttp.open("GET", "/txt", true);
Use GET or other http verbs
Route
Synchronous (true) or asynchronous  (false)
[w3schools ajax](http://www.w3schools.com/xml/ajax_intro.asp)  

**Synchronos**- Stuck in loop waiting, then send of next request for next piece of data, waiting for response

**Asynchronos**- Send off a message and then ignore it. Send off requests, the first that comes back gets processed into the page, not nesecarrily the first to be sent to the server. Buttons will work in the meantime

XML- is a way of formatting data

JSON- is also a way of processing data. Syntax for representing data

ajax server.py
```
import os
from flask import Flask, redirect, request,render_template, jsonify

app = Flask(__name__)

ALLOWED_EXTENSIONS = set(['txt', 'pdf', 'png', 'jpg', 'jpeg', 'gif'])
directory = {'Ian':'0000','Chris':'1111','Wendy':'2222'}

app = Flask(__name__)
@app.route("/Directory", methods=['GET'])
def returnDir():
    if request.method == 'GET':
        print("getting directory")
        return render_template('directoryForm.html', dir = directory)

# You could put this into the /Directory route to be better
# but this seperates the code for simplicity of the session.
# @app.route("/AddContact", methods=['POST'])
# def addContact():
#     print('processing Data')
#     message ='already there'
#     if request.method == 'POST':
#         name = request.form['name']
#         num = request.form['num']
#         if not(name in directory):
#             message = 'ok'
#             directory[name] =  num
#         print(directory)
#     return message

#
# @app.route("/DeleteContact", methods=['DELETE'])
# def delContact():
#     ----Exercise----
#     return 'ok'

# @app.route("/Length", methods=['GET'])
# def dirLength():
#     if request.method == 'GET':
#         print("getting length")
#         return str(len(directory))

# @app.route("/More", methods=['GET'])
# def more():
#     if request.method == 'GET':
#         return 'more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>more<br>'



if __name__ == "__main__":
    app.run(debug=True)
```

1_2ajax add.py
```
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Add entry </title>
  </head>

  <body onload="loaded()">
    <h3> Add a contact</h3>

    <form id='myForm' action='/WeDontWantThis' method='get'>
      first name:
      <input type = "text" name = "name"><br>
      number:
      <input type = "text" name = "num"><br>
      <button type = "submit" id='mySubmit'> submit </button>
    </form>
    <span id='txt'></span>
    <h3><a href=/Directory>Back to directory</h3>


<!-- Alternate method of intercepting the std form processing -->
    <script>
      function loadName(e) {
        // stop the default actions from the form
        e.preventDefault();
        e.stopPropagation();
        var name = document.forms["myForm"]["name"].value;
        var num = document.forms["myForm"]["num"].value;
        params = 'name='+name+'&num='+num;
        var xhttp = new XMLHttpRequest();
        xhttp.open("POST", '/AddContact', true);
        xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
        xhttp.onload = function() {
          if (xhttp.readyState === 4) {
            if (xhttp.status === 200) {
              console.log(xhttp.responseText);
              document.getElementById("txt").innerHTML = xhttp.responseText;
            } else {
              console.error(xhttp.statusText);
            }
          }
        };
        xhttp.send(params);
      }

// attach the event listener to submit button
      function loaded() {
        document.getElementById('mySubmit').addEventListener('click',loadName)
      }
    </script>

  </body>
</html>
```

summary.py
```
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Del entry </title>
  </head>

  <body onload="loaded()">
    <h3> This is the summary of the directory. </h3>

    This is a directory of contact numbers. you have
    <span id='DirLength'></span> contacts in your directory.
    <h3><a href=/Directory>Back to directory</h3>

    <script>
      function loadLength() {
        var xhttp = new XMLHttpRequest();
        xhttp.open("GET", '/Length', true);
        xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
        xhttp.onload = function() {
          if (xhttp.readyState === 4) {
            if (xhttp.status === 200) {
              console.log(xhttp.responseText);
              document.getElementById("DirLength").innerHTML = xhttp.responseText;
            } else {
              console.error(xhttp.statusText);
            }
          }
        };
        xhttp.send();
        setTimeout(loadLength, 3000);
      }

      function loaded() {
          setTimeout(loadLength, 3000);
      }
    </script>

  </body>
</html>
```
