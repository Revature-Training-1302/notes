## TypeScript
- A typed superset of JavaScript
- It is more strict than JS which requires more work on our part to set up the types for our variables
- It also allows TypeScript to guarantee that these type declarations are kept

### How to install and use TypeScript
- type ```npm install -g typescript``` into a command prompt
- Make a file called hello.ts, write some regular JS code (or TypeScript code)
- To transpile into JS code, we run ```tsc <name_of_file>```
- This will convert the ts file into a js file
- Finally, we can run the js file with node
- To check version, type ```tsc -v```

### Give types to Variables
- In JavaScript, we just used let, const, var to declare variables and didn't give a type
- We'll still use let, var, const, but we also can declare the type of the variable
- ```let x:Number = 4```
    - This would prevent us from assigning a string value to 4
- Strong Typing
- Arrays:
    - ```let names:String[] = ["john", "bob", "steve"];```

#### ? and !
- ? makes a parameter in an interface optional, so we don't need to include it when creating an object of that type
    - We could use this for id because we don't always know that value ahead of time
- !  means that the variable can't be null or undefined, telling the compiler to not worry or throw errors if we declare it without initializing it, because we're promising that this variable will be assigned a value later on

#### Interfaces
- When we want to define a custom type for an object
- We give what fields the object has and what types those fields are
- We usually make an interface for each entity that we're working with in our project
```ts
interface PersonI {
    // make this id field optional using the question mark
    id?: Number,
    name_: String,
    age: Number,
    job: String
}
// this variable is of type person:
let p1:PersonI = {
    name_: "bob",
    age: 20,
    job: "programmer"
}
```

#### any keyword
- If we declare a variable as "any", we can change its type

### OOP 
- Classes
- Inheritance
- Access Modifiers
    - public - we can access anywhere
    - protected - we can access within the class and sub-classes
    - private - we can access within that class
- Non-Access Modifiers
    - readonly - used for class fields, makes the fields immutable (like final in Java)
        - Unlike const, we use readonly for class fields

### RxJS
- Reactive Extensions for JavaScript
- Use Observables to write asynchronous code

#### Obervables
- pass messages/data around our program
- asynchronous programming
- Publisher/Subscribe design pattern
- When we return an observable, the received has to subscribe to that data in order to see it/use it
- Observables are similar to promises but observables can emit multiple values, whereas promises return a single response
- By default, when we call HTTP requests from Angular, those will return observables
- We can simulate HTTP requests using the "of" method

#### Subjects
- A type of observable where the values can be multicasted to many observers
- Three Variants
    - Behavior Subject - store the current data of any observer declared before it
    - Replay Subject - provides a option to choose how many values we want to emit from the last observer. This subject stores and then passes the last specificed option values to the new observer
    - Async Subject - emit the last value to observers when the sequence is completed, nothing willhappen if we don't call subject.complete();

### Decorators
- Syntacically similar to annotations in Java
    - @Decorator
- Can be applied to
    - Class
    - Methods
    - Properties
    - Parameters
- Decorators evaluate some function at runtime
- https://www.typescriptlang.org/docs/handbook/decorators.html