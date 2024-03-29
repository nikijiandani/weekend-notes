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

### Strings

Use single quotes '' for strings.

Strings that cause the line to go over 100 characters should not be written across multiple lines using string concatenation.
Why? Broken strings are painful to work with and make code less searchable.

When programmatically building up strings, use template strings instead of concatenation.

Never use eval() on a string, it opens too many vulnerabilities.

Do not unnecessarily escape characters in strings.

### Functions

Use named function expressions instead of function declarations.

Wrap immediately invoked function expressions in parentheses.

Never declare a function in a non-function block (if, while, etc). Assign the function to a variable instead. Browsers will allow you to do it, but they all interpret it differently, which is bad news bears.

Note: ECMA-262 defines a block as a list of statements. A function declaration is not a statement.

Never name a parameter arguments. This will take precedence over the arguments object that is given to every function scope.

Never use arguments, opt to use rest syntax ... instead. 
Why? ... is explicit about which arguments you want pulled. Plus, rest arguments are a real Array, and not merely Array-like like arguments.

Use default parameter syntax rather than mutating function arguments.

Avoid side effects with default parameters.

Always put default parameters last.

Never use the Function constructor to create a new function.

Spacing in a function signature.
Why? Consistency is good, and you shouldn’t have to add or remove a space when adding or removing a name.

Never mutate parameters.
Why? Manipulating objects passed in as parameters can cause unwanted variable side effects in the original caller.

Never reassign parameters.
Why? Reassigning parameters can lead to unexpected behavior, especially when accessing the arguments object. It can also cause optimization issues, especially in V8.

Prefer the use of the spread operator ... to call variadic functions.

Functions with multiline signatures, or invocations, should be indented just like every other multiline list in this guide: with each item on a line by itself, with a trailing comma on the last item.

