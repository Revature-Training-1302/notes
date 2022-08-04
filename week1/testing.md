## Test-Driven Development
- Write tests first, building the project afterwards and basically writing code until all the tests pass
- JUnit - framework that lets us write tests for Java
- Example:
1. Lets say we're creating a Calculator app that includes addition. 
2. Instead of writing the code first, we would actually write a test first. 
3. For example, a test could be something like "If add 2 and 3, we should get 5."
4. Then we would run our project, the code will fail because we didn't write any code yet. 
5. You would write the code until the test passed. At that point, you would know, or at least be pretty sure, that the code is working correctly. 

- In your main classes, you can write the method declarations and return some dummy value just so the tests will run. 

example:

```java
class Calculator {
    public int add(int a, int b) {
        // return some arbitray value to start with
        return 0;
    }
}

class CalculatorTest {
    public void testAdd() {
        int result =  Calculator.add(2,3);
        // make sure that 5 is the answer when we add 2 and 3
        assertEquals(5, result);
    }
}
```