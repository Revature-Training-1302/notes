## Scope vs Encapsulation
- Scope has to do with where you can access variables
- 3 main types of scope:
    - Class Level Scope
        - Object Level Scope (non-static)
    - Method Level Scope
    - Block Level Scope
        - if-statements
        - loops
- The general rule is if we define something within a scope, we can't use it outside
- Scope usually denoted by curly braces

## Static Scope
- If we make something static, then it's accessed through the class scope
- Otherwise, object scope
- Static - reusing the value throughout the entire class, rather than having a different instance for each instance

- https://www.codecademy.com/article/variable-scope-in-java
- https://www.geeksforgeeks.org/difference-between-static-and-non-static-method-in-java/

## Exceptions
- unwanted/unexpected behavior

### Exceptions vs Errors
- We want to handle exceptions
    - ArithmeticException
    - ClassNotFound
    - SQLException
- Errors, we usually don't try to handle them
    - Virtual Machine Error
    - Stack Overflow
    - Memory
- Let the compiler deal with errors
- https://stackoverflow.com/questions/5813614/what-is-difference-between-errors-and-exceptions#:~:text=Error%20is%20something%20that%20most,or%20write%20to%20the%20log.


### Types of Exceptions
- Checked Exceptions
    - compile-time
    - we usually get some warnings in our IDE if there is potential checked exception
    - IOException, SQLException, ClassNotFound
- Unchecked Exceptions
    - not checked at compile time
    - won't get a warning in IDE
    - Arithmetic, IndexOutOfBounds

### Handling Exceptions
- There are 2 ways of handling exceptions, we only have to do 1
####  try-catch-finally
- try-block is the first one, where you put code that could throw an exception
    - ex: 
    ```java
    String [names] = {"Rory", "Abiy", "Zabeer"};
    try {
        System.out.println(names[20]);
    } 
    ```
- catch-block is where we provide the code that executes if we encounter the specified exception:
    ```java
    catch(IndexOtBoundsException e) {
        e.printStackTrace();
        System.out.println("Trying to reach an index that doesn't exist!");
    }
- finally block: this will execute no matter what (whether or not the exception was thrown)
    ```java
    finally {
        System.out.println("This happens no matter what.");
    }
- We need exactly one try block, we can't have a catch/finally without a try block
- For one try block, we can have multiple catch blocks
- And we need either a finally, catch, or both
- https://www.youtube.com/watch?v=1XAfapkBQjk

#### Throws
- if we add a throws clause to the method signature, it's like a warning that this method may throw an exception
- It's a way of letting our program run if we have a checked exception
- Keep in mind if we don't catch it and handle it, our program will still stop if the exception is thrown
- throw vs throws
    - throw is the action of throwing an exception
    - throws is a clause that indicates an exception could be thrown in this method

## JDBC
- https://www.tutorialspoint.com/jdbc/jdbc-introduction.htm
- All about connecting Java to database
- Java DataBase connectivity
- From Java, we can
    - Connect to the database
    - Create SQL queries/commands
    - Execute queries/commands
    - View the results from the queries
- Interfaces
    - Driver Manager, manages the database drivers, helps us set up our connection
        - getConnection method, pass in url, username, and password
    - Driver, handles the connections to the database
        - we don't interact with it in our code, it's managed by the Driver Manager
        - We include the postgresql driver/dependency in our pom, but it is handled by the Driver Manager
    - Connection, communication interface with the database
        - all communication happens through the connection
    - Statement/PreparedStatement - write our queries/commands and put in parameters
        - submit these commands to the database
        - Use Statement if there are no dynamic values
        - Use Prepared Statement if we want to put in some values and prevent SQL Injection
    - ResultSet - These objects hold data retrieved from a query/operation, it acts as an iterator to allow you to move through its data.
        - resultSet.next()
        - ResultSet is like a pointer
        - https://www.tutorialspoint.com/java-resultset-next-method-with-example
    - SQLException
        - handles any errors that occur within the database

