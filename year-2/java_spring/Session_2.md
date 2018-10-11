
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

```
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
