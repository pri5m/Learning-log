# More templating

[Thymeleaf 2](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4835110_1&course_id=_387554_1)

Some th: attributes have used ‘$’ and others ‘#’.

There are more…

$ = variable expressions

# = message expressions

```*``` = selection variable expressions

@ = link URL expressions

```
Standard link
<a href="/err.html">Error</a>

th:href replace href
<a href="/err.html" th:href="@{/index.html}">Index</a>

URL parameter
<a href="/hello?name=MyName"
th:href="@{/hello/{name}(name=${name})}">Say Hello with ReST</a>

Request parameter
<a href="/?name=MyName"
th:href="@{/(name=${name})}">Dynamic Hello</a>
```

