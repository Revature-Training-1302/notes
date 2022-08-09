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