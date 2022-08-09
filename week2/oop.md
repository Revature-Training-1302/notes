## Object Oriented Programming Pillars

### Inheritance
- Parent-child relationships
- Any methods/variables  that a parent has, the child will inherit
- The child can expand on the functionality that's passed down
- Open for extension, closed for modification
- Animal -> Mammal -> Dog

#### Types of Inheritance
- Single - One parent, one child
- Multilevel - Linear family tree, where one class inherits another which inherits another, etc.
- Hierarchical - one parent with many children
- Multiple (NOT ALLOWED IN JAVA) - one class inherits multiple parents
- Hybrid (NOT ALLOWED IN JAVA) - combination of Multiple and Hierarchical
- Rule of Thumb: One class cannot inherit multiple classes

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
- Polymoprhism means many forms

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