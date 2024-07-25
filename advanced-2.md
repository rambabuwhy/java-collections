# Advanced-2

## list vs hashset

`List` and `ArrayList`, there are important differences between declaring a `Set` and a `HashSet` in Java:

#### `Set<String> set = new HashSet<>()`

* **Interface vs Implementation:** This approach declares `set` as a variable of type `Set`, which is an interface. The actual object instantiated is of type `HashSet`, which is a concrete implementation of the `Set` interface.
*   **Flexibility:** Using the interface type (`Set`) makes your code more flexible. You can change the implementation later without changing the variable's type. For example, you can easily switch to a `TreeSet` or any other class that implements the `Set` interface.

    ```java
    javaCopy codeSet<String> set = new HashSet<>();
    set = new TreeSet<>(); // This is allowed
    ```
* **Best Practice:** It is generally considered a best practice to program to an interface rather than to a specific implementation. This makes the code more modular and easier to maintain.

#### `HashSet<String> set = new HashSet<>()`

* **Specific Implementation:** This approach declares `set` as a variable of type `HashSet`. The actual object instantiated is also of type `HashSet`.
*   **Less Flexible:** Using the specific implementation (`HashSet`) makes your code less flexible. If you decide to change the implementation to another type of set (e.g., `TreeSet`), you will need to change the variable's type as well.

    ```java
    javaCopy codeHashSet<String> set = new HashSet<>();
    set = new TreeSet<>(); // This will cause a compilation error
    ```
* **Direct Access to Implementation-Specific Methods:** If you need to use methods that are specific to `HashSet` and not available in the `Set` interface, you will need to declare the variable as `HashSet`. However, such situations are rare and usually indicate that the code is overly reliant on a specific implementation.

#### Conclusion

In general, prefer using `Set<String> set = new HashSet<>()` unless you have a specific reason to use methods that are unique to `HashSet`. This approach follows the best practice of programming to an interface, which enhances code flexibility and maintainability.
