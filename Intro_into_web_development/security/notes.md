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
while (c.charAt(0) == ' ') c = c.substring(1, c.length);
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
