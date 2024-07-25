# Collections-3

#### 11. EnumSet

An `EnumSet` is a specialized `Set` implementation for use with enum types. All of the elements in an enum set must come from a single enum type.

**Example: EnumSet**

```java
import java.util.EnumSet;

public class EnumSetExample {
    enum Fruit {
        APPLE, BANANA, CHERRY
    }

    public static void main(String[] args) {
        EnumSet<Fruit> enumSet = EnumSet.of(Fruit.APPLE, Fruit.BANANA);

        for (Fruit fruit : enumSet) {
            System.out.println(fruit);
        }
    }
}
```

#### 12. LinkedHashMap

A `LinkedHashMap` is an implementation of `Map` that maintains the order of insertion.

**Example: LinkedHashMap**

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class LinkedHashMapExample {
    public static void main(String[] args) {
        Map<String, String> linkedHashMap = new LinkedHashMap<>();
        linkedHashMap.put("Apple", "Red");
        linkedHashMap.put("Banana", "Yellow");
        linkedHashMap.put("Cherry", "Red");
        
        for (Map.Entry<String, String> entry : linkedHashMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### 13. LinkedHashSet

A `LinkedHashSet` is an implementation of the `Set` interface that uses a hash table and linked list to maintain insertion order.

**Example: LinkedHashSet**

```java
import java.util.LinkedHashSet;
import java.util.Set;

public class LinkedHashSetExample {
    public static void main(String[] args) {
        Set<String> linkedHashSet = new LinkedHashSet<>();
        linkedHashSet.add("Apple");
        linkedHashSet.add("Banana");
        linkedHashSet.add("Cherry");
        linkedHashSet.add("Apple"); // Duplicate element, won't be added
        
        for (String fruit : linkedHashSet) {
            System.out.println(fruit);
        }
    }
}
```

#### 14. CopyOnWriteArrayList

A `CopyOnWriteArrayList` is a thread-safe variant of `ArrayList` in which all mutative operations (add, set, and so on) are implemented by making a fresh copy of the underlying array.

**Example: CopyOnWriteArrayList**

```java
import java.util.List;
import java.util.concurrent.CopyOnWriteArrayList;

public class CopyOnWriteArrayListExample {
    public static void main(String[] args) {
        List<String> list = new CopyOnWriteArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");
        
        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}
```

#### 15. CopyOnWriteArraySet

A `CopyOnWriteArraySet` is a thread-safe variant of `Set` backed by a `CopyOnWriteArrayList`. It’s useful in situations where set traversal operations vastly outnumber set mutation operations.

**Example: CopyOnWriteArraySet**

```java
import java.util.Set;
import java.util.concurrent.CopyOnWriteArraySet;

public class CopyOnWriteArraySetExample {
    public static void main(String[] args) {
        Set<String> set = new CopyOnWriteArraySet<>();
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

#### 16. ConcurrentLinkedQueue

A `ConcurrentLinkedQueue` is an unbounded thread-safe queue based on linked nodes. This queue orders elements FIFO (first-in-first-out).

**Example: ConcurrentLinkedQueue**

```java
import java.util.Queue;
import java.util.concurrent.ConcurrentLinkedQueue;

public class ConcurrentLinkedQueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new ConcurrentLinkedQueue<>();
        queue.add("Apple");
        queue.add("Banana");
        queue.add("Cherry");
        
        while (!queue.isEmpty()) {
            System.out.println(queue.poll());
        }
    }
}
```

#### 17. TreeSet

A `TreeSet` is a NavigableSet implementation based on a TreeMap. The elements in a TreeSet are sorted according to their natural ordering, or by a Comparator provided at set creation time.

**Example: TreeSet**

```java
import java.util.Set;
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        Set<String> treeSet = new TreeSet<>();
        treeSet.add("Banana");
        treeSet.add("Apple");
        treeSet.add("Cherry");
        
        for (String fruit : treeSet) {
            System.out.println(fruit);
        }
    }
}
```

#### 18. Collections Utility Class

The `Collections` class consists exclusively of static methods that operate on or return collections. It contains polymorphic algorithms that operate on collections, "wrappers", which return a new collection backed by a specified collection, and a few other odds and ends.

**Example: Collections Utility Class**

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class CollectionsExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Banana");
        list.add("Apple");
        list.add("Cherry");

        // Sorting the list
        Collections.sort(list);
        System.out.println("Sorted List: " + list);

        // Reversing the list
        Collections.reverse(list);
        System.out.println("Reversed List: " + list);

        // Shuffling the list
        Collections.shuffle(list);
        System.out.println("Shuffled List: " + list);
    }
}
```

#### Summary of More Collections

* **EnumSet**: Specialized `Set` for use with enum types.
* **LinkedHashMap**: `Map` implementation maintaining insertion order.
* **LinkedHashSet**: `Set` implementation maintaining insertion order.
* **CopyOnWriteArrayList**: Thread-safe variant of `ArrayList`.
* **CopyOnWriteArraySet**: Thread-safe variant of `Set`.
* **ConcurrentLinkedQueue**: Thread-safe, unbounded FIFO queue.
* **TreeSet**: Sorted set based on `TreeMap`.
* **Collections**: Utility class with static methods for collections.
