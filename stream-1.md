# stream-1

## Optional:

In Java, the `Optional` class is a container object which may or may not contain a non-null value. It is used to represent the presence or absence of a value, thus helping to avoid `NullPointerException`. Here’s an overview of how you can use `Optional` in Java:

#### Creating an Optional

1.  **Empty Optional**: Represents no value.

    ```java
    Optional<String> emptyOptional = Optional.empty();
    ```
2.  **Optional with a Non-Null Value**:

    ```java
    Optional<String> nonEmptyOptional = Optional.of("Hello");
    ```
3.  **Optional with a Nullable Value**: Allows for null values.

    ```java
    Optional<String> nullableOptional = Optional.ofNullable(null);
    ```

#### Checking Presence of a Value

1.  **isPresent()**: Checks if there is a value present.

    ```java
    if (nonEmptyOptional.isPresent()) {
        System.out.println("Value is present");
    }
    ```
2.  **ifPresent()**: Performs an action if the value is present.

    ```java
    nonEmptyOptional.ifPresent(value -> System.out.println("Value: " + value));
    ```

#### Getting the Value

1.  **get()**: Returns the value if present, otherwise throws `NoSuchElementException`.

    ```java
    javaCopy codeString value = nonEmptyOptional.get();
    ```
2.  **orElse()**: Returns the value if present, otherwise returns the provided default value.

    ```java
    javaCopy codeString value = nullableOptional.orElse("Default Value");
    ```
3.  **orElseGet()**: Returns the value if present, otherwise returns the result produced by the provided `Supplier`.

    ```java
    javaCopy codeString value = nullableOptional.orElseGet(() -> "Generated Default Value");
    ```
4.  **orElseThrow()**: Returns the value if present, otherwise throws the provided exception.

    ```java
    javaCopy codeString value = nullableOptional.orElseThrow(() -> new IllegalArgumentException("Value not present"));
    ```

#### Filtering and Transforming the Value

1.  **filter()**: Applies a predicate to the value if present, returning an `Optional` describing the value if the predicate matches.

    ```java
    Optional<String> filteredOptional = nonEmptyOptional.filter(value -> value.startsWith("H"));
    ```
2.  **map()**: Transforms the value if present, applying the provided function and returning an `Optional` describing the result.

    ```java
    Optional<Integer> lengthOptional = nonEmptyOptional.map(String::length);
    ```
3.  **flatMap()**: Similar to `map()`, but the function returns an `Optional` directly.

    ```java
    Optional<Integer> lengthOptional = nonEmptyOptional.flatMap(value -> Optional.of(value.length()));
    ```

#### Example Usage

Here is a complete example demonstrating some common usages of `Optional`:

```java
import java.util.Optional;

public class OptionalExample {
    public static void main(String[] args) {
        Optional<String> optional = Optional.ofNullable(getValue());

        // Using isPresent() and get()
        if (optional.isPresent()) {
            System.out.println("Value: " + optional.get());
        } else {
            System.out.println("No value present");
        }

        // Using orElse()
        String defaultValue = optional.orElse("Default Value");
        System.out.println("Value or default: " + defaultValue);

        // Using ifPresent()
        optional.ifPresent(value -> System.out.println("Value is present: " + value));

        // Using map()
        Optional<Integer> lengthOptional = optional.map(String::length);
        lengthOptional.ifPresent(length -> System.out.println("Length of the value: " + length));

        // Using orElseThrow()
        try {
            String value = optional.orElseThrow(() -> new IllegalArgumentException("No value present"));
            System.out.println("Value: " + value);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }

    private static String getValue() {
        return "Hello, World!";
    }
}
```

In this example, `Optional` is used to handle the possibility of a null value in a clean and expressive way, avoiding the need for explicit null checks and reducing the risk of `NullPointerException`.
