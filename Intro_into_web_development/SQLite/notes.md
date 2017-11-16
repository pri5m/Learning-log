[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4495782-dt-content-rid-8380796_2/courses/1718-CM6112/Sqlite3.pdf)

The question marks are like parameters
```
conn = sqlite3.connect(DATABASE)     #connect to the database
cur = conn.cursor()
cur.execute("INSERT INTO Students     #execute the SQL command
('firstName', 'surname', … , 'public')\
VALUES (?,?,?,?,?)",
('Ian', 'Cooper', 'Cardiff', ‘Devon', "true") )
conn.commit()   #commit the data
conn.close()    #Close the connection
```
**Command prompt**
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite>py StudentServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```
Select SQL > Python

```
data = cur.fetchall()   #Assign the data
```

Returns a list of tuples e.g.
```
[(1, 'Ian', 'Cooper', 'Cardiff', 'Devon', 'True', None),
(11, 'Oli', 'Cooper', 'Cardiff', 'Cardiff', 'True', None)]
```
Revision from templating: Tabularising the SQL data

• A List of tuples

  • Row is each item in the list (the input data)
  
  • Index in item tuple is the column number.

```
{% for row in data %}
<tr>
<td>{{row[0]}}</td>
<td>{{row[1]}}</td>
<td>{{row[2]}}</td>
<td>{{row[3]}}</td>
<td>{{row[4]}}</td>
<td>{{row[5]}}</td>
</tr>
{% endfor %}
```

# Injection:

Of course you could just create the SQL as a string and run it as a script

Used in hacking
```
query = "INSERT INTO Customers
('firstName', 'surname', 'termLocation', 'homeLocation')
VALUES ('%s','%s','%s','%s')"
% (firstName, surame, termLocation, homeLocation)
cur.executescript(query)
```

# StudentServer.py
```
import os
from flask import Flask, redirect, request, render_template
import sqlite3

DATABASE = 'University.db'
ALLOWED_EXTENSIONS = set(['txt', 'pdf', 'png', 'jpg', 'jpeg', 'gif'])

app = Flask(__name__)

@app.route("/Student/AddDefaultStudent", methods = ['GET'])
def studentAddDefaultDetails():
	try:
		conn = sqlite3.connect(DATABASE)
		cur = conn.cursor()
		cur.execute("INSERT INTO Students ('firstName', 'surname', 'termLocation', 'homeLocation', 'public')\
					 VALUES (?,?,?,?,?)",("Pudsey", "Bear", "Cardiff", "BBC", "True") )
		conn.commit()
		msg = "Record successfully added"
	except:
		conn.rollback()
		msg = "error in insert operation"
	finally:
		conn.close()
		return msg


@app.route("/Student/AddStudent", methods = ['POST','GET'])
def studentAddDetails():
	if request.method =='GET':
		return render_template('StudentData.html')
	if request.method =='POST':
		firstName = request.form.get('firstName', default="Error")#rem: args for get form for post
		surname = request.form.get('surname', default="Error")
		termLocation = request.form.get('termLocation', default="Error")
		homeLocation = request.form.get('homeLocation', default="Error")
		print("inserting student"+firstName)
		try:
			conn = sqlite3.connect(DATABASE)
			cur = conn.cursor()
			cur.execute("INSERT INTO Students ('firstName', 'surname', 'termLocation', 'homeLocation', 'public')\
						VALUES (?,?,?,?,?)",(firstName, surname, termLocation, homeLocation, "True") )

			conn.commit()
			msg = "Record successfully added"
		except:
			conn.rollback()
			msg = "error in insert operation"
		finally:
			conn.close()
			return msg

@app.route("/Module/AddModule", methods = ['POST','GET'])
def moduleAddDetails():
	if request.method =='GET':
		return render_template('ModuleData.html')
	if request.method =='POST':
		msg = "TODO"
		name = request.form.get('name', default="Error")
		description = request.form.get('description', default="Error")
		credits = request.form.get('credits', default="Error")
		try:
			conn = sqlite3.connect(DATABASE)
			cur = conn.cursor()
			cur.execute("INSERT INTO Students ('name', 'description', 'credits')\
						VALUES (?,?,?)",(name, description, credits) )
			conn.commit()
			msg = "Record successfully added"
		except:
			conn.rollback()
			msg = "error in insert operation"
		finally:
			conn.close()

# Exercise  add a new module
# Extract the data from the POST message
# Connect to the database
# Execute an insert query
# Close the connection
# Return a message
		return msg

@app.route("/Student/Search", methods = ['GET','POST'])
def surnameSearch():
	if request.method =='GET':
		return render_template('StudentSearch.html')
	if request.method =='POST':
		try:
			surname = request.form.get('surname', default="Error") #rem: args for get form for post
			conn = sqlite3.connect(DATABASE)
			cur = conn.cursor()
			# cur.execute("SELECT * FROM Students WHERE surname=? AND public = 'True';", [surname])
			cur.execute("SELECT * FROM Students WHERE surname=? AND  public = 'True' ;", [surname])
			data = cur.fetchall()
			print(data)
		except:
			print('there was an error', data)
			conn.close()
		finally:
			conn.close()
			return str(data)
			# return render_template('ListStudents.html', data = data)

@app.route("/Module/Search", methods = ['GET','POST'])
def moduleSearch():
	if request.method =='GET':
		return render_template('ModuleSearch.html')
	if request.method =='POST':
		try:
			name = request.form.get('name', default="Error") #rem: args for get form for post
			conn = sqlite3.connect(DATABASE)
			cur = conn.cursor()
			cur.execute("SELECT * FROM Modules WHERE name=?;", [name])
			module = cur.fetchall()
			print(module)
		except:
			print('there was an error', module)
			conn.close()
		finally:
			conn.close()
			return render_template('ListModules.html', data = module)
		# Exercise: Search for a Module and display the module information.
		# Extract the data from the POST message
		# Connect to the database
		# Execute an select query
		# Store the resulting data in a variable
		# Close the connection
		# Start by just returning the string.
		# Then return rendered template with the data
    	# (use ListModules.html)
		return "todo"



# THIS IS VERY BAD
@app.route("/Student/InjectionSearch", methods = ['POST'])
def surnameInjectionSearch():
	surname = request.form.get('surname', default="Error") #rem: args for get form for post
	conn = sqlite3.connect(DATABASE)
	cur = conn.cursor()
	# VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD
	query = "SELECT * FROM Students WHERE surname= '%s' AND  public = 'True' " % (surname,)
	print (query)
	cur.execute(query)
	# VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD VERY BAD
	data = cur.fetchall()
	print (data)
	print (surname)
	conn.close()
	return render_template('ListStudents.html', data = data)


if __name__ == "__main__":
	app.run(debug=True)
	#app.run(host='0.0.0.0', port=8080)
```
# ModuleData.html
```
{%extends 'generalPageStyled.html'%}


{%block mainBlock%}
<h2>Student Data</h2>
<form id='myForm' onsubmit="return loadName()">
  Module name:<input type = "text" name = "name"><br>
  Description:<input type = "text" name = "description"><br>
  Credits:<input type = "text" name = "credits"><br>

  <button type = "submit"> submit </button>
</form>
<span id='txt'></span>

<script>
  function loadName() {
    var name = document.forms["myForm"]["name"].value;
    var description = document.forms["myForm"]["description"].value;
    var credits = document.forms["myForm"]["credits"].value;
    params = 'name='+name+'&description='+description+'&credits='+credits;
    var xhttp = new XMLHttpRequest();
    xhttp.open("POST", '/Module/AddModule', true); // true is asynchronous
    xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xhttp.onload = function() {
      if (xhttp.readyState === 4 && xhttp.status === 200) {
        console.log(xhttp.responseText);
        document.getElementById("txt").innerHTML = xhttp.responseText;
      } else {
        console.error(xhttp.statusText);
      }
    };
    xhttp.send(params);
    return false;
  }

</script>

{%endblock%}
```

# Command prompt
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite

16/11/2017  13:33    <DIR>          .
16/11/2017  13:33    <DIR>          ..
16/11/2017  13:33    <DIR>          static
14/11/2017  23:54             2,616 Students.sql
16/11/2017  12:14             4,214 StudentServer.py
16/11/2017  13:33    <DIR>          templates
16/11/2017  12:39            20,480 University.db
               3 File(s)         27,310 bytes
               4 Dir(s)  131,100,721,152 bytes free

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite>py StudentServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 13:48:24] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:48:25] "[37mGET /static/css/bootstrap.min.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:48:25] "[37mGET /static/css/styles.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:48:25] "[37mGET /static/js/bootstrap.min.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:48:25] "[33mGET /favicon.ico HTTP/1.1[0m" 404 -
[(1, 'Ian', 'Cooper', 'Cardiff', 'Devon', 'True', '')]
127.0.0.1 - - [16/Nov/2017 13:48:40] "[37mPOST /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:49:06] "[37mGET /Student/AddDefaultStudent HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:49:14] "[33mGET /Student HTTP/1.1[0m" 404 -
127.0.0.1 - - [16/Nov/2017 13:49:21] "[33mGET /Student/search HTTP/1.1[0m" 404 -
127.0.0.1 - - [16/Nov/2017 13:49:27] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 13:52:29] "[37mGET /Student/AddStudent HTTP/1.1[0m" 200 -
inserting studentHolly
127.0.0.1 - - [16/Nov/2017 13:52:43] "[37mPOST /Student/AddStudent HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:06:14] "[33mGET /Student/AddModule HTTP/1.1[0m" 404 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:06:47] "[33mGET /Student/AddModule HTTP/1.1[0m" 404 -
127.0.0.1 - - [16/Nov/2017 14:07:04] "[37mGET /Module/AddModule HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:22:31] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:28:43] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:47] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:28:47] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:47] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:47] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:47] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:47] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:28:48] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:29:08] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:29:08] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:29:08] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:29:08] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:29:08] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:29:08] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:33:30] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:33:39] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:41] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:35:41] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:41] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:41] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:42] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:42] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:35:42] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:37:45] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:37:49] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:43:23] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:27] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:43:27] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:27] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:27] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:28] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:28] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:28] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:44] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
UnboundLocalError: local variable 'data' referenced before assignment
127.0.0.1 - - [16/Nov/2017 14:43:44] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:44] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:44] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:44] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:43:44] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
[]
127.0.0.1 - - [16/Nov/2017 14:45:11] "[1m[35mPOST /Module/Search HTTP/1.1[0m" 500 -
Traceback (most recent call last):
  File "C:\Python35\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Python35\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Python35\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Python35\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Python35\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\SQLite\StudentServer.py", line 120, in moduleSearch
    return str(data)
NameError: name 'data' is not defined
127.0.0.1 - - [16/Nov/2017 14:45:11] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:45:11] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:45:11] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:45:12] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:45:12] "[37mGET /Module/Search?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
[]
127.0.0.1 - - [16/Nov/2017 14:45:32] "[37mPOST /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:46:20] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
[('Web', 'Web and stuff', 1, 20)]
127.0.0.1 - - [16/Nov/2017 14:46:23] "[37mPOST /Module/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:47:22] "[37mGET /Module/Search HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
[('Web', 'Web and stuff', 1, 20)]
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
[('Web', 'Web and stuff', 1, 20)]
127.0.0.1 - - [16/Nov/2017 14:49:13] "[37mPOST /Module/Search HTTP/1.1[0m" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\SQLite\\StudentServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 269-236-196
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [16/Nov/2017 14:58:07] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
[]
127.0.0.1 - - [16/Nov/2017 14:59:25] "[37mPOST /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:59:33] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
[]
127.0.0.1 - - [16/Nov/2017 14:59:38] "[37mPOST /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 14:59:44] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
[]
127.0.0.1 - - [16/Nov/2017 15:00:57] "[37mPOST /Student/Search HTTP/1.1[0m" 200 -
127.0.0.1 - - [16/Nov/2017 15:00:58] "[37mGET /Student/Search HTTP/1.1[0m" 200 -
SELECT * FROM Students WHERE surname= 'ofMoney' AND  public = 'True'
[]
ofMoney
127.0.0.1 - - [16/Nov/2017 15:01:17] "[37mPOST /Student/InjectionSearch HTTP/1.1[0m" 200 -
SELECT * FROM Students WHERE surname= 'ofMoney';--' AND  public = 'True'
[(5, 'loads', 'ofMoney', 'Cardiff', 'Caymen Islands', 'FALSE', 1111)]
ofMoney';--
127.0.0.1 - - [16/Nov/2017 15:02:39] "[37mPOST /Student/InjectionSearch HTTP/1.1[0m" 200 -
SELECT * FROM Students WHERE surname= '*';--' AND  public = 'True'
[]
*';--
127.0.0.1 - - [16/Nov/2017 15:03:21] "[37mPOST /Student/InjectionSearch HTTP/1.1[0m" 200 -
```
