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


