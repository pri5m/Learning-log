# Templating

[Difference between controller and restcontroller](https://www.javacodegeeks.com/2017/08/difference-restcontroller-controller-annotation-spring-mvc-rest.html)

[Thymeleaf doc](https://www.thymeleaf.org/documentation.html)

controllers/GreetingControler.java
```Java
@Controller
public class GreetingController {
 @RequestMapping("/greeting")
 public String greeting(
 @RequestParam(
 value = "name", required = false,
 defaultValue = "World") String name,
 Model model) {
 model.addAttribute("name", name);
 return "greeting";
 }
}
```
Model object is this object used to pass data back to the next view so it has to be added as a attribute of key values pairs.

The return in this case 'greeting'. Spring will look for a template called 'greeting'

 src/m ain/resources/templates/greeting.html
```html
<html xmlns:th="http://www.thymeleaf.org">
  <head>
  <title>Getting Started: Serving Web
  Content</title>
  <meta http-equiv="Content-Type"
  content="text/html; charset=UTF-8" />
  </head>
  <body>
    <p th:text="'Hello, ' + ${name} + '!'" />
  </body>
</html>
```
$ indicates timeleaaf attribute and the {} will be used to look into the controller

Then the new html  page will be returned
 
 ```
 http://localhost:8080/greeting/?name=Holly
 Hello, Holly!
 ```
 
 Alternatively
 ```html
<body>
  <p th:text = "'Hello from Thymeleaf, ' + ${name} +'!'" />
  <p >Hello from Thymeleaf <span th:text = "${name}">Dave</span ></p >
</body>
```
Open file in windows explorer double click to see default value.

## Getting messages froom properties

resources/locale

new file messages.properties

locale can support internationalisation- could support different languages

## Accessing lists

controller/GreetingController.java
```
@Controller
public class GreetingController {

    @RequestMapping("/greeting")
    public String greeting(@RequestParam(value = "name", required = false, defaultValue = "World") String name, Model model) { 
        List<Person> people = Arrays.asList(
                new Person("Dave", 23, Gender.MALE),
                new Person("Rimmer", 31, Gender.MALE),
                new Person("Holly", 25, Gender.FEMALE),
                new Person("Mulder", 56, Gender.MALE),
                new Person("Scully", 48, Gender.FEMALE),
                new Person("Dave", 43, Gender.MALE)
        );
        List<Person> matches = people.stream().filter(p -> p.getName().equals(name)).collect(Collectors.toList());
        model.addAttribute("matches", matches);
        model.addAttribute("name", name);
        return "greeting";
    }
}
```

templates/greeting.html
```html
<html xmlns:th = "http://www.thymeleaf.org" >
    <head >
        <title >Getting Started: Serving Web Content</title >
        <meta http-equiv = "Content-Type" content = "text/html; charset=UTF-8" />
    </head >
    <body >

    <p >
        Today is: <span th:text = "${#calendars.format(#dates.createNow(),'dd MMMM yyyy')}" >13 May 2011</span >
    </p >

    <div th:each = "person : ${matches}" >
        <span th:text = "${person.name}" />
        <span th:text = "${person.age}" />
        <span th:text = "${person.gender}" />
    </div >

    </body >
</html >
```

Output
```
http://localhost:8080/greeting/?name=Dave
Today is: 12 October 2018

Dave 23 MALE
Dave 43 MALE
```
