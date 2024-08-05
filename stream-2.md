# stream-2

## flatMap:

In Java Streams, `flatMap` is a method used to transform each element of the stream into another stream and then flatten those streams into a single stream. This is particularly useful when dealing with nested structures or when you need to perform operations that produce multiple results for each input element.

Here’s an example to illustrate how `flatMap` works in Java Streams:

```java

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class FlatMapExample {
    public static void main(String[] args) {
        List<List<String>> nestedList = Arrays.asList(
            Arrays.asList("apple", "banana"),
            Arrays.asList("orange", "mango"),
            Arrays.asList("grapes", "kiwi")
        );

        List<String> flatList = nestedList.stream()
            .flatMap(List::stream)
            .collect(Collectors.toList());

        System.out.println(flatList);
    }
}
```

In this example:

1. We have a nested list of strings (`nestedList`), where each element is a list of fruits.
2. We use `flatMap` to transform each list within `nestedList` into a stream of strings and then flatten those streams into a single stream of strings.
3. Finally, we collect the results into a single list (`flatList`) and print it.

Output:

```csharp
[apple, banana, orange, mango, grapes, kiwi]
```

Here’s another example with more complex data structures:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

class Person {
    String name;
    List<String> phones;

    Person(String name, List<String> phones) {
        this.name = name;
        this.phones = phones;
    }

    List<String> getPhones() {
        return phones;
    }
}

public class FlatMapExample {
    public static void main(String[] args) {
        List<Person> persons = Arrays.asList(
            new Person("John", Arrays.asList("123", "456")),
            new Person("Jane", Arrays.asList("789", "101")),
            new Person("Jack", Arrays.asList("112", "131"))
        );

        List<String> allPhones = persons.stream()
            .flatMap(person -> person.getPhones().stream())
            .collect(Collectors.toList());

        System.out.println(allPhones);
    }
}
```

In this example:

1. We have a list of `Person` objects, each containing a list of phone numbers.
2. We use `flatMap` to transform each person's list of phone numbers into a stream of phone numbers and then flatten those streams into a single stream of phone numbers.
3. We collect the results into a single list (`allPhones`) and print it.

Output:

```csharp
[123, 456, 789, 101, 112, 131]
```

`flatMap` is powerful for handling nested structures and transforming complex data into a simpler, flat structure.
