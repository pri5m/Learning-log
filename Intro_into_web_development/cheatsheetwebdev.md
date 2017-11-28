# HTMl and Semantic tagging
**Bulleted list**
<ul>
  <li></li>
</ul>

**Numbered list**
<ol>
  <li></li>
</ol>

**Line break**
<br>

**Semantic tagging**
<nav> Site or in page navigation
<article> News article, weblog or forum post, ect.
<aside> Sidebar, comments section, footnote ect.
<figure> One or more images, graphics, code samples ect.
<section> A section of the page or a chapter of <article>
<p> paragraph

# CSS basic styling



# Layout using different box models



# JavaScript



# JavaScript form validation
*x and y must be filled out, telephone number check*
*Put in head*
```html
<script>
  function filloutForm() {
      var name = document.forms["getInTouch"]["name"].value;
      var tel = document.forms["getInTouch"]["tel"].value;
      if (name == "") {
        alert("Name must be filled out");
        return false;
      }
      if (tel == "") {
        alert("Telephone must be filled out");
        return false;
      }
      return telValidation();
  }
  /* Adapted from: https://www.w3schools.com/js/tryit.asp?filename=tryjs_validation_number (retrived: 1/11/17) */
  function telValidation(){
    var tel = document.forms["getInTouch"]["tel"].value;
    // Could use regular expression instead //
    if (isNaN(tel) || x < 1 || x > 10) {
      alert("Please use numbers and numbers only");
      return false;
    }
  }
</script>
```

# Setting up and running a server
**Python (It's a python based server)**
*include this at the top*
  ```
  import os
  from flask import flask
  app = Flask(__name__)
  ```

*include this at the bottom*
  ```
  if __name__ == "__main__"':
        app.run(debug=True)
  ```

# Routes on a server



# Templating with jinja
**Rendering a template**
Template files must be in the template directory.

*Rendering Templates*
```
 from flask import Flask, request, render_template
...
@app.route("/Basic", methods=['GET'])
def returnFirst():
if request.method == 'GET':
*return render_template('0_Basic.html', data='Hello World')*
```

**Loops- lists**
py
days = ['mon','tues','wed','thurs','fri']
return render_template('2_loops.html', days = days)

HTMl
<ul>
{%for day in days %}
<li>{{day}}</li>
{% endfor %}
</ul>

**Loops- dictionaries**
*Python*
data = {'title':'HelloWorld',
'name':'Ian',
'message':'hi!',
'days': ['mon','tues','wed','thurs','fri']
}
return render_template('3_dictionary.html', data = data)

*HTMl*
<ul>
{%for key,value in data.items() %}
<li>{{value}},{{key}}</li>
{% endfor %}
</ul>

**Inheretance**
*A base file can be extended.*
• {%extends ‘base.html'%}

*Blocks can be overriden*
• {% block myBlock%} Bla Bla Bla {%endblock%}

*Or Called…*
   • {{ super() }}

*Parent*
<!doctype html>
<html>
<head>
  <title>Inheritance</title>
</head>
<body>
  <header>
    cool header stuff...........
  </header>

  {% block myBlock%}This is the parent content{%endblock%}

  <footer>
    even cooler footer stuff..............
  </footer>
</body>
</html>

*Child*
{%extends '4_inheritance.html'%}

{% block myBlock%}
{{ super() }}
<!-- Hi This is the child content -->
{%endblock%}


# Processing a form (std html flow)

*Print out something from the form once submitted*
```python

  names = []
  surnames = []

  @app.route("/HomeForm", methods=['POST', "GET"])
  def form():
      global names
      global surnames
      print("Processing form")
      if request.method == 'POST':
          name = request.form['firstname']
          surname = request.form['surname']
          names.append(name)
          surnames.append(surname)
      if request.method =='POST':   # shouldn't use get for adding data
          name = request.args.post('firstname')
          surname = request.args.post('surname')
          names.append(name)
          surnames.append(surname)
      print(names )
      print(surnames )
      return "Hello World!"
  ```

```html
  <body>
    <form action="/HomeForm" method="get" id="myForm">
      first name:
      <input type="text" name="firstname"><br>
      surname:
      <input type="text" name="surname"><br>
      <button type="submit"> submit </button>

    </form>
  </body>
```
# Processing a form with AJAX



# HTTP Requests
- GET
- POST
- DELETE
- PUT


# Simple SQl queries
- Create
```SQl
  CREATE TABLE IF NOT EXISTS `Students` (
    `ID`        INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
    `firstName`    TEXT NOT NULL,
    `surname`    TEXT NOT NULL,
    `termLocation`    TEXT NOT NULL,
    `homeLocation`  TEXT NOT NULL
  );

  ```

- Insert
```SQl
  INSERT INTO `Students`('firstName','surname', 'termLocation', 'homeLocation' ) VALUES ('Ian','Cooper','Cardiff',  'Devon');
  ```

*Hard coded student*
```Python
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
  ```
  
*Student inputted from form*
```Python
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

  ```

- Drop
*put at top*
```SQl
  DROP TABLE IF EXISTS Students;
  ```

- Select


# Python connectivity to SQLite3
