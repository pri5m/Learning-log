
# What is a client?

• Program that requests a service.

  • Browser
  
  • WinScp
  
  • Git
  
  • Word (printing)
  
  • Terminal / ssh clients
  
    • GitBash

**Ctrl shift r** Hard reset- gets a new page no matter what

**Routes**

• Seen routes before in the browser urls

  • x.x.x.x:5000/Home.html
  
  • x.x.x.x:5000/IMC/Home.html
  
  
• Routes lead to execution of code

  • Go to the file system and retrieve page.
  
• Routes could request data

  • Or an Action
  
• APIs

  • application program interface

**Annotation:** Calls framework code to set up the function myHello as the function to be called when the server receives a request for /hello

# Command window
```
C:\Users\c1712480\OneDrive - Cardiff University>Semester_1
'Semester_1' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University>cd Semester_1

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>cd Intro into web development
The system cannot find the path specified.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1>cd Intro to web development

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development>cd Servers

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>virtualEnv <webdev>
The syntax of the command is incorrect.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>virtualEnv<webdev>
The syntax of the command is incorrect.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>virtualEnv<webDev>
The syntax of the command is incorrect.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>virtualEnvwebDev
'virtualEnvwebDev' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>virtualEnv webDev
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTROT~1\Servers\webDev\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>webDev\scripts\activate

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>py 1_StaticFlaskServer.py
Traceback (most recent call last):
  File "1_StaticFlaskServer.py", line 2, in <module>
    from flask import Flask
ImportError: No module named 'flask'

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>pip install flask
Collecting flask
  Downloading Flask-0.12.2-py2.py3-none-any.whl (83kB)
    100% |################################| 92kB 545kB/s
Collecting Werkzeug>=0.7 (from flask)
  Downloading Werkzeug-0.12.2-py2.py3-none-any.whl (312kB)
    100% |################################| 317kB 2.6MB/s
Collecting itsdangerous>=0.21 (from flask)
  Downloading itsdangerous-0.24.tar.gz (46kB)
    100% |################################| 51kB 4.3MB/s
Collecting click>=2.0 (from flask)
  Downloading click-6.7-py2.py3-none-any.whl (71kB)
    100% |################################| 71kB 3.1MB/s
Collecting Jinja2>=2.4 (from flask)
  Downloading Jinja2-2.9.6-py2.py3-none-any.whl (340kB)
    100% |################################| 348kB 3.4MB/s
Collecting MarkupSafe>=0.23 (from Jinja2>=2.4->flask)
  Downloading MarkupSafe-1.0.tar.gz
Building wheels for collected packages: itsdangerous, MarkupSafe
  Running setup.py bdist_wheel for itsdangerous ... done
  Stored in directory: C:\Users\c1712480\AppData\Local\pip\Cache\wheels\fc\a8\66\24d655233c757e178d45dea2de22a04c6d92766abfb741129a
  Running setup.py bdist_wheel for MarkupSafe ... done
  Stored in directory: C:\Users\c1712480\AppData\Local\pip\Cache\wheels\88\a7\30\e39a54a87bcbe25308fa3ca64e8ddc75d9b3e5afa21ee32d57
Successfully built itsdangerous MarkupSafe
Installing collected packages: Werkzeug, itsdangerous, click, MarkupSafe, Jinja2, flask
Successfully installed Jinja2-2.9.6 MarkupSafe-1.0 Werkzeug-0.12.2 click-6.7 flask-0.12.2 itsdangerous-0.24

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers

26/10/2017  14:53    <DIR>          .
26/10/2017  14:53    <DIR>          ..
20/10/2017  17:30             1,007 0_1_pyserver.py
18/10/2017  21:45               109 1_StaticFlaskServer.py
26/10/2017  11:05               763 2_FlaskServer.py
21/10/2017  14:48               489 3_FormServer.py
21/10/2017  14:42               652 4_FormServer.py
21/10/2016  15:37               131 hello.html
26/10/2017  13:43    <DIR>          static
26/10/2017  14:53    <DIR>          webDev
               6 File(s)          3,151 bytes
               4 Dir(s)  135,270,387,712 bytes free
(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>py 1_StaticFlaskServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 726-386-281
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>set FLASK_APP = 1_StatickFlaskServer.py

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>flask run --host=0.0.0.0
Usage: flask run [OPTIONS]

Error: Could not locate Flask application. You did not provide the FLASK_APP environment variable.

For more information see http://flask.pocoo.org/docs/latest/quickstart/

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>set FLASK_APP=1_StaticFlaskServer.py

(webDev) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro to web development\Servers>flask run --host=0.0.0.0
 * Serving Flask app "1_StaticFlaskServer"
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```
