# What is templating?
• A tool that constructs
html pages.

• Can get server side
and client side
templating.

• Jinja is Server side. 

This...
```
<ul>
{%for value in nums %}
<li>{{value}}</li>
{% endfor %}
</ul>
```
turns into this...
```
<ul>
<li> one </li>
<li> two </li>
<li> three </li>
<li> four </li>
<li> five </li>
<li> six </li>
<li> seven </li>
<li> eight </li>
<li> nine </li>
</ul>
```

What is Templating: Dynamic data.
• The python list ‘nums’:

- Can be created in the server and passed to the
templating engine

- This can be done when the page is requested. 

# Rendering a template

• Template files must be in the template directory.

 [Rendering Templates](http://flask.pocoo.org/docs/0.11/quickstart/#rendering-templates)
```
 from flask import Flask, request, render_template
...
@app.route("/Basic", methods=['GET'])
def returnFirst():
if request.method == 'GET':
**return render_template('0_Basic.html', data='Hello World')***
```

# Dictionaries
• We can access data from
dictionaries

```
<h1>
{{ data.title }}
</h1>
<p> Hi this is a message from
{{data.name}}.</p>
<p>{{data.message}}</p>
```
```
messages = {'title':'HelloWorld',
'name':'Ian',
'message':‘more'}
return render_template('1_json.html', data = messages)
```
# Loops: lists
py
```
days = ['mon','tues','wed','thurs','fri']
return render_template('2_loops.html', days = days)
```
html
```
<ul>
{%for day in days %}
<li>{{day}}</li>
{% endfor %}
</ul>
```

# Loops: Dictionaries

• data.items()

• Single var vs two vars

• De-reference into key, value

Python
```
data = {'title':'HelloWorld',
'name':'Ian',
'message':'hi!',
'days': ['mon','tues','wed','thurs','fri']
}
return render_template('3_dictionary.html', data = data)
```
html
```
<ul>
{%for key,value in data.items() %}
<li>{{value}},{{key}}</li>
{% endfor %}
</ul>
```

Command prompt
```
C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>frameworkserver\Scripts\activate

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode

09/11/2017  13:42    <DIR>          .
09/11/2017  13:42    <DIR>          ..
09/11/2017  13:43    <DIR>          frameworkserver
09/11/2017  10:33             2,264 JinjaServer.py
09/11/2017  13:12    <DIR>          templates
               1 File(s)          2,264 bytes
               4 Dir(s)  134,317,023,232 bytes free

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>set FLASK_APP = JinjaServer.py

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
Usage: flask run [OPTIONS]

Error: Could not locate Flask application. You did not provide the FLASK_APP environment variable.

For more information see http://flask.pocoo.org/docs/latest/quickstart/

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>pip install flask
Collecting flask
  Using cached Flask-0.12.2-py2.py3-none-any.whl
Collecting itsdangerous>=0.21 (from flask)
Collecting click>=2.0 (from flask)
  Using cached click-6.7-py2.py3-none-any.whl
Collecting Werkzeug>=0.7 (from flask)
  Using cached Werkzeug-0.12.2-py2.py3-none-any.whl
Collecting Jinja2>=2.4 (from flask)
  Downloading Jinja2-2.10-py2.py3-none-any.whl (126kB)
    100% |################################| 133kB 1.6MB/s
Collecting MarkupSafe>=0.23 (from Jinja2>=2.4->flask)
Installing collected packages: itsdangerous, click, Werkzeug, MarkupSafe, Jinja2, flask
Successfully installed Jinja2-2.10 MarkupSafe-1.0 Werkzeug-0.12.2 click-6.7 flask-0.12.2 itsdangerous-0.24

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>set FLASK_APP=JinjaServer.py

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>run flask
'run' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
 * Serving Flask app "JinjaServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 13:47:35] "GET / HTTP/1.1" 404 -
127.0.0.1 - - [09/Nov/2017 13:47:36] "GET /favicon.ico HTTP/1.1" 404 -
127.0.0.1 - - [09/Nov/2017 13:47:45] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:50:08] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:50:18] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:51:29] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:51:29] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:51:30] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:51:30] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:51:59] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:52:04] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:52:49] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:52:49] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:52:50] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:52:50] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:53:17] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:53:37] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:02] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:02] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:17] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:18] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:18] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:18] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:54:19] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:55:35] "GET /Basic HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:55:45] "GET /Json HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:55:52] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:56:12] "GET /Basic2 HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 13:56:13] "GET /Basic2 HTTP/1.1" 200 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
 * Serving Flask app "JinjaServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
[2017-11-09 13:56:47,242] ERROR in app: Exception on /Basic2 [GET]
Traceback (most recent call last):
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 21, in returnSecond
    return render_template('0-1_Basic.html', data = 'Hello World')
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 133, in render_template
    return _render(ctx.app.jinja_env.get_or_select_template(template_name_or_list),
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 869, in get_or_select_template
    return self.get_template(template_name_or_list, parent, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 830, in get_template
    return self._load_template(name, self.make_globals(globals))
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 804, in _load_template
    template = self.loader.load(self, name, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\loaders.py", line 113, in load
    source, filename, uptodate = self.get_source(environment, name)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 57, in get_source
    return self._get_source_fast(environment, template)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 85, in _get_source_fast
    raise TemplateNotFound(template)
jinja2.exceptions.TemplateNotFound: 0-1_Basic.html
127.0.0.1 - - [09/Nov/2017 13:56:47] "GET /Basic2 HTTP/1.1" 500 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
 * Serving Flask app "JinjaServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
[2017-11-09 13:57:32,667] ERROR in app: Exception on /Basic2 [GET]
Traceback (most recent call last):
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 21, in returnSecond
    return render_template('0-1_Basic.html', data = 'Hello World')
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 133, in render_template
    return _render(ctx.app.jinja_env.get_or_select_template(template_name_or_list),
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 869, in get_or_select_template
    return self.get_template(template_name_or_list, parent, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 830, in get_template
    return self._load_template(name, self.make_globals(globals))
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 804, in _load_template
    template = self.loader.load(self, name, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\loaders.py", line 113, in load
    source, filename, uptodate = self.get_source(environment, name)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 57, in get_source
    return self._get_source_fast(environment, template)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 85, in _get_source_fast
    raise TemplateNotFound(template)
jinja2.exceptions.TemplateNotFound: 0-1_Basic.html
127.0.0.1 - - [09/Nov/2017 13:57:32] "GET /Basic2 HTTP/1.1" 500 -
127.0.0.1 - - [09/Nov/2017 13:57:37] "GET /Basic HTTP/1.1" 200 -
[2017-11-09 13:57:52,095] ERROR in app: Exception on /Basic2 [GET]
Traceback (most recent call last):
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 21, in returnSecond
    return render_template('0-1_Basic.html', data = 'Hello World')
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 133, in render_template
    return _render(ctx.app.jinja_env.get_or_select_template(template_name_or_list),
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 869, in get_or_select_template
    return self.get_template(template_name_or_list, parent, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 830, in get_template
    return self._load_template(name, self.make_globals(globals))
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 804, in _load_template
    template = self.loader.load(self, name, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\loaders.py", line 113, in load
    source, filename, uptodate = self.get_source(environment, name)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 57, in get_source
    return self._get_source_fast(environment, template)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 85, in _get_source_fast
    raise TemplateNotFound(template)
jinja2.exceptions.TemplateNotFound: 0-1_Basic.html
127.0.0.1 - - [09/Nov/2017 13:57:52] "GET /Basic2 HTTP/1.1" 500 -
[2017-11-09 13:58:12,982] ERROR in app: Exception on /Basic2 [GET]
Traceback (most recent call last):
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 21, in returnSecond
    return render_template('0-1_Basic.html', data = 'Hello World')
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 133, in render_template
    return _render(ctx.app.jinja_env.get_or_select_template(template_name_or_list),
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 869, in get_or_select_template
    return self.get_template(template_name_or_list, parent, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 830, in get_template
    return self._load_template(name, self.make_globals(globals))
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\environment.py", line 804, in _load_template
    template = self.loader.load(self, name, globals)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\jinja2\loaders.py", line 113, in load
    source, filename, uptodate = self.get_source(environment, name)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 57, in get_source
    return self._get_source_fast(environment, template)
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\flask\templating.py", line 85, in _get_source_fast
    raise TemplateNotFound(template)
jinja2.exceptions.TemplateNotFound: 0-1_Basic.html
127.0.0.1 - - [09/Nov/2017 13:58:12] "GET /Basic2 HTTP/1.1" 500 -
127.0.0.1 - - [09/Nov/2017 14:02:47] "GET /EX_1 HTTP/1.1" 404 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode

09/11/2017  13:47    <DIR>          .
09/11/2017  13:47    <DIR>          ..
09/11/2017  13:43    <DIR>          frameworkserver
09/11/2017  14:02             2,373 JinjaServer.py
09/11/2017  13:12    <DIR>          templates
09/11/2017  13:56    <DIR>          __pycache__
               1 File(s)          2,373 bytes
               5 Dir(s)  134,250,037,248 bytes free

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>cd templates

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates

09/11/2017  13:12    <DIR>          .
09/11/2017  13:12    <DIR>          ..
09/11/2017  13:51               292 0-2_Basic.html
07/11/2017  14:39               176 0_Basic.html
09/11/2017  10:19               291 1_json.html
09/11/2017  10:21               200 2_loops.html
07/11/2017  19:23               457 3_dictionary.html
06/11/2016  23:07               290 4_inheritance.html
09/11/2017  08:25               124 5_inheritance.html
09/11/2017  14:00               388 EX_1Simple.html
09/11/2017  10:22               338 EX_2directoryForm.html
               9 File(s)          2,556 bytes
               2 Dir(s)  134,250,037,248 bytes free

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>flask run
Usage: flask run [OPTIONS]

Error: The file/path provided (JinjaServer.py) does not appear to exist.  Please verify the path is correct.  If app is not on PYTHONPATH, ensure the extension is .py

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>flask run
Usage: flask run [OPTIONS]

Error: The file/path provided (JinjaServer.py) does not appear to exist.  Please verify the path is correct.  If app is not on PYTHONPATH, ensure the extension is .py

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>..cd
'..cd' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>..cd
'..cd' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>dir
 Volume in drive C is Windows
 Volume Serial Number is 2AB5-E52C

 Directory of C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates

09/11/2017  13:12    <DIR>          .
09/11/2017  13:12    <DIR>          ..
09/11/2017  13:51               292 0-2_Basic.html
07/11/2017  14:39               176 0_Basic.html
09/11/2017  10:19               291 1_json.html
09/11/2017  10:21               200 2_loops.html
07/11/2017  19:23               457 3_dictionary.html
06/11/2016  23:07               290 4_inheritance.html
09/11/2017  08:25               124 5_inheritance.html
09/11/2017  14:00               388 EX_1Simple.html
09/11/2017  10:22               338 EX_2directoryForm.html
               9 File(s)          2,556 bytes
               2 Dir(s)  134,250,037,248 bytes free

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>..cd
'..cd' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates>cd..

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
 * Serving Flask app "JinjaServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 14:09:31] "GET /Json HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:11:46] "GET /Json HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:12:41] "GET /Json HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:12:42] "GET /Json HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:14:12] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:01] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:20] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:21] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:21] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:21] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:21] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:15:21] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:21:10] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:22:52] "GET /Loops HTTP/1.1" 200 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>flask run
 * Serving Flask app "JinjaServer"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 14:26:34] "GET /Loops HTTP/1.1" 200 -
----------------------------------------
Exception happened during processing of request from ('127.0.0.1', 53329)
Traceback (most recent call last):
  File "c:\python35\Lib\socketserver.py", line 313, in _handle_request_noblock
    self.process_request(request, client_address)
  File "c:\python35\Lib\socketserver.py", line 341, in process_request
    self.finish_request(request, client_address)
  File "c:\python35\Lib\socketserver.py", line 354, in finish_request
    self.RequestHandlerClass(request, client_address, self)
  File "c:\python35\Lib\socketserver.py", line 681, in __init__
    self.handle()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\werkzeug\serving.py", line 232, in handle
    rv = BaseHTTPRequestHandler.handle(self)
  File "c:\python35\Lib\http\server.py", line 422, in handle
    self.handle_one_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\werkzeug\serving.py", line 263, in handle_one_request
    self.raw_requestline = self.rfile.readline()
  File "c:\python35\Lib\socket.py", line 576, in readinto
    return self._sock.recv_into(b)
KeyboardInterrupt
----------------------------------------
127.0.0.1 - - [09/Nov/2017 14:27:10] "GET /Loops HTTP/1.1" 200 -
----------------------------------------
Exception happened during processing of request from ('127.0.0.1', 53345)
Traceback (most recent call last):
  File "c:\python35\Lib\socketserver.py", line 313, in _handle_request_noblock
    self.process_request(request, client_address)
  File "c:\python35\Lib\socketserver.py", line 341, in process_request
    self.finish_request(request, client_address)
  File "c:\python35\Lib\socketserver.py", line 354, in finish_request
    self.RequestHandlerClass(request, client_address, self)
  File "c:\python35\Lib\socketserver.py", line 681, in __init__
    self.handle()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\werkzeug\serving.py", line 232, in handle
    rv = BaseHTTPRequestHandler.handle(self)
  File "c:\python35\Lib\http\server.py", line 422, in handle
    self.handle_one_request()
  File "c:\users\c1712480\onedri~1\semest~1\intro_~1\framew~1\studen~1\framew~1\lib\site-packages\werkzeug\serving.py", line 263, in handle_one_request
    self.raw_requestline = self.rfile.readline()
  File "c:\python35\Lib\socket.py", line 576, in readinto
    return self._sock.recv_into(b)
KeyboardInterrupt
----------------------------------------
127.0.0.1 - - [09/Nov/2017 14:27:17] "GET /Loops HTTP/1.1" 200 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>
(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>
(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>
(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>JinjaServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 187-046-699
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 14:28:18] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:28:19] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:28:27] "GET /Loops HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:29:24] "GET /EX_2directoryForm.html HTTP/1.1" 404 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>JinjaServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 187-046-699
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 14:29:37] "GET /EX_2directoryForm.html HTTP/1.1" 404 -
127.0.0.1 - - [09/Nov/2017 14:30:12] "GET /EX_2 HTTP/1.1" 200 -
 * Detected change in 'C:\\Users\\c1712480\\OneDrive - Cardiff University\\Semester_1\\Intro_webdev\\framework\\StudentCode\\JinjaServer.py', reloading
 * Restarting with stat
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 70
    dictionary = ["Wendy": "2222", "Ian": "0000", "Chris": "1111"]
                         ^
SyntaxError: invalid syntax

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>JinjaServer.py
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 70
    dictionary = ["Wendy": "2222", "Ian": "0000", "Chris": "1111"]
                         ^
SyntaxError: invalid syntax

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>JinjaServer.py
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 71
    return render_template('EX_2directoryForm.html' data = dictionary)
                                                       ^
SyntaxError: invalid syntax

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>JinjaServer.py
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 187-046-699
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2 HTTP/1.1" 500 -
Traceback (most recent call last):
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1997, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1985, in wsgi_app
    response = self.handle_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1540, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1982, in wsgi_app
    response = self.full_dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1614, in full_dispatch_request
    rv = self.handle_user_exception(e)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1517, in handle_user_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\_compat.py", line 33, in reraise
    raise value
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1612, in full_dispatch_request
    rv = self.dispatch_request()
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1598, in dispatch_request
    return self.view_functions[rule.endpoint](**req.view_args)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\JinjaServer.py", line 71, in returnDir
    return render_template('EX_2directoryForm.html', data = dictionary)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\templating.py", line 134, in render_template
    context, ctx.app)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\templating.py", line 116, in _render
    rv = template.render(context)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\jinja2\environment.py", line 1008, in render
    return self.environment.handle_exception(exc_info, True)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\jinja2\environment.py", line 780, in handle_exception
    reraise(exc_type, exc_value, tb)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\jinja2\_compat.py", line 37, in reraise
    raise value.with_traceback(tb)
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode\templates\EX_2directoryForm.html", line 15, in top-level template code
    {%for key,value in  data.dictionary() %}
jinja2.exceptions.UndefinedError: 'dict object' has no attribute 'dictionary'
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=style.css HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=jquery.js HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=debugger.js HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=ubuntu.ttf HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -
127.0.0.1 - - [09/Nov/2017 14:39:08] "GET /EX_2?__debugger__=yes&cmd=resource&f=console.png HTTP/1.1" 200 -

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>..cd
'..cd' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework\StudentCode>cd..

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\framework>cd..

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev>cd takeaway

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Takeaway>home.py
'home.py' is not recognized as an internal or external command,
operable program or batch file.

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Takeaway>takeawayServer.py

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Takeaway>takeawayServer.py
Traceback (most recent call last):
  File "C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Takeaway\takeawayServer.py", line 15, in <module>
    @app.route("/Menu", methods=['GET'])
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1080, in decorator
    self.add_url_rule(rule, endpoint, f, **options)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 64, in wrapper_func
    return f(self, *args, **kwargs)
  File "C:\Users\c1712480\ONEDRI~1\SEMEST~1\INTRO_~1\FRAMEW~1\STUDEN~1\FRAMEW~1\lib\site-packages\flask\app.py", line 1051, in add_url_rule
    'existing endpoint function: %s' % endpoint)
AssertionError: View function mapping is overwriting an existing endpoint function: returnFirst

(FRAMEW~1) C:\Users\c1712480\OneDrive - Cardiff University\Semester_1\Intro_webdev\Takeaway>
```
