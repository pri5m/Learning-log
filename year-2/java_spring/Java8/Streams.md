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

IntStream, LongStream, DoubleStream

IntStreams can replace the regular for-loop utilizing IntStream.range():

```
IntStream.range(1, 4)
    .forEach(System.out::println);

// 1
// 2
// 3
```
All those primitive streams work just like regular object streams with the following differences: Primitive streams use specialized lambda expressions, e.g. IntFunction instead of Function or IntPredicate instead of Predicate. And primitive streams support the additional terminal aggregate operations sum() and average():

```
Arrays.stream(new int[] {1, 2, 3})
    .map(n -> 2 * n + 1)
    .average()
    .ifPresent(System.out::println);  // 5.0
```

Sometimes it's useful to transform a regular object stream to a primitive stream or vice versa. For that purpose object streams support the special mapping operations mapToInt(), mapToLong() and mapToDouble:

```
Stream.of("a1", "a2", "a3")
    .map(s -> s.substring(1))
    .mapToInt(Integer::parseInt)
    .max()
    .ifPresent(System.out::println);  // 3
```
Primitive streams can be transformed to object streams via mapToObj():

```
IntStream.range(1, 4)
    .mapToObj(i -> "a" + i)
    .forEach(System.out::println);

// a1
// a2
// a3
```

Here's a combined example: the stream of doubles is first mapped to an int stream and than mapped to an object stream of strings:

```
Stream.of(1.0, 2.0, 3.0)
    .mapToInt(Double::intValue)
    .mapToObj(i -> "a" + i)
    .forEach(System.out::println);

// a1
// a2
// a3
```

### Parallel streams
Streams can be executed in parallel to increase runtime performance on large amount of input elements. Parallel streams use a common ForkJoinPool available via the static ForkJoinPool.commonPool() method. The size of the underlying thread-pool uses up to five threads - depending on the amount of available physical CPU cores:
```
ForkJoinPool commonPool = ForkJoinPool.commonPool();
System.out.println(commonPool.getParallelism());    // 3
```

