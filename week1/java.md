## Java
- Object Oriented - forming our code based on real life objects
    - many different classes
    - converting real life objects to code
    - Objects vs Classes
        - classes - blueprint
        - object - instance of class
        - can have multiple instances of the same class
- Machine Independent (Write Once, Run Anywhere)

## Compilation Process
- 2 step-execution
### Compilation
- .java file is passed through the compiler
    - look something like 
    ``` 
    class Car {
        int wheels;
        String color;
    }
    ```
- Source code encoded into Bytecode (machine-independent)
- End result is a .class file
### Execution
- The main class file (starting point) is passed to the JVM
- Goes through three stages:
1. Class Loader - loads all classes that are used in the program
2. Bytecode Verifier - check that the bytecode doesn't contain any damaging instructions such as variables being used before being initialized
3. Just-In-Time Compiler - convert bytecode into machine code

![Diagram of Compilation](https://media.geeksforgeeks.org/wp-content/uploads/java.jpg)

Read More about the compilation process [here](https://www.geeksforgeeks.org/compilation-execution-java-program/)

## JVM, JRE, JDK
### JDK - Java Development Kit
- Provides everything you need to develop and run the Java program
- Includes development tools and JRE

### JRE - Java Runtime Environment
- Provides an environment to run (not develop) a Java program
- Used by end-users

### JVM - Java Virtual Machine
- Responsible for executing the Java program line by line
- Allows for WORA (Write Once Run Anywhere)


![JDK, JRE, JVM](https://media.geeksforgeeks.org/wp-content/uploads/20210218150010/JDK.png)

Read more about the JDK, JRE, and JVM [here](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/)

Read more about Java [here](https://www.geeksforgeeks.org/java/)


## To Get Started
We'll need 2 things:
1. IDE (Interactive Development Environment)- IntelliJ, it will let us write code, run it, debug it
    - https://www.jetbrains.com/idea/download/#section=windows
    - https://www.jetbrains.com/idea/download/#section=mac

2. JDK - Java Development Kit which actually lets us compile and run the program
    - https://www.oracle.com/java/technologies/downloads/#jdk17-windows
    - https://www.oracle.com/java/technologies/downloads/#jdk17-mac

## Our First Program (Hello World)
- public class HelloWorld - this defines a class
    - a class can have methods and variables
    - class names should start with a capital letter
- public static void main(String [] args) - this defines a method
    - Specifically, it is our main method meaning it is the entry point to our program
    - A method, in general, is a chunk of code that is executed whenever the method is called
    - A method is like a function
    - Method names usually start with a lower case letter

## How to Research/Find out more
1. In IntelliJ, we can right-click -> Go-To -> Declarations and this should take you to where the class is defined and hopefully tell you a little bit about it. 
2. We can use Google and the internet to find information. Just make sure you're looking at valuable sources
- Oracle - the official Java documentation site
- StackOverflow - q&a forum, a lot of good questions
- geeksforgeeks
- w3schools
3. Ask a co-worker
    - Sometimes, the act of explaining how something works reinforces our understanding of it

## Primitive Types
- any type of value that's not a class
- examples: char, int, double, float, long
- char - letter or symbol, ex: 'a', 'c', '4'
- int, bytes, long, short - represent whole numbers, ex: 1, 3, 4
- float, double - represent decimal numbers, ex: 3.0, 3.14, 9.001
- boolean - true or false values
- Read more about primitve types [here](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)

## Operators
- math operators -> +, -, *, /, %
    - % is remainder
- boolean operators -> 
    - ! - not
    - && - and
    - || - or
- comparison:
    - == means we check if 2 values are the same

## Scanner
- a class that lets us read user input
- first we have to create a scanner instance
- then we can use the scanner to read data from the command line (Strings, int)

## Flow Control
- if, else if, else statements - let us control what happens based on different conditions
    - we need exactly one if statement
    - we can have 0 or more else if statemenets
    - we can have 0 or 1 else statements
    - in a single "group" of if statements, only one condition will trigger
- for loops and while loops - run certain code a certain number of times or until a condition is met
    - while loops
    - for loops
        - for(intiialization; condition; increment)
    - Three main parts of a loop
        - Initialization (int i = 0)
        - condition (i < 100)
        - increment (i ++)
    - Key words for loops:
        - break - immediately exit the current loop
        - continue - skip the current step and move on to the next one
- switch statement - similar to if, else if, else - check a single variable and run different code based on the value
    - Once a single case is matched, every following case will also trigger
    - Keep in mind we can achieve everything a switch statement does with if-statements, but it does clear up the syntax
    - we can use primitve types and strings with switch statements

## Classes and Objects
- Classes are like the blueprint that we go off of in order to create objects
    - Methods - like functions, actions that we can perform
    - Variables - data about the object or class
- Objects are the instances of that class
    - created with the new keyword
    - Each object can hold a different state (data)
- Methods
    - Return Type - what type of value the method returns (output)
    - Paremeters - values that we pass in to the method (input)
    - Body - what happens when the method is executed
- Constructor
    - A special type of method that lets us create an object
    - Constructors ALWAYS have the same name as the class
    - we can have multiple constructors for one class
    - If we do not define any constructor in our class, Java will create the default constructor(no arguments) for us
        - Once we create a constructor in our class, Java won't create a constructor for us anymore
    - A default constructor (no arguments)
    - A parameterized constructor is a constructor that takes in parameters (input)
- "this" keyword
    - indicates that we are referring to the current instance of an object

## The Object Class
- Inheritance
    - one of the 4 pillars of OOP
    - parent-child information, child class pulls variables and methods from the parent
- Every class is a descendant from the Object class
    - meaning every class is going to have a certain set of methods that it has just because it inherits from the object class
- The class is called "Object" and contains different methods that every class will inherit:
- Methods:
    - equals - determine if 2 objects are equal
        - until we override the .equals method, it acts exactly like ==
        - == check the memory address of the object (reference)
        - So, if we create 2 different objects using the new keyword, == comparison will always return false
        - However, if we override the .equals method, then we control how the objects are compared (by value)
    - getClass - gets the runtime class
    - hashcode - returns the hash value
    - toString - converts an object to a string representation
- [Documentation](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html)

## Constructor/Method Overloading
- Overloading is when we have 2 methods of the same name but different parameters
    - different number of parameters
    - different types of parameters
    - different order of parameters
- The compiler will automatically know which one to pick based on the parameters

## Annotations
- begin with the @ symbol
- used to decorate (put on top) methods, class, or variables
- provide some extra information about what's going on
- ex: @Override tells us that we are overriding a method

## Hash Values
- code/integer representation of an object
- consistent hash function, where one object will only have 1 hash value 
- same input to produce the same output
- It is possible to have multiple inputs with the same output hash code
    - example: "act" and "cat" could produce the same hash code if the hash function was as simple as adding up the characters

## Strings
- https://docs.oracle.com/javase/7/docs/api/java/lang/String.html
- String pool
    - We notice that in our programs, we can create strings using notation that is similar to primitives
    - Even though, String is a class, we can instantiate it like a primitive
    - We can create a string using the "new" keyword
    - The difference is, it won't be created in the String pool
### String Pool
- To save memory, if we have 2 or more strings with the same value, the string will be created once in the string pool and the different variables will point to the same string
- The exception to this rule is if we use the new keyword. In this case, the string will be created outside of the string pool and it will be a different memory location no matter what
- Only one string pool, if we use the "new" keyword, the string will just be in heap memory
- Strings are immutable (can't be changed) because of the String pool
    - Lets say we have 100 strings that point to the same value in the String pool
    - If strings were mutable, then that would affect all of the other references to that string

![String Pool Diagram](https://www.javastring.net/wp-content/uploads/java-string-pool-1024x564.png)
### Stack vs Heap
- Stack and Heap are 2 different parts of memory
- In the stack, we see primitive values and variable references
- In the heap, we see object values ("fish"), new object

## For Each
- a shorter way to iterate through an array, or any sort of collection
- syntax:
```java
for(Type counter : array) {
    System.out.println(counter);
}
```