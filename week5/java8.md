## Java 8
- Introduced some features to Java
- Different syntax of doing operations that we've already seen before
- In IntelliJ, we have to make sure our language level is set to 8 or above
    - File -> Project Structure -> Modules
    - Click on the drop-down menu Language Level and select 8 or higher
### Lambda Expressions
- parameter(s)
- expression/code block
#### Different Variations:
- parameter -> expression
    - take in a single parameter and return a single value
- (parameter1, parameter2,...) -> expression
    - takes in multiple parameters and returns a value
- (parameter1, parameter2, ...) -> {code}
    - takes in multiple parameters and runs some code
- Notice that lambda expressions are similar to methods in that they can take values in and return a value, but they are more concise in their syntax and they can be declared within methods
### Functional Interfaces
- An interface with a single abstract method
- We can use functional interfaces to store lambda expressions
- Built-in Functional Interfaces
    - Consumer - takes in a single value and not return anything
        - take in a value and print it out
    - Predicate - takes in a single value and return a boolean
        - check if a number is even
    - Function - takes in a single value and return a single value
        - square/cube function
    - Supplier - not going to take in a value but return a single value
        - return a random number
    - Bi-versions of the first 3:
        - BiConsumer takes in 2 values
        - BiPredicate takes in 2 values
        - BiFunction takes in 2 values
### Streams
- A way to process collections of objects in Java
- Intermediate Operations (similar to JS array methods)
    - map - apply some function to every element in the collection
        - return a value
    - filter - filter out the elements based on some condition
    - sorted - sort the elements
- Terminal Operations
    - collect - take in all of the return values and return it to some Collection object
    - forEach - apply some function/operation to each returned object
        - perform some operation
    - reduce - reduce all of the elements of the stream to a single value