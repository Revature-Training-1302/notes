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

## Misc
- Get geographic location https://www.w3schools.com/html/html5_geolocation.asp