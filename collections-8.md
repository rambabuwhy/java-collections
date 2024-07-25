# Collections-8

## Iterating List:

In Java, the `java.util` package provides several implementations of the `List` interface. Here are the main types of list collections, along with examples of how to insert elements and iterate over them:

1. **ArrayList**
2. **LinkedList**
3. **Vector**
4. **Stack**

#### 1. ArrayList

`ArrayList` is a resizable array implementation of the `List` interface. It allows duplicate elements and provides fast random access.

```java
import java.util.ArrayList;
import java.util.List;

public class ArrayListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();

        // Inserting elements
        list.add("One");
        list.add("Two");
        list.add("Three");

        // Iterating over elements
        for (String element : list) {
            System.out.println(element);
        }
    }
}
```

#### 2. LinkedList

`LinkedList` is a doubly linked list implementation of the `List` interface. It allows null elements and provides better performance for insertions and deletions.

```java
import java.util.LinkedList;
import java.util.List;

public class LinkedListExample {
    public static void main(String[] args) {
        List<String> list = new LinkedList<>();

        // Inserting elements
        list.add("One");
        list.add("Two");
        list.add("Three");

        // Iterating over elements
        for (String element : list) {
            System.out.println(element);
        }
    }
}
```

#### 3. Vector

`Vector` is a synchronized implementation of the `List` interface. It is similar to `ArrayList` but is thread-safe and generally slower.

```java
import java.util.List;
import java.util.Vector;

public class VectorExample {
    public static void main(String[] args) {
        List<String> list = new Vector<>();

        // Inserting elements
        list.add("One");
        list.add("Two");
        list.add("Three");

        // Iterating over elements
        for (String element : list) {
            System.out.println(element);
        }
    }
}
```

#### 4. Stack

`Stack` is a last-in, first-out (LIFO) stack implementation of the `List` interface. It extends `Vector` and provides methods for stack operations.

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();

        // Inserting elements
        stack.push("One");
        stack.push("Two");
        stack.push("Three");

        // Iterating over elements
        while (!stack.isEmpty()) {
            System.out.println(stack.pop());
        }
    }
}
```

#### Summary

* **ArrayList**: Best for frequent access and fewer modifications.
* **LinkedList**: Best for frequent insertions and deletions.
* **Vector**: Thread-safe but generally slower.
* **Stack**: Provides stack-specific operations.
