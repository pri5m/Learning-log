
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

# console log
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>virtualEnv ajaxserver
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\ajax\STUDEN~2\STUDEN~1\static\AJAXSE~1\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>pip install flask
Requirement already satisfied: flask in c:\python35\lib\site-packages
Requirement already satisfied: click>=2.0 in c:\python35\lib\site-packages (from flask)
Requirement already satisfied: Werkzeug>=0.7 in c:\python35\lib\site-packages (from flask)
Requirement already satisfied: Jinja2>=2.4 in c:\python35\lib\site-packages (from flask)
Requirement already satisfied: itsdangerous>=0.21 in c:\python35\lib\site-packages (from flask)
Requirement already satisfied: MarkupSafe>=0.23 in c:\python35\lib\site-packages (from Jinja2>=2.4->flask)

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>activate
'activate' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>ajaxserver\scripts/activate
'ajaxserver\scripts' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>ajaxserver\activate
'ajaxserver\activate' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>ajaxserver\Scripts\activate

(AJAXSE~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static

06/11/2017  14:26    <DIR>          .
06/11/2017  14:26    <DIR>          ..
04/11/2017  14:48               628 0_formAdd.html
06/11/2017  09:04             1,175 1_Directory.html
06/11/2017  14:25               606 2_Summary.html
05/11/2017  19:29             1,636 3-2_AjaxAdd.html
05/11/2017  19:29             1,285 3_AjaxAdd.html
06/11/2017  09:25               421 4_AjaxDel.html
05/11/2017  20:05               721 4_SummaryJQ.html
06/11/2017  09:29               478 5_footer.html
02/11/2016  17:54             6,989 6_More.html
06/11/2017  14:26    <DIR>          ajaxserver
05/11/2017  20:16                97 footer.html
05/11/2017  20:34               551 thankyou.html
              11 File(s)         14,587 bytes
               3 Dir(s)  134,308,298,752 bytes free

(AJAXSE~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode\static>cd ..\

(AJAXSE~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode>set FLASK_APP=AjaxServer.py

(AJAXSE~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\ajax\StudentCode(3)\StudentCode>flask run
 * Serving Flask app "AjaxServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [06/Nov/2017 14:32:07] "[33mGET / HTTP/1.1[0m" 404 -
127.0.0.1 - - [06/Nov/2017 14:32:07] "[33mGET /favicon.ico HTTP/1.1[0m" 404 -
getting directory.
127.0.0.1 - - [06/Nov/2017 14:33:09] "[37mGET /Directory HTTP/1.1[0m" 200 -

```

# Exercise
**AjaxServer.py**
```
import os
import json
from flask import Flask, redirect, request,render_template, jsonify

app = Flask(__name__)

ALLOWED_EXTENSIONS = set(['txt', 'pdf', 'png', 'jpg', 'jpeg', 'gif'])
directory = {'Ian':'0000','Chris':'1111','Wendy':'2222'}

app = Flask(__name__)
@app.route("/Hello", methods=['GET'])
def returnHello():
    if request.method == 'GET':
        print("Executing Hello")
        return "Hello world"

@app.route("/Directory", methods=['GET'])
def returnDir():
    if request.method == 'GET':
        print("getting directory.")
        return json.dumps(directory);


# Exercise 1:
@app.route("/Length", methods=['GET'])
def dirLength():
    if request.method == 'GET':
        print("getting length")
        return str(len(directory))

# ----------------------------------------------------------------
# You could put this into the /Directory route to be better
# but this seperates the code for simplicity of the session.
@app.route("/AddContact", methods=['POST'])
def addContact():
    print('processing Data')
    message ='already there'
    if request.method == 'POST':
        name = request.form['name']
        num = request.form['num']
        if not(name in directory):
            message = 'ok'
            directory[name] =  num
        print(directory)
    return message

# this is the route for ex2
@app.route("/DeleteContact", methods=['DELETE'])
def delContact():
    print('processing Data')
    message = 'Not here anymore'
    if request.method == 'DELETE':
        name = request.form['name']
        if (name in directory):
            #del directory[name]
            message = 'Deleted'
            directory.pop(name)
        print(directory)
    return message


@app.route("/More", methods=['GET'])
def more():
    if request.method == 'GET':
        return


if __name__ == "__main__":
    app.run(debug=True)
```

**4_AjaxDel.html
html```
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Del entry </title>
  </head>

  <body >
    <h3> Delete a contact</h3>

<!-- Ex2: create a form that provides the name to be deleted -->
    <form id='myForm' action='/DeleteContact' method='delete' onsubmit="return delName()">
      name:<input type = "text" name = "name"><br>
      <button type = "submit"> submit </button>
    </form>

    <span id='txt'></span>
    <h3><a href=/static/1_Directory.html>Back to directory</h3>

    <script>
// Ex 2 submit the form to /DeleteContact and render the result in <span id="txt">
    function delName() {
      var name = document.forms["myForm"]["name"].value;
      parameters = 'name='+name;
      var xhttp = new XMLHttpRequest();
      xhttp.open("DELETE", '/DeleteContact', true); // true is asynchronous
      xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
      xhttp.onreadystatechange = function() {
        if (xhttp.readyState === 4 && xhttp.status === 200) {
          console.log(xhttp.responseText);
          document.getElementById("txt").innerHTML = xhttp.responseText;
        } else {
        //  console.error(xhttp.statusText);
        }
      };
      xhttp.send(parameters);
      return false;
    }
    </script>

  </body>
</html>
```
