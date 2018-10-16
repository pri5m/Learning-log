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
# Thymeleaf forms

[Slides](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4835113_1&course_id=_387554_1)

Returning ModelAndView object.
“addPerson” is the name of the view
It is odd that the constructor won’t take a
Model object, so you have to get it’s
internal Map and pass that in.
```
@RequestMapping(value = "/addPerson", method = RequestMethod.GET)
public ModelAndView addPerson(Model model) {
Person aPerson = new Person();
model.addAttribute("person", aPerson);
return new ModelAndView(
"addPerson",
(Map<String, ?>) model.asMap());
}
```

Might want to populate the form with exisiting values for an update form rather than a new form

```
<form action = "#" th:action = "@{/addPerson}"
#th:object = "${person}" method = "post" >
<input type = "text" th:field = "*{name}" />
<input type = "text" th:field = "*{age}" />
<input type = "radio" th:field = "*{gender}" th:value = "MALE" />
<input type = "radio" th:field = "*{gender}" th:value = "FEMALE" />
<button type = "submit" >Submit</button >
</form >
```

Handling a post
```
@RequestMapping(value = "/addPerson", method = RequestMethod.POST)
public ModelAndView addPersonFromForm(@Valid Person someone,
BindingResult bindingResult, Model model) {
System.out.println("Form Received");
System.out.println(someone);
model.addAttribute("person", someone);
return new ModelAndView("addPerson", model.asMap());
}
```

# Exersize

**PersonController.java**
```java
@RestController
public class PersonController {

    List<Person> people = new ArrayList<Person>();
    @RequestMapping(value = "/addPerson", method = RequestMethod.GET)
    public ModelAndView addPerson(Model model) {
        Person aPerson = new Person();
        model.addAttribute("person", aPerson);
        model.addAttribute("people", people);
        return new ModelAndView("addPerson", model.asMap());
    }

    @RequestMapping(value = "/addPerson", method = RequestMethod.POST)
    public ModelAndView addPersonFromForm(@Valid Person someone, BindingResult bindingResult, Model
            model) {
        System.out.println("Form Received");
        System.out.println(someone.getName() + ", " + someone.getAge() + ", " + someone.getGender());
        model.addAttribute("person", someone);
        people.add(someone);
        model.addAttribute("people", people);
        return new ModelAndView("addPerson", model.asMap());
    }
}
```

**addPerson.html**
```html
<!DOCTYPE html>
<html  lang="en" xmlns:th="http://thymeleaf.org">
    <head>
        <meta charset="UTF-8">
        <title>Beans</title>
        <meta http-equiv="Consent-Type" content="text/html"; charset="UTF-8"/>
    </head>
    <body>
        <h1>Person form</h1>

        <div th:each = "person : ${people}" >
            <div th:object = "${person}" >
                <span th:text = "*{name}" ></span>
                <span th:text = "*{age}" ></span>
                <span th:text = "*{gender}" ></span>
            </div >
        </div >

        <form action = "#" th:action = "@{/addPerson}" th:object = "${person}" method = "post" >
            <input type = "text" th:field = "*{name}" />
            <input type = "text" th:field = "*{age}" />
            <input type = "radio" th:field = "*{gender}" th:value="MALE" />
            <input type = "radio" th:field = "*{gender}" th:value="FEMALE" />
            <button type="submit">Submit</button>
        </form>
    </body>
</html>
```
