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

Enter info into a form and the info is them retrieved and displayed to the user

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

Add attribute is basically a key value pair the key is used in the thymeleaf template 

# Sessions

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4835114-dt-content-rid-11854591_2/courses/1819-CM6213/Slides/Spring%20Boot/W2.11%20-%20Sessions%20and%20Double%20Submits.pdf)

[Redirect and forwards](https://www.baeldung.com/spring-redirect-and-forward)

# Singleton

[Slide](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4842093_1&course_id=_387554_1)

```java
public class ClassicSingleton {
private static ClassicSingleton instance = null;
protected ClassicSingleton() {
// Exists only to defeat instantiation. }
public static ClassicSingleton getInstance() {
if(instance == null) {
instance = new ClassicSingleton();
}
return instance;
}
}
```

# Services

[Slides](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4842094_1&course_id=_387554_1)

## Remember what the controller is for

• It is adapting web requests into application
events

• A request to “/api/products” means deal with a “send product catalogue” event.

• The application handles the event, and returns objects to suit.

• The controller adapts that back to the web world.

• That event could be triggered by other means...

- IIOP, messaging, custom protocols, etc.

# Spring redirects

[Website link](https://www.baeldung.com/spring-redirect-and-forward)

## Why do a redirect?

There are many possible examples and reasons of course. One simple one might be POSTing form data, working around the double submission problem, or just delegating the execution flow to another controller method.

## RedirectView

```
@Controller
@RequestMapping("/")
public class RedirectController {
     
    @GetMapping("/redirectWithRedirectView")
    public RedirectView redirectWithUsingRedirectView(
      RedirectAttributes attributes) {
        attributes.addFlashAttribute("flashAttribute", "redirectWithRedirectView");
        attributes.addAttribute("attribute", "redirectWithRedirectView");
        return new RedirectView("redirectedUrl");
    }
}
```
Notice here how we’re injecting the redirect attributes into the method – the framework will do the heavy lifting here and allow us to interact with these attributes.

We’re adding the model attribute attribute – which will be exposed as HTTP query parameter. The model must contain only objects – generally Strings or objects that can be converted to Strings.

Using RedirectView – is suboptimal for a few reasons.

First- we’re now coupled to the Spring API because we’re using the RedirectView directly in our code.

Second – we now need to know from the start, when implementing that controller operation – that the result will always be a redirect – which may not always be the case.

## Redirect with the Prefix redirect

A better option is using the prefix redirect: – the redirect view name is injected into the controller like any other logical view name. The controller is not even aware that redirection is happening.

```
@Controller
@RequestMapping("/")
public class RedirectController {
     
    @GetMapping("/redirectWithRedirectPrefix")
    public ModelAndView redirectWithUsingRedirectPrefix(ModelMap model) {
        model.addAttribute("attribute", "redirectWithRedirectPrefix");
        return new ModelAndView("redirect:/redirectedUrl", model);
    }
}
```

When a view name is returned with the prefix redirect: – the UrlBasedViewResolver (and all its subclasses) will recognize this as a special indication that a redirect needs to happen. The rest of the view name will be used as the redirect URL.

A quick but important note here is that – when we use this logical view name here – redirect:/redirectedUrl – we’re doing a redirect relative to the current Servlet context.

We can use a name such as a redirect: http://localhost:8080/spring-redirect-and-forward/redirectedUrl if we need to redirect to an absolute URL.

So now, when we execute the curl command:

```curl -i http://localhost:8080/spring-rest/redirectWithRedirectPrefix```

We’ll immediately get redirected:

```
HTTP/1.1 302 Found
Server: Apache-Coyote/1.1
Location: 
  http://localhost:8080/spring-rest/redirectedUrl?attribute=redirectWithRedirectPrefix
```

## Forward with the prefix foward

Before the code, let’s go over a quick, high-level overview of the semantics of forward vs. redirect:

- redirect will respond with a 302 and the new URL in the Location header; the browser/client will then make another request to the new URL

- forward happens entirely on a server side; the Servlet container forwards the same request to the target URL; the URL won’t change in the browser

