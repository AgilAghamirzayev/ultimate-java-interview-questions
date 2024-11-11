# Java Stream interview questions


**1. What is the difference between map and flat map**

- `map` is used to transform each element of a collection independently and returns a new collection with the
  transformed elements.
- `flatMap` is used to transform each element of a collection into a sequence of elements and then flatten the
  sequences into a single collection.

In other words, map applies a one-to-one transformation to each element, while flatMap applies a one-to-many
transformation and flattens the resulting sequences into a single collection.

Example using map:

    List<String> words = Arrays.asList("Hello", "world");
    List<Integer> wordLengths = words.stream()
                                     .map(String::length)
                                     .collect(Collectors.toList());
    // Result: [5, 5]

Example using flatMap:

    List<List<Integer>> listOfLists = Arrays.asList(Arrays.asList(1, 2), Arrays.asList(3, 4));
    List<Integer> flattenedList = listOfLists.stream()
                                             .flatMap(List::stream)
                                             .collect(Collectors.toList());
    // Result: [1, 2, 3, 4]

