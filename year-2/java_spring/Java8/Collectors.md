# Collectors

## groupingBy collector

[Source](https://www.baeldung.com/java-groupingby-collector)

The SQL GROUP BY clause has similar functionality in Java 8 by using Collectors.groupingBy() and Collectors.groupingByConcurrent()

They are used for grouping objects by some property and storing results in a Map instance

**Simple grouping by a Single column**
```
Map<BlogPostType, List<BlogPost>> postsPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType));
```

**Grouping by with a complex Map key type**
```
Map<Tuple, List<BlogPost>> postsPerTypeAndAuthor = posts.stream()
  .collect(groupingBy(post -> new Tuple(post.getType(), post.getAuthor())));
```

**Modifying the returned Map value type**
```
Map<BlogPostType, Set<BlogPost>> postsPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType, toSet()));
```

**Providing a secondary group by collector**
```
Map<String, Map<BlogPostType, List>> map = posts.stream()
  .collect(groupingBy(BlogPost::getAuthor, groupingBy(BlogPost::getType)));
```

**Getting the Sum from grouped results**
```
Map<BlogPostType, Integer> likesPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType, summingInt(BlogPost::getLikes)));
```

**Getting the max or min from grouped results**
```
Map<BlogPostType, Optional<BlogPost>> maxLikesPerPostType = posts.stream()
  .collect(groupingBy(BlogPost::getType,
  maxBy(comparingInt(BlogPost::getLikes))));
```

**Getting a summary for an attribute of grouped results**
```
Map<BlogPostType, IntSummaryStatistics> likeStatisticsPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType, 
  summarizingInt(BlogPost::getLikes)));
```

**Mapping grouped results to a different type**
```
Map<BlogPostType, String> postsPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType, 
  mapping(BlogPost::getTitle, joining(", ", "Post titles: [", "]"))));
```

**Modifying the return Map type**
```
EnumMap<BlogPostType, List<BlogPost>> postsPerType = posts.stream()
  .collect(groupingBy(BlogPost::getType, 
  () -> new EnumMap<>(BlogPostType.class), toList()));
```

