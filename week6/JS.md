## JavaScript
- Scripting Language
- We write scripts and the code will execute sequentially
- Normally run in browsers
    - We can create script tags in an HTML file and include JS code in that
        - We usually want to put our scripts tags in the body, near the bottom of our visual elements 
            - If our script takes too long to run, it could slow down the display of the other elements
    - If we install Node, we can run JS on our local machine
        - https://nodejs.org/en/download/
        - Type in node -v in terminal to verify installation
        - To run a JavaScript file, type node file-name.js in terminal
- Provide the logic of what's going on in the front-end

## Variable Types in JS
1.  String
2.  Boolean
3.  Null
4.  Objects
    - Arrays
5. Number
6. Undefined 
7. Symbol
- JS is loosely typed where we don't specify the type of the variable when we create it
### Null vs Undefined
- Undefined means we haven't given it a value, can be assigned implicitly or explicitly
- Null means somewhere in the code, the variable was set to null
    - We could use null to represent the result from get by id if the id doesn't exist
### Declaring Variables
- Use var to define any type of variable
- Let and Const

### Type Coercion
- == checks value, but not type, allow for type coercion
- === checks value and type

### Scopes
- Global - anytime we declare a variable at the highest scope (not in any functions, blocks, classes)
    - we can access global variables anywhere within the program
- Function scope - declare a variable within a function, we can't use it outside of that function
- Block scope - if define a variable using var, we can use it outside of block scope
    - let and const - if we define a variable within a block (loop, if statement, flow control blocks), we can't use it outside
    - const doesn't let you change the value after you set it, like the final keyword in Java
- Lexical scope - defining a variable in a function as well as outside, use the closest scope and then search outwards if we can't find a value

#### Hoisting
- think of an HTML page with a script that uses a variable before it's defined
```html
<script>
    console.log(x);
    var x;
</script>
```
- hoisting is the process of moving variable and function declarations to the top of the script to make sure we don't run into issues where the function or the variable is not defined
- works only with var, not let

### Functions
- Callback functions - passing a function as a parameter into another function
- Arrow functions - syntax for writing functions introduced in ES6
- Anonymous functions - store arrow functions in a variable
- Self-Invoked Functions or Immediately Invoked Function Expression) - functions that are called right after they are defined
- Closure - if we return a function from another function, it will still have access to the outer function's scope of variables

#### Passing by Value
- JS functions are pass-by-value which means if we pass in a value, those changes won't be reflected outside of the scope of that function, in the case of primitives
- With objects, it's a bit tricker
    - When we pass in an object to a function, we're actually passing in the reference. So, even though we're still passing by value, so the object's data can be affected by operations that happen within the function

### ES6 (ECMAScript)
- came out in 2015
- Introduced a lot of new features to JS
    - let and const keywords
- Classes
- Default Parameters
    - defining a value for a parameter in a function which is taken if no value is given when the function is called
- Arrow functions - different syntax for writing functions, allows for anonymous functions
- JS Classes, extending from classes

### JS Classes
- follow similar patterns as Java classes and similar syntax
- We can have methods, fields, just like Java
- We use the "this" to access the current object's properties
- Computed properties, takes two or more existing properties and combines into one new one
- Just like Java, we can have static methods

### Strict mode
- When we have scripts in an HTML file, we can use strict mode so that we'll be warned if we do certain things that are usually ignored:
    - using undefined variables
    - using reserved words as variable names
    - duplicate properties/parameters
    - assigning values to read-only properties
    - modifying arguments object
    - deleting an undeletable property
- To initiate strict mode, include this line :
```
'use strict';
```
in your script tag

## Misc
- Get geographic location https://www.w3schools.com/html/html5_geolocation.asp