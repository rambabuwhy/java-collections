# Collections-7

In Java, the `java.util` package provides several implementations of the `Map` interface. Here are the main types of map collections, along with examples of how to insert elements and iterate over them:

1. **HashMap**
2. **LinkedHashMap**
3. **TreeMap**
4. **Hashtable**
5. **ConcurrentHashMap**

#### 1. HashMap

`HashMap` is a hash table-based implementation of the `Map` interface. It allows null values and null keys and is unsynchronized.

```java
import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
    public static void main(String[] args) {
        Map<String, Integer> map = new HashMap<>();

        // Inserting elements
        map.put("One", 1);
        map.put("Two", 2);
        map.put("Three", 3);

        // Iterating over elements
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

#### 2. LinkedHashMap

`LinkedHashMap` is a hash table and linked list implementation of the `Map` interface, with predictable iteration order (insertion order or access order).

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class LinkedHashMapExample {
    public static void main(String[] args) {
        Map<String, Integer> map = new LinkedHashMap<>();

        // Inserting elements
        map.put("One", 1);
        map.put("Two", 2);
        map.put("Three", 3);

        // Iterating over elements
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

#### 3. TreeMap

`TreeMap` is a Red-Black tree-based implementation of the `Map` interface. It sorts the keys in natural order or by a specified comparator.

```java
import java.util.Map;
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        Map<String, Integer> map = new TreeMap<>();

        // Inserting elements
        map.put("One", 1);
        map.put("Two", 2);
        map.put("Three", 3);

        // Iterating over elements
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

#### 4. Hashtable

`Hashtable` is a synchronized implementation of the `Map` interface. It does not allow null keys or values.

```java
import java.util.Hashtable;
import java.util.Map;

public class HashtableExample {
    public static void main(String[] args) {
        Map<String, Integer> map = new Hashtable<>();

        // Inserting elements
        map.put("One", 1);
        map.put("Two", 2);
        map.put("Three", 3);

        // Iterating over elements
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

#### 5. ConcurrentHashMap

`ConcurrentHashMap` is a thread-safe implementation of the `Map` interface.

```java
import java.util.Map;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentHashMapExample {
    public static void main(String[] args) {
        Map<String, Integer> map = new ConcurrentHashMap<>();

        // Inserting elements
        map.put("One", 1);
        map.put("Two", 2);
        map.put("Three", 3);

        // Iterating over elements
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

Each of these implementations has its own characteristics and use cases, so you can choose the one that best fits your needs.
