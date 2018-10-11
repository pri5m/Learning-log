
## Url parameters

```
@RequestMapping(value = {"hello/{name}", "/hello"})
  public String hello(@PathVariable Optional<String> name){
    if (name.isPresent()){
      return "Hello " + name.get();
    }
    else{
      return "Hello Anonymous.";
    }
  }
```
```
http://localhost:8080/hello/holly
Hello holly
```

# Testing

F12 chrome

Look at the status code and content-type

```java
//Run it with JUnit
@RunWith(SpringJUnit4ClassRunner.class)
@SpringBootTest
//Create a mock server
@AutoConfigureMockMvc
public class helloSlashNameReturnsGreetingAndName {
    private MockMvc mvc;
  @Test
  public void getHello() throws Exception{
    mvc.perform( //Ask mock to perform request
      get("/hello/Slartibartfast")
    .contentType(MediaType.APPLICATION_JSON))
    .andDo(print())
    .andExpect(status().isOk()) // Check for 200
    .andExpect(content().string(equalTo("Hello Slartibartfast"))); // Check content
  }
}
```

```java
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.servlet.AutoConfigureMockMvc;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.http.MediaType;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.web.servlet.MockMvc;

import static org.hamcrest.Matchers.containsString;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultHandlers.print;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.content;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringBootTest
@AutoConfigureMockMvc
public class helloSlashNameReturnsGreetingAndName {

    @Autowired
    private MockMvc mockMvc;

    @Test
    public void getHello() throws Exception{
        this.mockMvc.perform(
                get("/hello/Slartibartfast")
                        .contentType(MediaType.APPLICATION_JSON))
                .andDo(print())
                .andExpect(status().isOk())
                .andExpect(content().string(containsString("Hello Slartibartfast")));
    }
}
```

# Forms

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4835105-dt-content-rid-11854573_2/courses/1819-CM6213/Slides/Spring%20Boot/W2.5%20-%20Handling%20form%20posts.pdf)

resources/templates/name.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <title>Form</title>
    </br>
    <form action="/name" method="post">
        <input type="text" name="name" id="name" value="Enter name"/>
    </form>
</body>
</html>
```

dto/NameForm.java
```java
import lombok.Data;
import javax.validation.constraints.NotBlank;

@Data
public class NameForm {

    @NotBlank(message="Name  is  required")
    private String Name;
}
```

controllers/FormController.java
```java
import com.cm6213.dependencytest.dto.NameForm;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.ModelAttribute;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

@Controller
public class FormController {

    @RequestMapping(path="/name", method = RequestMethod.GET)
    public Model getForm(Model model){
        return model;
    }

    @RequestMapping(path="/name", method = RequestMethod.POST)
    public String postName(@ModelAttribute NameForm in_form, Model model){
        System.out.println("name equals" + in_form.getName());
        return "redirect:/";
    }
}
```

# MVC

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4835106-dt-content-rid-11854576_2/courses/1819-CM6213/Slides/Spring%20Boot/W2.6%20-%20Model-View-Controller.pdf)

1 Controller interprets user action

2 Select logic to call on model

3 Model returns data + next view

4 View renders using supplied data

