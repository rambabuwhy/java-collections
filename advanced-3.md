# Advanced-3

`HashSet` and `TreeSet` are two different implementations of the `Set` interface in Java, each with its own characteristics and use cases. Here's a detailed comparison:

#### `HashSet`

* **Underlying Data Structure:** `HashSet` is backed by a hash table (actually a `HashMap` instance).
* **Order:** It does not guarantee any order of the elements. The order can change over time, even if no modifications are made to the set.
* **Performance:** It provides constant time performance (`O(1)`) for basic operations like add, remove, contains, and size, assuming the hash function disperses the elements properly among the buckets.
* **Null Values:** It allows the null element.
* **Use Case:** Use `HashSet` when you need a fast, unordered collection of unique elements.

#### `TreeSet`

* **Underlying Data Structure:** `TreeSet` is backed by a `TreeMap` (Red-Black tree).
* **Order:** It stores elements in a sorted order according to their natural ordering or by a specified comparator. Thus, it provides a sorted iteration order.
* **Performance:** It provides guaranteed log(n) time cost for the basic operations (add, remove, contains). This is because it is based on a balanced tree structure.
* **Null Values:** It does not allow the null element (throws `NullPointerException` if you try to add null).
* **Use Case:** Use `TreeSet` when you need a sorted collection of unique elements.

#### Summary of Differences

| Feature         | `HashSet`                       | `TreeSet`                      |
| --------------- | ------------------------------- | ------------------------------ |
| Underlying Data | Hash table                      | Red-Black tree                 |
| Order           | Unordered                       | Sorted (natural or comparator) |
| Performance     | O(1) for basic operations       | O(log n) for basic operations  |
| Null Values     | Allows null                     | Does not allow null            |
| Use Case        | Fast, unordered unique elements | Sorted unique elements         |

#### Examples

**`HashSet`**

```java
Set<String> hashSet = new HashSet<>();
hashSet.add("Banana");
hashSet.add("Apple");
hashSet.add("Mango");

for (String fruit : hashSet) {
    System.out.println(fruit);
}
```

Output order can vary, for example:

```
Mango
Apple
Banana
```

**`TreeSet`**

```java
Set<String> treeSet = new TreeSet<>();
treeSet.add("Banana");
treeSet.add("Apple");
treeSet.add("Mango");

for (String fruit : treeSet) {
    System.out.println(fruit);
}
```

Output will be sorted:

```
Apple
Banana
Mango
```

#### Conclusion

Choose `HashSet` for fast operations and no need for ordering. Choose `TreeSet` when you need to maintain elements in a sorted order.
