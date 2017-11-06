
# How (and where) could you construct dynamic content?

- Ask for webpage, construct webpage, run javascrpt goes to server, javascript used to manipulate the dom, puts content on the webpage

- HTML template loadup (one off thing), populate server side, server does all the route manipulation


**Discuss: pros and cons**

- client or server pay for time

# Creating Dynamic content: Ajax

Asynchronous JavaScript And XML

Calls a server route and continues. 
When the server route returns
 execute the onload(e) function. 

xhttp.open("GET", "/txt", true);
Use GET or other http verbs
Route
Synchronous (true) or asynchronous  (false)
[w3schools ajax](http://www.w3schools.com/xml/ajax_intro.asp)  

**Synchronos**- Stuck in loop waiting, then send of next request for next piece of data, waiting for response

**Asynchronos**- Send off a message and then ignore it. Send off requests, the first that comes back gets processed into the page, not nesecarrily the first to be sent to the server. Buttons will work in the meantime
