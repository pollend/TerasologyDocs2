Over the course of its life, every project develops it's own code conventions, and Terasology is no different. Note that we try and stick to the standard Java conventions as much as possible.

### Identation
We follow the [1TBS](https://en.wikipedia.org/wiki/Indentation_style#Variant:_1TBS_.28OTBS.29) (One true brace style) exclusively. Also, every text file (be it code, or text-asset like json) should end with an empty line.

For all code files, we follow a 4-space identation style, and firmly believe in the saying "death to all tabs".
```
void someFunction() {
    doSomething();
    doSomethingElse();
}
```

However, for asset files (like json, that is used for all prefab and config files) we follow a 2-space indentation style.
```
container: {
  property1: "someValue",
  property2: "someOtherValue"
}
```

Note that even for single line `if` and `while` statements, we use brackets.
```
// Bad
if (something)
    // Do something

// Good
if (something) {
    // Do something
}
```

### Naming Conventions
Almost everything uses either camelCase, or PascalCase (same as camelCase, but with the first letter capitalized).

| Type | Style to follow |
| --- | --- |
| Package name | camelCase |
| Class or interface name | PascalCase |
| Functions and attributes | camelCase |
| Constants | ALL_CAPITAL |

For more information, refer to the [official Oracle docs](http://www.oracle.com/technetwork/java/codeconventions-135099.html).
```
package test;

class TestClass {
    private static final int SOME_CONSTANT = 0;

    int someInt;

    void doSomething() {
    }
}
```

### Some random examples
Control flow keywords (if, while, for) and other similar constructs are followed by a space, and the actual conditional statement is not padded by any space inside the parentheses.
```
if (x == 5) {
    // Something
}

for (int i = 0; i < 10; i++) {
    // Something
}

while ((x > 10 && x >= 20) || (y == 8 || z == 16)) {
}
```

Conditional operator `?:` is also padded liberally with spaces.
```
int x = y == 10 ? 20 : 30;
```

A few extra parentheses to make things clear are always appreciated, but don't overdo them!
```
// Good
int x = (y == 10) ? 20 : 30;

// Bad
int x = ((y == (10)) ? (20) : (30));
```

### Gray areas
TODO: Empty function blocks
TODO: Indentation in multi-line function calls

### Others
- Use // TODO comments to note where something needs to be done
- Don't use Hungarian notation to denote types
- Use interfaces over concrete classes for variables (e.g. Map instead of HashMap). Feel free to use guava to construct the actual instance (e.g. Maps.newHashMap())
- Use complete imports, instead of * imports
- Never have any `if` or `while` constructs without brackets, even if they only contain a single statement.

### Checkstyle
Terasology uses Checkstyle to ensure that the styling is correct. For more information, refer to the [Checkstyle wiki page](https://github.com/MovingBlocks/Terasology/wiki/Checkstyle).