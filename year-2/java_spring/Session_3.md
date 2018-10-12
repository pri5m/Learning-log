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

 src/m ain/resources/templates/greeting.html
 ```html
 <!DOCTYPE HTML>
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
