
# virtual envrionment

command prompt
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>Intro_webdev
'Intro_webdev' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>myEnv
'myEnv' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>cd myEnv

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv>virtualEnv servers
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\ONEDRI~1\SEMEST~1\myEnv\servers\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv>cd servers/Scripts

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>activate

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>
```
# hosts
Anyone can access it if using this address:
http://0.0.0.0:5000/

I accessed it by using **flask run --host=0.0.0.0**

Use local host for testing, use this most times:

http://127.0.0.1:5000/

To access the local host address just use **flask run** and it will use the local host automatically

```
(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>flask run --host=0.0.0.0
 * Serving Flask app "2_FlaskServer"
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>flask run
 * Serving Flask app "2_FlaskServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
hello requested
127.0.0.1 - - [01/Nov/2017 10:51:02] "[37mGET /hello HTTP/1.1[0m" 200 -
127.0.0.1 - - [01/Nov/2017 10:51:02] "[33mGET /favicon.ico HTTP/1.1[0m" 404 -
```
# Command prompt
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>Intro_webdev
'Intro_webdev' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>myEnv
'myEnv' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>cd myEnv

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv>virtualEnv servers
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\ONEDRI~1\SEMEST~1\myEnv\servers\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv>cd servers/Scripts

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>activate

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>flask run --host=0.0.0.0
Usage: flask run [OPTIONS]

Error: Could not locate Flask application. You did not provide the FLASK_APP environment variable.

For more information see http://flask.pocoo.org/docs/latest/quickstart/

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>set FLASK_APP=2_FlaskServer.py

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>flask run --host=0.0.0.0
Usage: flask run [OPTIONS]

Error: The file/path provided (2_FlaskServer.py) does not appear to exist.  Please verify the path is correct.  If app is not on PYTHONPATH, ensure the extension is .py

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts

01/11/2017  10:18    <DIR>          .
01/11/2017  10:18    <DIR>          ..
01/11/2017  10:18             2,233 activate
01/11/2017  10:18               788 activate.bat
01/11/2017  10:18             8,325 activate.ps1
01/11/2017  10:18             1,137 activate_this.py
01/11/2017  10:18               508 deactivate.bat
01/11/2017  10:17            98,199 easy_install-3.5.exe
01/11/2017  10:17            98,199 easy_install.exe
01/11/2017  10:17            98,171 pip.exe
01/11/2017  10:17            98,171 pip3.5.exe
01/11/2017  10:17            98,171 pip3.exe
01/11/2017  10:17            42,136 python.exe
01/11/2017  10:17         3,942,552 python35.dll
01/11/2017  10:17            42,136 pythonw.exe
01/11/2017  10:17            98,178 wheel.exe
              14 File(s)      4,628,904 bytes
               2 Dir(s)  135,230,570,496 bytes free

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>set FLASK_APP=2_FlaskServer.py

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>flask run --host=0.0.0.0
Usage: flask run [OPTIONS]

Error: The file/path provided (2_FlaskServer.py) does not appear to exist.  Please verify the path is correct.  If app is not on PYTHONPATH, ensure the extension is .py

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers\Scripts>cd ..

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>set FLASK_APP=2_FlaskServer.py

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>flask run --host=0.0.0.0
 * Serving Flask app "2_FlaskServer"
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>flask run
 * Serving Flask app "2_FlaskServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
hello requested
127.0.0.1 - - [01/Nov/2017 10:51:02] "[37mGET /hello HTTP/1.1[0m" 200 -
127.0.0.1 - - [01/Nov/2017 10:51:02] "[33mGET /favicon.ico HTTP/1.1[0m" 404 -
goodbye requested
127.0.0.1 - - [01/Nov/2017 10:55:50] "[37mGET /goodbye HTTP/1.1[0m" 200 -
127.0.0.1 - - [01/Nov/2017 10:57:44] "[33mGET /time HTTP/1.1[0m" 404 -
127.0.0.1 - - [01/Nov/2017 10:58:08] "[33mGET /time HTTP/1.1[0m" 404 -
hello requested
127.0.0.1 - - [01/Nov/2017 10:58:14] "[37mGET /hello HTTP/1.1[0m" 200 -
127.0.0.1 - - [01/Nov/2017 11:00:35] "[33mGET /time HTTP/1.1[0m" 404 -
goodbye requested
127.0.0.1 - - [01/Nov/2017 11:00:45] "[37mGET /goodbye HTTP/1.1[0m" 200 -
127.0.0.1 - - [01/Nov/2017 11:02:55] "[33mGET /time HTTP/1.1[0m" 404 -
127.0.0.1 - - [01/Nov/2017 11:04:07] "[33mGET /time HTTP/1.1[0m" 404 -
127.0.0.1 - - [01/Nov/2017 11:04:19] "[33mGET /time HTTP/1.1[0m" 404 -

(servers) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\myEnv\servers>
```

# Python code 2_FlaskServer
```
import os
from flask import Flask, redirect, request
import datetime

ALLOWED_EXTENSIONS = set(['txt', 'pdf', 'png', 'jpg', 'jpeg', 'gif'])

app = Flask(__name__)

@app.route("/hello")
def myHello():
    print("hello requested")
    return "Hello World! - from Flask server 2"

@app.route("/redirect")
def redirectToStatic():
    return redirect("/static/hello.html")

# =================================
# Exercises

# 1) complete the route to give a goodbye message
# @app.route("/goodbye")
#    def goodbye():
@app.route("/goodbye")
def goodbye():
    print("goodbye requested")
    return ("goodbye - from the flask server")

# 2) complete the route to return the time
# @app.route("/time")
@app.route("/time")
def time():
    from time import time
    time.time()
    print(time)
    return(time)

# 3) create a route that returns a hit counter with a message

# 4) create a route to returrn the IP ADDRESS of the client


if __name__ == "__main__":
    app.run(debug=True)
```
