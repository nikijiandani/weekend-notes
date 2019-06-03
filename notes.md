# Weekend notes

## JavaScript style guide

### Types

 Primitives: When you access a primitive type you work directly on its value.

 Complex: When you access a complex type you work on a reference to its value.

### References

Use const for all of your references; avoid using var.
Why? This ensures that you can’t reassign your references, which can lead to bugs and difficult to comprehend code.

If you must reassign references, use let instead of var.
Why? let is block-scoped rather than function-scoped like var.

Note that both let and const are block-scoped.

### Objects

Use the literal syntax for object creation.

Use computed property names when creating objects with dynamic property names.

Use computed property names when creating objects with dynamic property names.

Use object method shorthand.

Use property value shorthand.

Group your shorthand properties at the beginning of your object declaration.
Why? It’s easier to tell which properties are using the shorthand.

Only quote properties that are invalid identifiers.
Why? In general we consider it subjectively easier to read. It improves syntax highlighting, and is also more easily optimized by many JS engines.

Do not call Object.prototype methods directly, such as hasOwnProperty, propertyIsEnumerable, and isPrototypeOf.

Prefer the object spread operator over Object.assign to shallow-copy objects. Use the object rest operator to get a new object with certain properties omitted.

### Arrays

Use the literal syntax for array creation.

Use Array#push instead of direct assignment to add items to an array.

Use array spreads ... to copy arrays.

To convert an iterable object to an array, use spreads ... instead of Array.from.

Use Array.from for converting an array-like object to an array.

Use Array.from instead of spread ... for mapping over iterables, because it avoids creating an intermediate array.

Use return statements in array method callbacks. It’s ok to omit the return if the function body consists of a single statement returning an expression without side effects.

Use line breaks after open and before close array brackets if an array has multiple lines.

### Destructuring

Use object destructuring when accessing and using multiple properties of an object.
Why? Destructuring saves you from creating temporary references for those properties.

Use array destructuring.

Use object destructuring for multiple return values, not array destructuring.

