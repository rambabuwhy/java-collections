# Collections-5

## ArrayList

An `ArrayList` is a resizable array implementation of the `List` interface. It is part of the Java Collections Framework and provides a way to store elements in a dynamically resizable array. `ArrayList` allows duplicate elements and maintains the order of insertion.

**Key Features:**

* **Resizable**: Automatically grows as more elements are added.
* **Indexed Access**: Provides fast random access to elements using an index.
* **Not synchronized**: Not thread-safe unless explicitly synchronized.

**Example: ArrayList**

```java
import java.util.ArrayList;
import java.util.List;

public class ArrayListExample {
    public static void main(String[] args) {
        List<String> arrayList = new ArrayList<>();
        arrayList.add("Apple");
        arrayList.add("Banana");
        arrayList.add("Cherry");
        
        // Print all elements
        for (String fruit : arrayList) {
            System.out.println(fruit);
        }

        // Access an element by index
        System.out.println("Element at index 1: " + arrayList.get(1));

        // Remove an element by index
        arrayList.remove(1); // Removes "Banana"
        System.out.println("ArrayList after removal: " + arrayList);

        // Check if the list contains an element
        System.out.println("Contains Cherry: " + arrayList.contains("Cherry"));
        
        // Get the size of the list
        System.out.println("Size of ArrayList: " + arrayList.size());
        
        // Clear all elements
        arrayList.clear();
        System.out.println("ArrayList after clear: " + arrayList);
    }
}
```

#### Summary of ArrayList

* **Resizable**: Automatically adjusts size.
* **Indexed Access**: Fast access to elements via index.
* **Allows Duplicates**: Stores duplicate elements.
* **Order Maintained**: Preserves the order of insertion.
* **Not Synchronized**: Not thread-safe by default.

`ArrayList` is a core part of the Java Collections Framework and is frequently used for its efficient and flexible array-like behavior.
