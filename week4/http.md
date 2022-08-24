## HTTP
- If we go to a website, we usually see http://www.google.com
- HTTP is the communication protocol used to communicate between server and a client
- HTTP - HyperText Transfer Protocol
- HTTP Request - sent by the client and contain all of the information that is necessary to complete the request
- HTTP Response - response back to the client from the server
### Types of HTTP Requests, HTTP Verbs:
1. Get - get information (get pet by id, get all pets, etc.)
2. Post - inserting, adding new information (register, adding a pet to the database)
3. Put - modify/update data that already exists
4. Delete - delete resources/records
CRUD 
- Create - POST(HTTP) - insert(SQL)
- Read - GET(HTTP) - select(SQL)
- Update - PUT(HTTP) - update(SQL)
- Delete - DELETE(HTTP) - delete(SQL)

### Response Code
- Give us information about the response
- Different ranges of values that correlate to a general idea of what the response
    - But the code itself is more descriptive
#### Ranges:
- 100s - informational, giving information, not a success or failure
- 200s - success, telling the user that whatever they wanted to do was successful
- 300s - redirecting the request somewhere else
- 400s - client-side error, something is wrong with the request, usually the client can fix this
    - 404 - page/path wasn't found (ex: google.com/dinosaur)
- 500s - server-side error, something went wrong in the back-end server, which means can't fix that
    - These would pop up if we have some exception thrown in our Java code
- List of the different status codes: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

### HTTP vs HTTPS
- S stands for secure
- encryption
- https://developer.mozilla.org/en-US/docs/Web/Security

### Helpful Links
- [Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP Session](https://developer.mozilla.org/en-US/docs/Web/HTTP/Session)
- [Request Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- [Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

## Postman
- For now, we've seen GET methods being triggered from our browser
- But how do we see POST, PUT, DELETE?
    - One way is that once we build a web page, insert some data, we can specify POST methods
    - Until then, we can test them out using Postman
- Postman is a program that lets us enter in endpoints and trigger the different servlets/controllers
- Go [here](https://www.postman.com/) to download the app. Just pick your operating system