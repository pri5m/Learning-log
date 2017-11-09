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
