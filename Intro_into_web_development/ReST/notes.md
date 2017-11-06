
Sushi takeaway

- order/{orderNo}/paymentDetails   -Add payment details to an order number

- **Get**  /client/{clientNo}/order     -retrieve a client's order

- **Put**  /cust/{custNo}/delivery   -Post inforamtion about the status of the delivery

For all customers just drop the id

What actions could we preform?

- **get**  /cust/id

- **post**   /cust

- **put**    /cust/id

- **delete**   /cust/id

```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>virtualEnv form
Using base prefix 'c:\\python35'
New python executable in C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\Scripts\python.exe
Installing setuptools, pip, wheel...done.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>activate
'activate' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>form/scripts
'form' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>form/Scripts
'form' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>cd form/Scripts

C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>activate

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>3_FormServer.py
'3_FormServer.py' is not recognized as an internal or external command,
operable program or batch file.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>3_FormServer.py
'3_FormServer.py' is not recognized as an internal or external command,
operable program or batch file.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>3_FormServer.py
'3_FormServer.py' is not recognized as an internal or external command,
operable program or batch file.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>cd 3_FormServer.py
The system cannot find the path specified.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>3_FormServer.py
'3_FormServer.py' is not recognized as an internal or external command,
operable program or batch file.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>cd 3_FormServer.py
The system cannot find the path specified.

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>3_FormServer.py
Traceback (most recent call last):
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts\3_FormServer.py", line 2, in <module>
    from flask import Flask, redirect, request
ImportError: No module named 'flask'

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>flask run
Usage: flask run [OPTIONS]

Error: Could not locate Flask application. You did not provide the FLASK_APP environment variable.

For more information see http://flask.pocoo.org/docs/latest/quickstart/

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>set FLASK_APP=2_FlaskServer.py

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>set FLASK_APP=3_FormServer.py

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>flask run
 * Serving Flask app "3_FormServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [02/Nov/2017 14:00:04] "[33mGET / HTTP/1.1[0m" 404 -
127.0.0.1 - - [02/Nov/2017 14:01:36] "[33mGET / HTTP/1.1[0m" 404 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:02:37] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
127.0.0.1 - - [02/Nov/2017 14:06:06] "[33mGET /Form.html HTTP/1.1[0m" 404 -
127.0.0.1 - - [02/Nov/2017 14:06:18] "[33mGET /form.html HTTP/1.1[0m" 404 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:06:58] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:06] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:07] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:08] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:34] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:34] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:34] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
Processing form
None
127.0.0.1 - - [02/Nov/2017 14:11:35] "[37mGET /HomeForm HTTP/1.1[0m" 200 -
(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>set FLASK_APP=4_FormSserver.py

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>flask run
Usage: flask run [OPTIONS]

Error: The file/path provided (4_FormSserver.py) does not appear to exist.  Please verify the path is correct.  If app is not on PYTHONPATH, ensure the extension is .py

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>set FLASK_APP=4_FormServer.py

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>flask run
 * Serving Flask app "4_FormServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts

02/11/2017  14:22    <DIR>          .
02/11/2017  14:22    <DIR>          ..
21/10/2017  13:48               489 3_FormServer.py
02/11/2017  14:10               653 4_FormServer.py
02/11/2017  13:49             2,247 activate
02/11/2017  13:49               792 activate.bat
02/11/2017  13:49             8,325 activate.ps1
02/11/2017  13:49             1,137 activate_this.py
02/11/2017  13:49               508 deactivate.bat
02/11/2017  13:49            98,206 easy_install-3.5.exe
02/11/2017  13:49            98,206 easy_install.exe
02/11/2017  14:00               364 form.html
02/11/2017  13:49            98,178 pip.exe
02/11/2017  13:49            98,178 pip3.5.exe
02/11/2017  13:49            98,178 pip3.exe
02/11/2017  13:49            42,136 python.exe
02/11/2017  13:49         3,942,552 python35.dll
02/11/2017  13:49            42,136 pythonw.exe
02/11/2017  13:49            98,185 wheel.exe
02/11/2017  14:13    <DIR>          __pycache__
              17 File(s)      4,630,470 bytes
               3 Dir(s)  134,379,376,640 bytes free

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev\form\Scripts>cd ../../

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev

02/11/2017  14:21    <DIR>          .
02/11/2017  14:21    <DIR>          ..
02/11/2017  14:22    <DIR>          form
               0 File(s)              0 bytes
               3 Dir(s)  134,379,376,640 bytes free

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\webDev>cd ../

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev

02/11/2017  14:21    <DIR>          .
02/11/2017  14:21    <DIR>          ..
12/10/2017  12:22    <DIR>          CSS
17/10/2017  13:25    <DIR>          DOM
02/11/2017  13:04    <DIR>          Frontend_frameworks
10/10/2017  13:58    <DIR>          HTML
01/11/2017  11:34    <DIR>          Intro to web development
17/10/2017  09:30    <DIR>          Javascript
19/10/2017  12:35    <DIR>          Jquery
02/11/2017  09:42    <DIR>          project_work
02/11/2017  14:21    <DIR>          Servers
02/11/2017  14:21    <DIR>          webDev
               0 File(s)              0 bytes
              12 Dir(s)  134,378,995,712 bytes free

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev>cd servers

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers

02/11/2017  14:21    <DIR>          .
02/11/2017  14:21    <DIR>          ..
20/10/2017  16:30             1,007 0_1_pyserver.py
18/10/2017  20:45               109 1_StaticFlaskServer.py
01/11/2017  11:04               979 2_FlaskServer.py
02/11/2017  14:05               571 3_FormServer.py
02/11/2017  14:19               825 4_FormServer.py
21/10/2016  14:37               131 hello.html
02/11/2017  13:01    <DIR>          ReST
02/11/2017  14:29    <DIR>          static
25/10/2017  08:58             3,143 takeaway.html
26/10/2017  13:53    <DIR>          webDev
26/10/2017  14:05    <DIR>          __pycache__
               7 File(s)          6,765 bytes
               6 Dir(s)  134,379,061,248 bytes free

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>py 4_FormServer.py
Traceback (most recent call last):
  File "4_FormServer.py", line 2, in <module>
    from flask import Flask, redirect, request
ImportError: No module named 'flask'

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>pip install flask
Collecting flask
  Using cached Flask-0.12.2-py2.py3-none-any.whl
Collecting click>=2.0 (from flask)
  Using cached click-6.7-py2.py3-none-any.whl
Collecting itsdangerous>=0.21 (from flask)
Collecting Werkzeug>=0.7 (from flask)
  Using cached Werkzeug-0.12.2-py2.py3-none-any.whl
Collecting Jinja2>=2.4 (from flask)
  Using cached Jinja2-2.9.6-py2.py3-none-any.whl
Collecting MarkupSafe>=0.23 (from Jinja2>=2.4->flask)
Installing collected packages: click, itsdangerous, Werkzeug, MarkupSafe, Jinja2, flask
Successfully installed Jinja2-2.9.6 MarkupSafe-1.0 Werkzeug-0.12.2 click-6.7 flask-0.12.2 itsdangerous-0.24

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>py 4_FormServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>py 4_FormServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [02/Nov/2017 14:38:09] "GET /static/form.html HTTP/1.1" 200 -
Processing form
[]
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?firstname=dscsdcsdc&surname=fdsvdsv HTTP/1.1" 500 -
Traceback (most recent call last):
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers\4_FormServer.py", line 28, in form
    print(surname )
UnboundLocalError: local variable 'surname' referenced before assignment
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:38:41] "GET /HomeForm?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:38:42] "GET /HomeForm?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\Servers\\4_FormServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\Servers\\4_FormServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [02/Nov/2017 14:39:34] "GET /static/form.html HTTP/1.1" 304 -
Processing form
[]
127.0.0.1 - - [02/Nov/2017 14:39:37] "GET /HomeForm?firstname=fgfdg&surname=wes HTTP/1.1" 500 -
Traceback (most recent call last):
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers\4_FormServer.py", line 28, in form
    print(surname )
UnboundLocalError: local variable 'surname' referenced before assignment
127.0.0.1 - - [02/Nov/2017 14:39:38] "GET /HomeForm?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:39:38] "GET /HomeForm?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:39:38] "GET /HomeForm?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:39:38] "GET /HomeForm?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:39:38] "GET /HomeForm?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\Servers\\4_FormServer.py', reloading
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
Processing form
[]
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?firstname=fgfdg&surname=wes HTTP/1.1" 500 -
Traceback (most recent call last):
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers\4_FormServer.py", line 28, in form
    print(surnames )
NameError: name 'surnames' is not defined
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:40:01] "GET /HomeForm?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:41:16] "GET /static/form.html HTTP/1.1" 304 -
Processing form
[]
127.0.0.1 - - [02/Nov/2017 14:41:20] "GET /HomeForm?firstname=dcsas&surname=adadsad HTTP/1.1" 500 -
Traceback (most recent call last):
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\webDev\form\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers\4_FormServer.py", line 28, in form
    print(surnames )
NameError: name 'surnames' is not defined
127.0.0.1 - - [02/Nov/2017 14:41:21] "GET /HomeForm?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:41:21] "GET /HomeForm?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:41:21] "GET /HomeForm?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:41:21] "GET /HomeForm?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 14:41:21] "GET /HomeForm?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers>cd ReST

(form) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Servers\ReST>py Server.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 107-146-453
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [02/Nov/2017 15:31:44] "GET / HTTP/1.1" 404 -
getting directory
127.0.0.1 - - [02/Nov/2017 15:31:58] "GET /Directory HTTP/1.1" 200 -
getting person 1111
127.0.0.1 - - [02/Nov/2017 15:32:13] "GET /Directory/Chris HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 15:32:27] "PUT /Directory/Chris HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 15:32:28] "PUT /Directory/Chris HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 15:32:29] "PUT /Directory/Chris HTTP/1.1" 200 -
127.0.0.1 - - [02/Nov/2017 15:34:24] "POST /Directory HTTP/1.1" 201 -

```
