# Collections-1

Java provides a rich set of collection classes through the `java.util` package. Here’s an overview of the main types of collections in Java along with examples for each:

1. **List**
2. **Set**
3. **Queue**
4. **Map**

#### 1. List

A `List` is an ordered collection that can contain duplicate elements. Common implementations include `ArrayList`, `LinkedList`, and `Vector`.

**Example: ArrayList**

```java
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");
        list.add("Apple"); // List allows duplicates
        
        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}
```

#### 2. Set

A `Set` is a collection that cannot contain duplicate elements. Common implementations include `HashSet`, `LinkedHashSet`, and `TreeSet`.

**Example: HashSet**

```java
import java.util.HashSet;
import java.util.Set;

public class SetExample {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Cherry");
        set.add("Apple"); // Duplicate element, won't be added
        
        for (String fruit : set) {
            System.out.println(fruit);
        }
    }
}
```

#### 3. Queue

A `Queue` is used to hold multiple elements prior to processing. Common implementations include `LinkedList` and `PriorityQueue`.

**Example: LinkedList (as a Queue)**

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<>();
        queue.add("Apple");
        queue.add("Banana");
        queue.add("Cherry");
        
        while (!queue.isEmpty()) {
            System.out.println(queue.poll());
        }
    }
}
```

#### 4. Map

A `Map` is an object that maps keys to values. Common implementations include `HashMap`, `LinkedHashMap`, and `TreeMap`.

**Example: HashMap**

```java
import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();
        map.put("Apple", "Red");
        map.put("Banana", "Yellow");
        map.put("Cherry", "Red");
        
        for (Map.Entry<String, String> entry : map.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### Summary

* **List**: Ordered, allows duplicates. Examples: `ArrayList`, `LinkedList`.
* **Set**: Unordered, no duplicates. Examples: `HashSet`, `TreeSet`.
* **Queue**: Ordered collection for holding elements prior to processing. Examples: `LinkedList` (as a queue), `PriorityQueue`.
* **Map**: Key-value pairs, no duplicate keys. Examples: `HashMap`, `TreeMap`.
