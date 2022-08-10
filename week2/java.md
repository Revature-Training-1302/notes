## IntelliJ Tips:
1. Right-click on the class.
2. Select Generate.
3. Choose what you want to generate(constructor, getter, setter, etc.)
4. Select the fields you want it to apply to (hold shift to select more than one)
5. As always, make sure you know how to do it without the shortcut before you use the shortcut

## Access Modifier
- can be applied to methods, variables, classes
- private - can only be directly accessed within that class
    - classes can't be private
    - can be indirectly access if we have public getters/setters
- public - can be accessed anywhere in the entire project
    - no matter what package/class we're in, we can access this
- default (package) - this will apply if we don't specify the access
    - we can access the method/variable if we are in the same package
- protected - can access in the same package or any sub-class


## Non-Access Modifiers
- static - if we use this keyword, it attaches the variable/method to the class rather than an instance
    - static methods can be called from the class or the object
    - non-static method can only be called from an object
    - It's good to use static methods when you don't care about state (member variables)
    - We don't want to use static methods if we need access to member variables (then we can't reference "this")
    - static variables are attached to the class
    - We only want to use static variables if they are the same for the entire class (ex: the value of PI)
    - We do NOT want static variables if we want to keep track of state
    - If we want make it static, we add the keyword "static" before it
- final - we can't change it
    - variables - we can't reassign the value
        - We can change final objects by changing the fields but NOT reassinging
        - ex: can't do
        ```java
        final Mammal dog = new Mammal("Scooby");
        dog = new Mammal("Scrappy");
        ```
        - but we CAN do this:
        ```java
        final Mammal dog = new Mammal("Scooby");
        dog.setName("Scrappy");
        ```
    - methods - if a method is final, we cannot override it
    - classes - if a class is final, we cannot extend it
- abstract keyword - means we don't fill out the body of the methods
    - class - if you make the class abstract, this means you can have abstract methods within the class
    - method - if you make a method abstract, that means you declare it but don't fill in the body


## Scope
- Method Scope
- Class Scope
- Block Scope
- In general, different scopes are denoted by {}
- If we define something within a scope (or in a set of {}), then we can't use it outside that scope

## Exceptions
- unwanted or unexpected event that disrupt the normal flow of the program's instructions

### Error VS Exception
- An error is something we don't actually handle and usually don't have control over (Out of Memory, Stack Overflow)
- An exception is something we can and should handle in our program. If we don't handle these exceptions, the program could stop running

### Checked Exceptions
- Checked at compile time
- Examples: ClassNotFoundException, SocketException, SQLException, IOException, FileNotFoundException

### Unchecked Exceptions
- Runtime exception
- Not checked at compile time
- Examples: NullPointerException, ClassCastException, ArithmeticException, DateTimeException, ArrayStoreException

![Exception Diagram](https://media.geeksforgeeks.org/wp-content/uploads/Exception-in-java1.png)


### Handling Exception
#### Catching
- "Try" some potentially problematic code
- "Catch" any potential exceptions that are thrown and perform some behavior accordingly
    - In our catch block, we specify what exception we're handling
    - It must either be the type of Exception that could be thrown or a superclass
    - Ex: If we are encountering a FileNotFound Exception, we could catch FileNotFoundException, IOException, or the top-most Exception which is just Exception
- "Finally" clause will run no matter what
    - if we catch an exception or not
#### Declaring that it will be Thrown
- In the method declaration, we can declare that an exception will be thrown, therefore eliminating the need for a try-catch block
    - Be careful because the exception could still arise
- Only need to do one of these methods to make the program run

#### Shortcuts in IntelliJ
- Right-click -> Show Context Actions
    - pick either surround with try/catch
    - or Add exception to method signature

#### Throw vs Throws
- Throw is the action of making an exception happen
    - ```java
    throw new RuntimeException(e);
    ```
    means we are throwing a RuntimeException
- Throws is a clause or a warning that the method will throw an exception
    - ```java
    public static void main(String[] args) throws FileNotFoundException
    ```
warns us that the main method might throw a FileNotFoundException

### Exception Propogation
- If we declare a method throws something and it's called in a different method, we have to ensure the outer method throws the same exception
- If we use a try-catch block we don't have to propogate the exceptions

### Custom Exception
- we want to extend the Exception class
- Set up a constructor that takes in a message and calls the parent-class constructor with that message