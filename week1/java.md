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