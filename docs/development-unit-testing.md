How and why we unit test code.

## FAQ

### Why Test?

Most developers spend the majority of their time not *writing* code, but debugging and maintaining it. Unit tests are one of the best ways to minimize unnecessary time spent on both. Testing also helps document your code. Finally, we use a passing unit test suite as one of the criteria for accepting pull requests.

### What software is used to test?

Terasology uses [JUnit 4](http://www.junit.org/) for its automated test suite. It also uses [Mockito](http://site.mockito.org) for mocking/stubbing in special situations for which a dependency is too expensive or unreliable to bring into a test suite - for example, network activity or OpenGL.

An IDE is highly encouraged for running tests, as most support JUnit. In Eclipse, for example, you can quickly run a single test by right-clicking on the test method declaration and selecting *Run As → JUnit Test*. You can give this command a shortcut key of your choice to make it even faster.

### How often should I use Mocks or Stubs?

Rarely. If you find yourself using Mockito a lot, you may want to consider refactoring your code to be more modular.

### What should I test?

Ideally, every line of code that you want to merge should be backed by a unit test. However, there are exceptions, such as  straightforward getters/setters. The general rule is that the more likely your code is to fail or change, the more important it is to have test coverage.

### When should I run the full test suite?

On pulling any changes and before making any pull requests. To save yourself any unpleasant surprises, you should also run the complete test suite after completing any unit of work on the code.

### How should I test?

Ideally, you should [write your tests first](http://en.wikipedia.org/wiki/Test-driven_development). Begin by thinking about what success looks like for the problem you're trying to solve. Then attempt to write a test in code that captures the solution. Then write the code to make the test pass.

### What's up with the nested tests?

JUnit supports nested test classes. Our convention is to use a single outer class to test all of the functionality of a given class. Each inner class contains all tests for a single method on the object under test.

For example:

```java
@RunWith(Enclosed.class)
public class StringTest {
    public static class Equals {
        private String string;
        
        @Before
        public void setUp() {
            string = "Testing";
        }

        @Test
        public void testEqualStrings() {
            assertTrue(string.equals(testing));
        }
    }

    public static class IndexOf {
        private String string;

        @Before
        public void setUp() {
            string = "Testing";
        }

        @Test
        public void testIndexNotFound() {
            assertEquals(-1, string.indexOf("foobar"));
        }
    }
}
```

### How are Terasology's game systems tested?

Test classes that require a Terasology environment should extend [`TerasologyTestingEnvironment`](https://github.com/MovingBlocks/Terasology/blob/develop/engine-tests/src/main/java/org/terasology/TerasologyTestingEnvironment.java) - a test class that sets up a headless environment by initializing core game systems and providing access to them via the `context` field or the `CoreRegistry`.

=====
Terasology's test suite can be found in the [engine-tests/src/test/java/org/terasology](https://github.com/MovingBlocks/Terasology/tree/develop/engine-tests/src/test/java/org/terasology) folder.