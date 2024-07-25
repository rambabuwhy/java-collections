# Collections-4

#### 19. NavigableMap

A `NavigableMap` is a `SortedMap` with navigation methods returning the closest matches for given search targets. Common implementations include `TreeMap`.

**Example: NavigableMap (TreeMap)**

```java
import java.util.NavigableMap;
import java.util.TreeMap;

public class NavigableMapExample {
    public static void main(String[] args) {
        NavigableMap<String, String> navigableMap = new TreeMap<>();
        navigableMap.put("Banana", "Yellow");
        navigableMap.put("Apple", "Red");
        navigableMap.put("Cherry", "Red");

        // Get a key-value mapping associated with the least key greater than or equal to the given key.
        System.out.println("Ceiling entry: " + navigableMap.ceilingEntry("B"));

        // Get a key-value mapping associated with the greatest key less than or equal to the given key.
        System.out.println("Floor entry: " + navigableMap.floorEntry("B"));

        // Get a reverse order view of the mappings contained in this map.
        System.out.println("Descending map: " + navigableMap.descendingMap());
    }
}
```

#### 20. NavigableSet

A `NavigableSet` is a `SortedSet` with navigation methods reporting closest matches for given search targets. Common implementations include `TreeSet`.

**Example: NavigableSet (TreeSet)**

```java
import java.util.NavigableSet;
import java.util.TreeSet;

public class NavigableSetExample {
    public static void main(String[] args) {
        NavigableSet<String> navigableSet = new TreeSet<>();
        navigableSet.add("Banana");
        navigableSet.add("Apple");
        navigableSet.add("Cherry");

        // Get the least element in this set greater than or equal to the given element.
        System.out.println("Ceiling: " + navigableSet.ceiling("B"));

        // Get the greatest element in this set less than or equal to the given element.
        System.out.println("Floor: " + navigableSet.floor("B"));

        // Get a reverse order view of the elements contained in this set.
        System.out.println("Descending set: " + navigableSet.descendingSet());
    }
}
```

#### 21. BitSet

A `BitSet` is a special type of array that holds bits (true or false).

**Example: BitSet**

```java
import java.util.BitSet;

public class BitSetExample {
    public static void main(String[] args) {
        BitSet bitSet = new BitSet();
        bitSet.set(0);
        bitSet.set(2);
        bitSet.set(4);

        // Print all set bits
        System.out.println("BitSet: " + bitSet);

        // Get the number of set bits
        System.out.println("Cardinality: " + bitSet.cardinality());

        // Perform logical AND with another BitSet
        BitSet anotherBitSet = new BitSet();
        anotherBitSet.set(2);
        anotherBitSet.set(3);
        bitSet.and(anotherBitSet);
        System.out.println("BitSet after AND: " + bitSet);
    }
}
```

#### 22. WeakHashMap

A `WeakHashMap` is a `HashMap` implementation with weak keys, allowing keys to be garbage-collected.

**Example: WeakHashMap**

```java
import java.util.Map;
import java.util.WeakHashMap;

public class WeakHashMapExample {
    public static void main(String[] args) {
        Map<String, String> weakHashMap = new WeakHashMap<>();
        String key1 = new String("Apple");
        String key2 = new String("Banana");

        weakHashMap.put(key1, "Red");
        weakHashMap.put(key2, "Yellow");

        System.out.println("WeakHashMap before GC: " + weakHashMap);

        // Remove the strong references
        key1 = null;
        key2 = null;

        // Invoke garbage collection
        System.gc();

        // Give some time for garbage collection
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("WeakHashMap after GC: " + weakHashMap);
    }
}
```

#### 23. IdentityHashMap

An `IdentityHashMap` is a `Map` implementation using reference equality (==) instead of object equality (equals).

**Example: IdentityHashMap**

```java
import java.util.IdentityHashMap;
import java.util.Map;

public class IdentityHashMapExample {
    public static void main(String[] args) {
        Map<String, String> identityHashMap = new IdentityHashMap<>();
        identityHashMap.put(new String("Apple"), "Red");
        identityHashMap.put(new String("Apple"), "Green");

        // The map size will be 2 because the keys are different objects
        System.out.println("IdentityHashMap size: " + identityHashMap.size());

        for (Map.Entry<String, String> entry : identityHashMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### 24. Properties

A `Properties` object is a persistent set of properties. The `Properties` class is often used for configuration settings.

**Example: Properties**

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Properties;

public class PropertiesExample {
    public static void main(String[] args) {
        Properties properties = new Properties();
        properties.setProperty("username", "admin");
        properties.setProperty("password", "12345");

        try (FileOutputStream output = new FileOutputStream("config.properties")) {
            properties.store(output, "User Configurations");
        } catch (IOException e) {
            e.printStackTrace();
        }
        
        // Load properties from file
        try (FileInputStream input = new FileInputStream("config.properties")) {
            Properties loadedProperties = new Properties();
            loadedProperties.load(input);
            System.out.println("Loaded Properties: " + loadedProperties);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 25. EnumMap

An `EnumMap` is a specialized `Map` implementation for use with enum type keys.

**Example: EnumMap**

```java
import java.util.EnumMap;
import java.util.Map;

public class EnumMapExample {
    enum Fruit {
        APPLE, BANANA, CHERRY
    }

    public static void main(String[] args) {
        Map<Fruit, String> enumMap = new EnumMap<>(Fruit.class);
        enumMap.put(Fruit.APPLE, "Red");
        enumMap.put(Fruit.BANANA, "Yellow");
        enumMap.put(Fruit.CHERRY, "Red");

        for (Map.Entry<Fruit, String> entry : enumMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### 26. PriorityBlockingQueue

A `PriorityBlockingQueue` is a thread-safe priority queue backed by a priority heap.

**Example: PriorityBlockingQueue**

```java
import java.util.concurrent.PriorityBlockingQueue;

public class PriorityBlockingQueueExample {
    public static void main(String[] args) throws InterruptedException {
        PriorityBlockingQueue<String> priorityBlockingQueue = new PriorityBlockingQueue<>();
        priorityBlockingQueue.put("Banana");
        priorityBlockingQueue.put("Apple");
        priorityBlockingQueue.put("Cherry");

        while (!priorityBlockingQueue.isEmpty()) {
            System.out.println(priorityBlockingQueue.take());
        }
    }
}
```

#### Summary of Additional Collections

* **NavigableMap**: A `SortedMap` with navigation methods for closest matches.
* **NavigableSet**: A `SortedSet` with navigation methods for closest matches.
* **BitSet**: An array of bits (true or false).
* **WeakHashMap**: A `HashMap` with weak keys.
* **IdentityHashMap**: A `Map` using reference equality.
* **Properties**: A persistent set of properties for configuration.
* **EnumMap**: A `Map` implementation for enum keys.
* **PriorityBlockingQueue**: A thread-safe priority queue.
