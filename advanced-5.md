# Advanced-5

## HashMap vs TreeMap

Now, let's compare `HashMap` and `TreeMap`.

#### `HashMap`

* **Underlying Data Structure:** `HashMap` is backed by a hash table.
* **Order:** It does not guarantee any order of the entries. The order can change over time.
* **Performance:** It provides constant time performance (`O(1)`) for basic operations like `put`, `get`, `remove`, and `containsKey`, assuming the hash function disperses the elements properly among the buckets.
* **Null Values:** It allows one null key and multiple null values.
* **Use Case:** Use `HashMap` when you need a fast, unordered collection of key-value pairs.

#### `TreeMap`

* **Underlying Data Structure:** `TreeMap` is backed by a `TreeMap` (Red-Black tree).
* **Order:** It stores entries in a sorted order according to the natural ordering of its keys or by a specified comparator. Thus, it provides a sorted iteration order.
* **Performance:** It provides guaranteed log(n) time cost for the basic operations (`put`, `get`, `remove`, `containsKey`). This is because it is based on a balanced tree structure.
* **Null Values:** It does not allow null keys but allows multiple null values.
* **Use Case:** Use `TreeMap` when you need a sorted collection of key-value pairs.

#### Summary of Differences

| Feature         | `HashMap`                           | `TreeMap`                                        |
| --------------- | ----------------------------------- | ------------------------------------------------ |
| Underlying Data | Hash table                          | Red-Black tree                                   |
| Order           | Unordered                           | Sorted (natural or comparator)                   |
| Performance     | O(1) for basic operations           | O(log n) for basic operations                    |
| Null Values     | Allows one null key and null values | Does not allow null keys, but allows null values |
| Use Case        | Fast, unordered key-value pairs     | Sorted key-value pairs                           |

#### Examples

**`HashMap`**

```java
Map<String, Integer> hashMap = new HashMap<>();
hashMap.put("Banana", 1);
hashMap.put("Apple", 2);
hashMap.put("Mango", 3);

for (Map.Entry<String, Integer> entry : hashMap.entrySet()) {
    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

Output order can vary, for example:

```yaml
yamlCopy codeApple : 2
Mango : 3
Banana : 1
```

**`TreeMap`**

```java
Map<String, Integer> treeMap = new TreeMap<>();
treeMap.put("Banana", 1);
treeMap.put("Apple", 2);
treeMap.put("Mango", 3);

for (Map.Entry<String, Integer> entry : treeMap.entrySet()) {
    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

Output will be sorted by keys:

```yaml
Apple : 2
Banana : 1
Mango : 3
```

#### Conclusion

Choose `HashMap` for fast operations and no need for ordering. Choose `TreeMap` when you need to maintain entries in a sorted order by keys.
