# pkg-2

## Optional:

#### 1. Creating an `Optional`

```java
Optional<String> optionalValue = Optional.of("Hello");
System.out.println(optionalValue);
```

**Explanation**: `Optional.of("Hello")` creates an `Optional` containing the value "Hello".

**Output**:

```css
Optional[Hello]
```

#### 2. Handling `null` with `Optional.ofNullable()`

```java
Optional<String> optionalNullable = Optional.ofNullable(null);
System.out.println(optionalNullable);
```

**Explanation**: `Optional.ofNullable(null)` creates an empty `Optional` since the value is `null`.

**Output**:

```mathematica
Optional.empty
```

#### 3. Checking if a Value is Present with `isPresent()`

```java
Optional<String> optionalValue = Optional.of("Hello");
if (optionalValue.isPresent()) {
    System.out.println("Value is present: " + optionalValue.get());
} else {
    System.out.println("Value is absent");
}
```

**Explanation**: `isPresent()` checks if the `Optional` contains a value. If it does, `get()` retrieves the value.

**Output**:

```csharp
Value is present: Hello
```

#### 4. Providing a Default Value with `orElse()`

```java
Optional<String> optionalEmpty = Optional.empty();
String value = optionalEmpty.orElse("Default Value");
System.out.println(value);
```

**Explanation**: `orElse("Default Value")` returns the specified default value if the `Optional` is empty.

**Output**:

```mathematica
Default Value
```

#### 5. Using `orElseGet()` with a Supplier

```java
javaCopy codeOptional<String> optionalEmpty = Optional.empty();
String value = optionalEmpty.orElseGet(() -> "Generated Default Value");
System.out.println(value);
```

**Explanation**: `orElseGet()` takes a `Supplier` that generates a default value if the `Optional` is empty.

**Output**:

```mathematica
Generated Default Value
```

#### 6. Throwing an Exception with `orElseThrow()`

```java
Optional<String> optionalEmpty = Optional.empty();
try {
    String value = optionalEmpty.orElseThrow(() -> new IllegalStateException("No value present"));
    System.out.println(value);
} catch (Exception e) {
    System.out.println(e.getMessage());
}
```

**Explanation**: `orElseThrow()` throws a custom exception if the `Optional` is empty.

**Output**:

```yaml
No value present
```

#### 7. Transforming a Value with `map()`

```java
Optional<String> optionalValue = Optional.of("Hello");
Optional<Integer> length = optionalValue.map(String::length);
System.out.println(length);
```

**Explanation**: `map()` applies the provided function (`String::length`) to the value inside the `Optional` and returns a new `Optional` with the result.

**Output**:

```css
Optional[5]
```

#### 8. Flat Mapping with `flatMap()`

```java
Optional<String> optionalValue = Optional.of("Hello");
Optional<String> upperCaseValue = optionalValue.flatMap(s -> Optional.of(s.toUpperCase()));
System.out.println(upperCaseValue);
```

**Explanation**: `flatMap()` is similar to `map()`, but the mapping function itself returns an `Optional`. This is useful when you want to chain operations that may return `Optional` objects.

**Output**:

```css
Optional[HELLO]
```

#### 9. Filtering a Value with `filter()`

```java
Optional<String> optionalValue = Optional.of("Hello");
Optional<String> filteredValue = optionalValue.filter(s -> s.startsWith("H"));
System.out.println(filteredValue);
```

**Explanation**: `filter()` applies a predicate to the value inside the `Optional`. If the value matches the predicate, it remains in the `Optional`; otherwise, the `Optional` becomes empty.

**Output**:

```css
Optional[Hello]
```

#### 10. Handling Empty Optional with `ifPresentOrElse()`

```java
Optional<String> optionalEmpty = Optional.empty();
optionalEmpty.ifPresentOrElse(
    value -> System.out.println("Value: " + value),
    () -> System.out.println("No value present")
);
```

**Explanation**: `ifPresentOrElse()` takes two actions: one to perform if the value is present, and another if the `Optional` is empty.

**Output**:

```yaml
No value present
```
