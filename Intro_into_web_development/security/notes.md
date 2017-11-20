# What are sessions?

• “A continuous series of sittings / meetings / activities …”

• In Web Development –

• A period, during which conversation data can be persistently accessed
between the server and the client.

• When the session is over, the data is removed. 

# Cookies: Server-side processing

**European cookie law**

You must tell people if you set cookies, and clearly explain what the
cookies do and why

Alerts are not a good option as they are sometimes blocked!


• Create the response

• Render the template

• Set cookie in the response

• Return the response

• For using the cookie values
```
from flask import request, make_response
…
resp = make_response(render_template('Customer.html',….
resp.set_cookie('username', uName)
return resp
…
…
username = request.cookies.get('username')
```
# Cookies: Client side storage.

• Look at the cookies

• Chrome>settings>advances Settings> content settings>all cookies and site
data

• Cookies are related to a domain!

• Cookies are created on client or the server and added to the header

• Look at the request and response headers.

• Restart server – session should remain – check expiry

# Cookies: Client-side processing - set

• document.cookie

• Most of this is about
setting the date.

```
function setCookie(cname, cvalue, exdays) {
var d = new Date();
d.setTime(d.getTime() + (exdays*24*60*60*1000));
var expires = "expires="+ d.toUTCString();
document.cookie = cname + "=" +
cvalue + ";" + expires + ";path=/";
}
```

```
Basically creating a string - “cname=cvalue;expires=XXXX;path=/”
```
```
function loadBasket(){
var shopping = document.getElementById('shopping').value;
console.log(shopping);
setCookie('basket', shopping, 1);
}
```
eg
```
<script>
    function loadBasket(){
      var shopping = document.getElementById('shopping').value;
      console.log(shopping);
      setCookie('basket', shopping, 1);
    }

    function setCookie(cname, cvalue, exdays) {
        alert('I accept that this site will set cookies')
        var d = new Date();
        // d.setTime(d.getTime() + (exdays*24*60*60*1000));
        d.setTime(d.getTime() + (exdays*20*1000)); //20 seconds
        var expires = "expires="+ d.toUTCString();
        document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
    }
  </script>
```

# Cookies: Client-side processing - read
• Handling of the cookie
string in java script.

• Split by ‘;’ into
key/values

• Search for the required
sub string,

• Remove leading spaces

• Extract and return
value


• The reason is there
may be more than one
cookie.
```
function readCookie(name) {
var nameEQ = name + "=";
var ca = document.cookie.split(';');
for (var i = 0; i < ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == ' ') c = c.substring(1, c.length); #Removes whitespace, checks to see if there is a space infrom of the string
    if (c.indexOf(nameEQ) == 0) {
        return c.substring(nameEQ.length, c.length);
    }
 }
 return null;
}
```
```
username=ian; basket=oil,filter,bolt,washer
```
# Discussion

*Thinking about the shopping example*

• When could this be useful?

- Keep username in there

- Can change the prices- manipulate the cookies

• When could this not be good?



• When could this be dangerous?

# Signed Cookie Sessions:

• More modules

• Need a server side
secret key

• Create session data

• Retrieve session Data

• THIS IS NOT SECURE!!!

• https://blog.miguelgri
nberg.com/post/howsecure-is-the-flaskuser-session

• But is signed

```
from flask import Flask, redirect,
request, render_template,
make_response, escape , session
```
```
app.secret_key = 'fj590Rt?h40gg'
…
session['username'] = request.form['username']
…
username = escape(session['username'])
…
```
# Basic Restricted Access: There is no security in this yet!!!

In the login function
```
if (uName =="Ian"):
    session['usertype'] = 'Admin'
else:
    session['usertype'] = 'Customer'
```

In the /Admin route
```
@app.route("/Admin")def admin():
 username = request.cookies.get('username')
 usertype = "null" if 'usertype' in session:
  usertype = escape(session['usertype'])
 if usertype == "Admin":
    return render_template('Admin.html', msg = '', username = username)
 else:
    return render_template('Customer.html', msg = 'no access ', username = username)
```
