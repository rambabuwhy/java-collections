# pkg-1

## Optional:

In Java, the `Optional` class is a container object that may or may not contain a non-null value. It was introduced in Java 8 as a part of the `java.util` package to address the issue of null references and to avoid `NullPointerException`, which is a common problem in Java programming.

#### Key Concepts of `Optional`:

1. **Presence and Absence of Value**:
   * An `Optional` can contain a value (non-null), or it can be empty (no value, effectively representing `null` but without using `null` directly).
2.  **Creating an Optional**:

    * `Optional.of(value)`: Creates an `Optional` with the specified non-null value.
    * `Optional.ofNullable(value)`: Creates an `Optional` that can hold a value or be empty if the value is `null`.
    * `Optional.empty()`: Creates an empty `Optional` instance.

    ```java
    Optional<String> optionalValue = Optional.of("Hello");
    Optional<String> optionalNullable = Optional.ofNullable(null);
    Optional<String> emptyOptional = Optional.empty();
    ```
3.  **Checking for a Value**:

    * `isPresent()`: Returns `true` if the `Optional` contains a value, otherwise `false`.
    * `isEmpty()`: Returns `true` if the `Optional` is empty (Java 11+).

    ```java
    if (optionalValue.isPresent()) {
        System.out.println(optionalValue.get());
    }
    ```
4.  **Retrieving the Value**:

    * `get()`: Returns the value if present; otherwise, throws `NoSuchElementException`. It's safer to check if the value is present before calling this method.
    * `orElse(T other)`: Returns the value if present; otherwise, returns the provided default value.
    * `orElseGet(Supplier<? extends T> other)`: Returns the value if present; otherwise, returns the result produced by the supplying function.
    * `orElseThrow()`: Returns the value if present; otherwise, throws `NoSuchElementException`.
    * `orElseThrow(Supplier<? extends X> exceptionSupplier)`: Returns the value if present; otherwise, throws an exception provided by the supplier.

    ```java
    javaCopy codeString value = optionalNullable.orElse("Default Value");
    ```
5.  **Transforming the Value**:

    * `map(Function<? super T,? extends U> mapper)`: If a value is present, applies the provided mapping function to it and returns an `Optional` describing the result.
    * `flatMap(Function<? super T,Optional<U>> mapper)`: Similar to `map`, but the mapping function must return an `Optional`.
    * `filter(Predicate<? super T> predicate)`: If a value is present, and it matches the given predicate, returns an `Optional` describing the value, otherwise returns an empty `Optional`.

    ```java
    javaCopy codeOptional<Integer> stringLength = optionalValue.map(String::length);
    ```
6. **Why Use `Optional`?**
   * **Avoiding `null` checks**: `Optional` helps reduce the number of `null` checks, making the code more readable and reducing the likelihood of `NullPointerException`.
   * **Clearer intent**: By using `Optional`, you make it explicit that a variable or return type might not hold a value, which helps in better understanding and maintaining the code.
   * **Functional operations**: `Optional` supports a variety of operations that are in line with the functional programming style, making it easier to handle potential absence of values in a more declarative manner.

#### Example:

```java
public Optional<String> findNameById(int id) {
    if (id == 1) {
        return Optional.of("John Doe");
    } else {
        return Optional.empty();
    }
}

public void greetUser(int id) {
    String greeting = findNameById(id)
                          .map(name -> "Hello, " + name + "!")
                          .orElse("Hello, Stranger!");
    System.out.println(greeting);
}
```

In this example, `findNameById` returns an `Optional` that may or may not contain a name. `greetUser` then uses this `Optional` to create a greeting, with a default message for the case when no name is found. This approach avoids `null` and makes the intent clear.
