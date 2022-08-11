## Object Oriented Programming Pillars

### Inheritance
- Parent-child relationships
- Any methods/variables  that a parent has, the child will inherit
- The child can expand on the functionality that's passed down
- Open for extension, closed for modification
- Animal -> Mammal -> Dog
- https://stackoverflow.com/questions/7187799/why-default-constructor-is-required-in-a-parent-class-if-it-has-an-argument-ed-c

#### Types of Inheritance
- Single - One parent, one child
- Multilevel - Linear family tree, where one class inherits another which inherits another, etc.
- Hierarchical - one parent with many children
- Multiple (NOT ALLOWED IN JAVA) - one class inherits multiple parents
- Hybrid (NOT ALLOWED IN JAVA) - combination of Multiple and Hierarchical
- Rule of Thumb: One class cannot inherit multiple classes

#### Exception to Multiple Inheritance Rule
- We can achieve multiple inheritance if we use interfaces
- One class can implement mulitple interfaces

#### "super" keyword
1. We can use it to call the constructor of the parent class. 
    - ex: super();
2. We can use it to call methods of the parent class.
    - ex: super.method();
3. We can use it to access variables of the parent class.
   -  super.param;

A -> B -> C -> D -> ... Z would be fine as long as no class inherits multiple classes

![Diagram of Inheritance](https://www.goseeko.com/blog/wp-content/uploads/2021/09/typescript-classes-types-of-inheritance.png)

### Polymorphism
- poly - many
- morph - forms
- Polymorphism means many forms

#### Overriding - Inheritance
- If have inheritance, we can override a method and change it's behavior
- When we override, we use the same method declaration as well as the @Override annotation
- We change up the body of the method to take on the new functionality
- We can only override the same method once per class
- Run Time Polymorphism

#### Overloading - same name, different parameters
- 2 methods with similar declaration (same name, different parameters), we can overload
    - different number of parameters
    - different types of parameters
    - different order of parameters
- Rule of thumb: As long as 2 methods don't have the exact same sequence of parameter types, they can be used to overload
- We can overload a method as many times as we want
- Compile Time Polymorphism

![Polymorphism](https://miro.medium.com/max/886/1*RYd4K00FeQshQ_clT8ALuA.png)


### Encapsulation
- packaging everything about an object into one unit
- data-hiding
    - make our variables private
    - public getter/setter methods


### Abstraction
- Hiding away the implementation details of methods
- We define the expected input/output/behavior, but we leave the details up to a different class
- In Java, we can achieve abstraction in 2 different ways:
    - Through the abstract class, abstract methods - partial abstraction
        - In an abstract class you can have abstract and concrete methods
        - In a regular java class, you cannot have abstract methods
        - Cannot instantiate an abstract class
        - If we extend an abstract class, we must fill in all of the methods or declare the class as abstract
            - fulfill the contract
            - must keep the method declaration the same
                - with one exception, child method should be at least as open than the parent method
        - In intelliJ, we can right-click class, generate, and implement methods automatically
    - Interface - full/complete abstraction
        - no concrete methods, meaning no methods that contain code
- Common QC Question: What is the difference between an abstract class and an interface?
    - the interface must be full abstraction
    - abstract classes can have concrete methods
    - class can implement multiple interfaces in Java

#### Real-World Example
- With databases, we need someway to connect and interact with them
    - We will create an interface that defines the functionality of what we want to happen
        - insert, read, delete
        - If we want to define the behavior first, we couldn't use a concrete class because we don't necesarily know the impementation just yet
    - We can implement the interface with 2 or more concrete classes and provide the same functionality with different implementations
