# Advanced-6

* **HashMap**:
  * **Ordering of keys**: The ordering of the keys cannot be determined. `HashMap` does not maintain any order for the keys. The order can change when the map is resized or when items are added or removed.
* **TreeMap**:
  * **Ordering of keys**: Keys are ordered based on their natural ordering (if they implement `Comparable`) or by a specified comparator (if provided at the map's creation). `TreeMap` maintains keys in a sorted order, not by their insertion order.
* **LinkedHashMap**:
  * **Ordering of keys**: Keys are ordered based on their insertion order. If a key is re-inserted, its order is not affected unless the `LinkedHashMap` is constructed with access-order mode (which affects the order based on access frequency). `LinkedHashMap` maintains a doubly-linked list running through its entries, which defines the iteration ordering, either insertion-order or access-order.
