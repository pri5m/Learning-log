
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
