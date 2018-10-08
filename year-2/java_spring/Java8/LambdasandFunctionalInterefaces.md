# Lambda Expressions and Functional Interfaces

[Source](https://www.baeldung.com/java-8-lambda-expressions-tips)

## Tips and best practices

### Prefer standard functional interfaces

Functional interfaces, which are gathered in the java.util.function package, satisfy most developers’ needs in providing target types for lambda expressions and method references. Each of these interfaces is general and abstract, making them easy to adapt to almost any lambda expression. Developers should explore this package before creating new functional interfaces.

```
Consider an interface Foo:

@FunctionalInterface
public interface Foo {
    String method(String string);
}

and a method add() in some class UseFoo, which takes this interface as a parameter:

public String add(String string, Foo foo) {
    return foo.method(string);
}

To execute it, you would write:

Foo foo = parameter -> parameter + " from lambda";
String result = useFoo.add("Message ", foo);
```
Look closer and you will see that Foo is nothing more than a function that accepts one argument and produces a result. Java 8 already provides such an interface in Function<T,R> from the java.util.function package.

Now we can remove interface Foo completely and change our code to:
```
public String add(String string, Function<String, String> fn) {
    return fn.apply(string);
}
```

To execute this, we can write:
```
Function<String, String> fn = 
  parameter -> parameter + " from lambda";
String result = useFoo.add("Message ", fn);
```

