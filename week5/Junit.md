## JUnit

- JUnit is a framework that helps us test our Java code
- The key point here is we're doing unit testing
- Unit testing is the idea of testing our application piece by piece
- Usually, with Unit Testing in Java, we test out the methods, give some parameters and hope that we get the correct output

### Setting up a Project for testing
- With Maven, we can choose the maven-archetype-quickstart
- This will automatically set up the structure 
    - Main and Test and they both have a single class
        - App.java
        - AppTest.Java
    - Example, if we have a Counter class, we would also have a CounterTest class
        - Within the CounterTest class, we would test out all of the methods in the Counter class


### Annotations
- @Test - tells our program that this method is testing something
- @BeforeAll - indicates that a method is going to run once at the beginning of the class, before all the tests are run
- @BeforeEach - indicates that a method is going to run once before each test
- @AfterAll - run after all tests in the class are finished
- @AfterEach - run after each individual test

### Methods
- assertEquals - ensure that 2 values are the same, otherwise the test fails
- assertArrayEquals - ensure that 2 arrays are the same in terms of values and length
- Big list of different types of assertions we can do in JUnit - https://junit.org/junit5/docs/5.0.1/api/org/junit/jupiter/api/Assertions.html

### Code Coverage
- In IntelliJ, we can run tests with coverage
- Coverage is the idea of how much code is being run with our tests
- If our tests cover a lot of code, that's a good sign that our test had fewer bugs
- On the other hand, if your coverage isn't that high, the mistakes could still be there, not being detected by the tests
- Make sure your tests are covering as many possibilities as possible based on flow control statements

### Exercise later
- You'll be given some code and have to write tests that pass and cover at least 80% of lines

### Good Testing Strategies
- Test postive/negative
    - Test the case where your method succeeds
    - Test the case where it fails
- For tests where you're checking multiple values
    - Check 0
    - Check 1
    - Check 2