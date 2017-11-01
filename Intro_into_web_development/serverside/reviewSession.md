
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
