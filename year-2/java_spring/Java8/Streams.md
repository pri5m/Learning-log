# Streams

## What is a stream?

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
