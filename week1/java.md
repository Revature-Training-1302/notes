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