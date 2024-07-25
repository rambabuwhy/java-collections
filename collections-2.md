# Collections-2

#### 5. Stack

A `Stack` is a subclass of `Vector` that represents a last-in-first-out (LIFO) stack of objects.

**Example: Stack**

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();
        stack.push("Apple");
        stack.push("Banana");
        stack.push("Cherry");
        
        while (!stack.isEmpty()) {
            System.out.println(stack.pop());
        }
    }
}
```

#### 6. Deque

A `Deque` (double-ended queue) is a linear collection that supports element insertion and removal at both ends. Common implementations include `ArrayDeque` and `LinkedList`.

**Example: ArrayDeque**

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class DequeExample {
    public static void main(String[] args) {
        Deque<String> deque = new ArrayDeque<>();
        deque.addFirst("Apple");
        deque.addLast("Banana");
        deque.addFirst("Cherry");
        
        while (!deque.isEmpty()) {
            System.out.println(deque.removeFirst());
        }
    }
}
```

#### 7. LinkedList

`LinkedList` can be used as a List, Queue, or Deque.

**Example: LinkedList as a List**

```java
import java.util.LinkedList;
import java.util.List;

public class LinkedListExample {
    public static void main(String[] args) {
        List<String> list = new LinkedList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");
        
        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}
```

**Example: LinkedList as a Deque**

```java
import java.util.Deque;
import java.util.LinkedList;

public class LinkedListDequeExample {
    public static void main(String[] args) {
        Deque<String> deque = new LinkedList<>();
        deque.addFirst("Apple");
        deque.addLast("Banana");
        deque.addFirst("Cherry");
        
        while (!deque.isEmpty()) {
            System.out.println(deque.removeFirst());
        }
    }
}
```

#### 8. PriorityQueue

A `PriorityQueue` is an unbounded priority queue based on a priority heap.

**Example: PriorityQueue**

```java
import java.util.PriorityQueue;
import java.util.Queue;

public class PriorityQueueExample {
    public static void main(String[] args) {
        Queue<String> priorityQueue = new PriorityQueue<>();
        priorityQueue.add("Banana");
        priorityQueue.add("Apple");
        priorityQueue.add("Cherry");
        
        while (!priorityQueue.isEmpty()) {
            System.out.println(priorityQueue.poll());
        }
    }
}
```

#### 9. TreeMap

A `TreeMap` is a map that is sorted according to the natural ordering of its keys, or by a comparator provided at map creation time.

**Example: TreeMap**

```java
import java.util.Map;
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        Map<String, String> treeMap = new TreeMap<>();
        treeMap.put("Banana", "Yellow");
        treeMap.put("Apple", "Red");
        treeMap.put("Cherry", "Red");
        
        for (Map.Entry<String, String> entry : treeMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### 10. ConcurrentHashMap

A `ConcurrentHashMap` is a thread-safe variant of `HashMap` in which updates are made using modern lock-free techniques.

**Example: ConcurrentHashMap**

```java
import java.util.concurrent.ConcurrentHashMap;
import java.util.Map;

public class ConcurrentHashMapExample {
    public static void main(String[] args) {
        Map<String, String> concurrentMap = new ConcurrentHashMap<>();
        concurrentMap.put("Apple", "Red");
        concurrentMap.put("Banana", "Yellow");
        concurrentMap.put("Cherry", "Red");
        
        for (Map.Entry<String, String> entry : concurrentMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

#### Summary of Other Collections

* **Stack**: LIFO stack of objects. Example: `Stack`.
* **Deque**: Double-ended queue allowing insertion/removal at both ends. Examples: `ArrayDeque`, `LinkedList`.
* **LinkedList**: Can be used as a List, Queue, or Deque.
* **PriorityQueue**: Unbounded priority queue based on a priority heap.
* **TreeMap**: Sorted map based on natural ordering or comparator.
* **ConcurrentHashMap**: Thread-safe `HashMap` using lock-free techniques.
