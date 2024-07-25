# Advanced-4

## map vs hashmap

compare `Map` and `HashMap` in Java.

#### `Map<K, V> map = new HashMap<>()`

* **Interface vs Implementation:** This approach declares `map` as a variable of type `Map`, which is an interface. The actual object instantiated is of type `HashMap`, which is a concrete implementation of the `Map` interface.
*   **Flexibility:** Using the interface type (`Map`) makes your code more flexible. You can change the implementation later without changing the variable's type. For example, you can easily switch to a `TreeMap` or any other class that implements the `Map` interface.

    ```java
    javaCopy codeMap<String, Integer> map = new HashMap<>();
    map = new TreeMap<>(); // This is allowed
    ```
* **Best Practice:** It is generally considered a best practice to program to an interface rather than to a specific implementation. This makes the code more modular and easier to maintain.

#### `HashMap<K, V> map = new HashMap<>()`

* **Specific Implementation:** This approach declares `map` as a variable of type `HashMap`. The actual object instantiated is also of type `HashMap`.
*   **Less Flexible:** Using the specific implementation (`HashMap`) makes your code less flexible. If you decide to change the implementation to another type of map (e.g., `TreeMap`), you will need to change the variable's type as well.

    ```java
    javaCopy codeHashMap<String, Integer> map = new HashMap<>();
    map = new TreeMap<>(); // This will cause a compilation error
    ```
* **Direct Access to Implementation-Specific Methods:** If you need to use methods that are specific to `HashMap` and not available in the `Map` interface, you will need to declare the variable as `HashMap`. However, such situations are rare and usually indicate that the code is overly reliant on a specific implementation.

#### Conclusion

In general, prefer using `Map<K, V> map = new HashMap<>()` unless you have a specific reason to use methods that are unique to `HashMap`. This approach follows the best practice of programming to an interface, which enhances code flexibility and maintainability.

####
