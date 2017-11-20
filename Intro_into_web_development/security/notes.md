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

