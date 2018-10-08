# Streams

## What is a stream?

[Source](https://winterbe.com/posts/2014/07/31/java8-stream-tutorial-examples/)

A stream represents a sequence of elements and supports different kind of operations to perform computations upon those elements:
```Java
List<String> myList =
    Arrays.asList("a1", "a2", "b1", "c2", "c1");

myList
    .stream()
    .filter(s -> s.startsWith("c"))
    .map(String::toUpperCase)
    .sorted()
    .forEach(System.out::println);

// C1
// C2
```
Stream operations are either intermediate or terminal. Intermediate operations return a stream so we can chain multiple intermediate operations without using semicolons. Terminal operations are either void or return a non-stream result. In the above example filter, map and sorted are intermediate operations whereas forEach is a terminal operation.

[Streams Javadoc](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html)

## What type of streams are there?

### Sequential streams

#### Stream.of()
```
Arrays.asList("a1", "a2", "a3")
    .stream()
    .findFirst()
    .ifPresent(System.out::println);  // a1
```

Can be refactored to:
```
Stream.of("a1", "a2", "a3")
    .findFirst()
    .ifPresent(System.out::println);  // a1
```
Just use Stream.of() to create a stream from a bunch of object references.

#### Primitive data types


### Parallel streams
