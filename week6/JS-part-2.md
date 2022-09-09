## Sending Requests with JS
### AJAX
- Asynchronous JavaScript and XML
- Asynchronous meaning these requests can happen along-side othe processes
- Using JavaScript to send these requests
#### XMLHttpRequest
- Series of events
    1. Event occurs on a web page (click, page load, etc.)
    2. Use JavaScript to create an XMLHttpRequest
    3. The request makes an asynchronous request to the server
    4. Server process the request
    5. Server sends a response back to the client
    6. Browser/client processes this response
    7. Update the page with the new data from the request
- Ready States - indicate what state the request is in:
    - 0 - not initialized
    - 1 - connection established
    - 2 - request was received by server
    - 3 - processing request
    - 4 - request is finished and the response is ready
- Methods/Attributes
    - request.open(HTTP Verb, url, async)
    - request.onreadystatechange(function) - specify what occurs when the ready state changes
        - in this function, we can use the "this" keyword to access the request
            - request.readyState
            - request.responseText
    - request.send() - send the request

### Promises
- We use promises to handle asynchronous requests in JS
- When we create promises, we specify what happens when the request is successful and what happens if the request is unsuccessful
- We pass in 2 arguments, which are callback functions, resolve (success) and reject (failure)
- When we execute a promise, we call the .then method to specify actions to take after a success
    - .catch to specify actions to take after a failure
- When we resolve, we look at the function that we passed in the .then
- When we reject, we look at the function that we passed in the .catch

### Fetch API
- fetch returns a promise, so we specify what we do upon successful request and then what we do based on an unsuccessful request
- The .then takes in a function as a parameter
    - So when we pass in a function to .then, we usually use an arrow function for simpler syntax
    - Because of the way fetch is set up, the arrow function takes in one parameter, which is the response
    - Usually, our first .then takes the response value and then returns a response.json(), converting the data from string to JS object
    - Once the response is JSONified, we can interact with it in the next .then and do whatever we would do to it normally (setting the HTML, etc.)


### Importing/Exporting
- export - we use this keyword to make the variable/function available in a different file
- import - take in something from a different file
    ```
    import {val} from './module1.js';
    import {val2 as newVal} from './module1.js';
    ```

### Async and Await Keywords
- async - when we apply this to a function, the function will run asynchronously, return a promise
- await - only valid inside of async functions, wait until the promised is resolve/returned

### Errors in JS:
- When something unexpected occurs, errors can be thrown in JS
    - Trying to access something an invalid url
    - Trying to access a property of a null object
- In JS, we can use try/catch blocks
```js
try {
    console.log(object.name);
    // in our catch block, we define what happens if we encounter the error:
} catch (error) {
    console.log("Object is not defined");
}
```
- We can also use console.error instead of console.log to print out messages as an error
    - In chrome, we will see that error messages are printed in red


### Iterators:
- We can use iterators to iterate/loop through elements in an array
- We can use generators to generate values based on some functionality that we define
- We can use Iterables, by implementing the iterator method to use generators with the for-of syntax


### Truthy vs Falsey Values in JS
- Truthy value is any value that returns true in an if-statement or any conditional check
- Falsey values return false in conditional check
- List of falsey values:
    - 0
    - ""
    - false
    - null
    - undefined
    - NaN - not a number
- True and False are boolean values
- Truthy and Falsey are adjectives used to describe if a value will be recognized as true/false in an if statement
- True is a truthy value
- False is a falsey value

### OOP in JS
- Encapsulation in JavaScript using Closures
- Inheritance
    - As of ES6, we can illustrate inheritance in JS using classes and the extends keyword
    - Before ES6, we used prototypical inheritance
        - 
        ```js
        let animal = {
            eats: true
        }
        let bunny = {
        __proto__: animal
        }
        ```