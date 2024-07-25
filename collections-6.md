# collections-6

In Java, the Collections Framework provides a set of classes and interfaces for managing groups of objects. The main interfaces in the Collections Framework are `Collection`, `Set`, `List`, `Queue`, and `Map`. Here’s a breakdown of these groups and examples of classes that implement these interfaces:

#### 1. List

A `List` is an ordered collection that can contain duplicate elements. Lists allow positional access and insertion of elements.

*   **ArrayList**

    ```java
    import java.util.ArrayList;

    public class ArrayListExample {
        public static void main(String[] args) {
            ArrayList<String> list = new ArrayList<>();
            list.add("Apple");
            list.add("Banana");
            list.add("Cherry");
            System.out.println(list);
        }
    }
    ```
*   **LinkedList**

    ```java
    import java.util.LinkedList;

    public class LinkedListExample {
        public static void main(String[] args) {
            LinkedList<String> list = new LinkedList<>();
            list.add("Dog");
            list.add("Cat");
            list.add("Horse");
            System.out.println(list);
        }
    }
    ```

#### 2. Set

A `Set` is a collection that does not allow duplicate elements. It models the mathematical set abstraction.

*   **HashSet**

    ```java
    import java.util.HashSet;

    public class HashSetExample {
        public static void main(String[] args) {
            HashSet<String> set = new HashSet<>();
            set.add("Red");
            set.add("Green");
            set.add("Blue");
            System.out.println(set);
        }
    }
    ```
*   **TreeSet**

    ```java
    import java.util.TreeSet;

    public class TreeSetExample {
        public static void main(String[] args) {
            TreeSet<String> set = new TreeSet<>();
            set.add("One");
            set.add("Two");
            set.add("Three");
            System.out.println(set);
        }
    }
    ```

#### 3. Queue

A `Queue` is a collection used to hold multiple elements prior to processing. It is typically used for holding elements prior to processing and provides various operations such as insertion, removal, etc.

*   **PriorityQueue**

    ```java
    import java.util.PriorityQueue;

    public class PriorityQueueExample {
        public static void main(String[] args) {
            PriorityQueue<Integer> queue = new PriorityQueue<>();
            queue.add(10);
            queue.add(20);
            queue.add(15);
            System.out.println(queue);
        }
    }
    ```
*   **LinkedList** (implements `Queue`)

    ```java
    import java.util.LinkedList;
    import java.util.Queue;

    public class QueueExample {
        public static void main(String[] args) {
            Queue<String> queue = new LinkedList<>();
            queue.add("First");
            queue.add("Second");
            queue.add("Third");
            System.out.println(queue);
        }
    }
    ```

#### 4. Map

A `Map` is an object that maps keys to values. A map cannot contain duplicate keys, and each key can map to at most one value.

*   **HashMap**

    ```java
    import java.util.HashMap;

    public class HashMapExample {
        public static void main(String[] args) {
            HashMap<String, Integer> map = new HashMap<>();
            map.put("One", 1);
            map.put("Two", 2);
            map.put("Three", 3);
            System.out.println(map);
        }
    }
    ```
*   **TreeMap**

    ```java
    import java.util.TreeMap;

    public class TreeMapExample {
        public static void main(String[] args) {
            TreeMap<String, Integer> map = new TreeMap<>();
            map.put("A", 1);
            map.put("B", 2);
            map.put("C", 3);
            System.out.println(map);
        }
    }
    ```

#### Summary

* **List**: `ArrayList`, `LinkedList`
* **Set**: `HashSet`, `TreeSet`
* **Queue**: `PriorityQueue`, `LinkedList`
* **Map**: `HashMap`, `TreeMap`
