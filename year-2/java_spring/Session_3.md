# Templating

[Difference between controller and restcontroller](https://www.javacodegeeks.com/2017/08/difference-restcontroller-controller-annotation-spring-mvc-rest.html)

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
