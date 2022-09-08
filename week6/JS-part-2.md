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