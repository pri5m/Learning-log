# Intro into Spring

## Dependency injection

[Martin Fowler- Injection](https://www.martinfowler.com/articles/injection.html)

Create a diary for technical descisiosn as well as the agile diary

## Module success

• Write a Spring Boot Application

• Use the right Spring Boot components

• Know their place in an architecture

• Combine components correctly

• Understand the design motivations

• Enable rapid change of the application

• Consider framework development trade-offs

• Treat the materials as a foundation

• Treat the project as a catalyst for learning

• Combine the module learning

## To run

Gradle -> application -> bootRun

## Port already in use

Close the other running tab and rebuild

If the problem persists then change the server port go to application.properties and change the port number
```server.port=9090```


## Example

controller/HelloWorldDateTime.java
```
@RestController
public class HelloWorldDateTime {

    @RequestMapping("/test")
    public String index(){
        return "Hello from Spring Boot. Today is : " + new SimpleDateFormat("dd/MM/yyyy").format(new Date());
    }
}
```

Class-level annotation: @RestController

Registers that class with Spring Boot as a control bean. Body of the reponse from HTTP

Method-level annotation: @RequestMapping

Tells Spring Boot to route web requests on the stated URL pattern to this method

## Request param annotation

```

    @RequestMapping("/")
    public String index(
            @RequestParam(value="name",defaultValue="World") String name){
        return "Hello " + name + " from Spring Boot. Today is : " + new SimpleDateFormat("dd/MM/yyyy").format(new
        Date());
    }
```
http://localhost:8080/?name=Holly

Output:
```Hello Holly from Spring Boot. Today is : 09/10/2018```
