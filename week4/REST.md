# SOA

Service Oriented Architecture: an application designed to be accessed by another application as a service. Primarily refers to business to business (B2B) use cases.

ex. Grubhub exposes an API for China Express to consume. Equifax exposes an API so car dealerships can access your credit score.

## Properties of SOA
1. Represents a business outcome
   1. Trying to access a functionality of the business (ex. claiming an order/ calculating a credit score)
2. Self-contained. (The client doesn't need to send multiple requests to different servers. The client sends one request and the service handles things from there.)
3. Black-box to consumers.
   1. Input comes in (you know what it needs and send it. ex. your ssn)
   2. Output comes out (you know what will come out. ex. your credit score)
   3. You don't know what happens in-between (how did they calculate that score?)
4. May consist of underlying services. (the credit score service might call another service to obtain information it needs.)

## Web Services

Applications designed to be accessed by another application as a service over the internet.

A SOA over the internet


### REST

REpresentational State Transfer

IS AN ARCHITECTURE

Defines a way to build an application utilizing HTTP to access the "representational state" of an entity. 

#### Representational State

A copy of the state of an entity on the service.

Not necessarily (and usually not) the entity itself, as that entity only exists on the server or database.

We can use this copy to mutate/replace/create entities on the service.

REST is all about the practice of utilizing representational states of an entity to mutate the actual state of that entity.

#### Interface

HTTP/S: We access the application by sending GET, PUT, POST, DELETE, PATCH, OPTIONS, CONNECT, HEAD, and TRACE requests to it.

Data can be transmitted in any language agnostic format. We can transfer application state using XML, JSON, or other languages. 


#### REST Constraints
1. Client-Server Architecture
   1. separate the user interface from the data.
   2. separate the end-user from the data.
2. Statelessness
   1. The server should not maintain state.
   2. All state should exist elsewhere usually a database
   3. How do we get around this for session data?
      1. Store it as cookies
      2. Store is as tokens we can process and authenticate with each request.
3. Cacheability
   1. Data can be cached by a browser/client
   2. Each response would categorize it's data as cacheable or non-cacheable
4. Layered System
   1. The service can consist of underlying services.
5. Code on Demand (optional)
   1. The service can serve executable code. (sending a js file to be run on the client's computer to save on processing.)
6. Uniform Interface
   1. Resource Identification in Requests
      1. We identify our resources through the use of a URI.
      2. In the request itself, the URI for the resource can be found
      3. ex. GET request to `/cats/` | GET to `/restaurants/McDonalds`
   2. Resource Manipulation through Representations
      1. When w try to update a resource we send a representation of that resource to the server. The server than updates the corresponding entity with that data.
      2. ex. PUT to `/restaurants/McDonalds` but *our version* of that has an extra menu item.
   3. Self-descriptive messages
      1. GET request should retrieve something.
      2. a POST request should post that information somewhere on the server.
      3. DELETE request should remove something
      4. if the `application/json` header is present, the body should be in JSON.
      5. etc.
   4. Hypermedia As The Engine Of Application State (HATEOAS)
      1. We can represent other entities by giving a URI.


#### RESTful API Design

##### Collections

`https://mycats.com/cats`

`/cats` is a collection. Any operation on that URI affects the entire collection. Collections should be plural. They should be the name of the entity that it is a collection of.

GET - returns a representation of the collection.
POST - creates a new member of the collection.
PUT - replace the entire collection
DELETE - delete the entire collection
PATCH - update the collection with the parts of the collection included in the PATCH

##### Resources

`https://mycats.com/cats/Sprankles` or `https://mycats.com/cats/1`

`/cats/Sprankles` or `/cats/1` represents a single cat. The collection followed by the id of the cat we want. Any operation done on a resource should only affect that resource

GET - returns a representation of that resource
POST - creates an entity inside of that resource
PUT - replaces that resource or creates it if doesn't exist
DELETE - removes the specific resource
PATCH - update the resource with the parts included in the PATCH

##### Guidelines
* Pluralize collections
  * /cats
  * /books/
  * /restaurants/1/menuitems
  * octopi
* Don't use verbs
  * your METHODS are your verbs, you don't need to put them in your URLS
  * /cats/1/add-cat is VERY BAD
  * POST to /cats/1/kittens is good (add a kitten to the cat)
  * POST to /restaurants is good (add a new restaurant)
* Make your endpoints descriptive
  * /z/3 is bad
  * /cats/3 is good

## Web Stuff

URI: Uniform Resource Identifier - a string of characters that is used to identify a name or resource on the internet by location, by name, or both.

URL: Uniform Resource Location - A URI that specifies *WHERE* a resource is available and *HOW* to retrieve it. A URL has to specify a protocol and the domain. ex: `http://mywebsite.com` and `http://mywebsite.com/cats/1`

URN: Uniform Resource Name - A URI that specifies a unique name for a resource. ex. `/cats/1` or `http://mywebsite.com/cats/1`

## HTTP

Hyper-text transfer protocol

protocol - a set of rules for communication

Originally designed for the transfer of HTML documents via the internet.

### Structure

To use the http protocol we need to create an http request and recieve the http response

#### http request

Consists of a head and a body.
The head contains meta-data such as what URI we're sending the request to, what kind of request it is, and any headers we included.
The body contains the actual subject of the request, usually the data we're adding to the server.

#### http response

consists of a head and a boyd.
head contains the status code and other information
body contains the response usually in the form of an html document but sometimes it is data.

### Http Methods

Define how we transfer information and what the reciever is supposed to do with it.

*Idempotent* - An operation that has the same result no matter how many times you do it.

```Java
// assignment operation is idempotent
int i = 5;
i = 5;
i = 5;
i = 5;

// adding to an arrayList is not idempotent
List<Integer> i = new ArrayList<>();
i.add(5);
i.add(5);
i.add(5);
```

(I) = Idempotent, (N) = Not Idempotent

* GET - (I) - Retreives data from the server, no information in Body of request
* POST - (N) - Creates or appends information to a collection or resource. We do not know the final destination of the new resource (If I add a new restaurant, I do not know what ID the database will give it)
* PUT - (I) - Replaces information on the server at the location specified.
* DELETE - (I) - Removes data from a specific location
---
* PATCH - Update/replace part of a resource
* CONNECT - Try to establish a connection
* TRACE
* OPTIONS - Attempt to establish which methods are allowed on a specific resource
* HEAD - (I) Retrieves just the header information from the server.

### Status Codes - THE SERVER SPEAKS

#### 100 - Informational - I'm doing something

* 100 - Continue - I've received part of your request, continue with the next part.

#### 200 - Success - I did it.

* 200 - Ok - Nothing went wrong.
* 201 - Created - You asked me to make something and I did.
* 204 - No Content - I did what you asked and have nothing to show for it.

#### 300 - Redirect - What you asked for is somewhere else

* 301 - Moved Permanently - I'm sending you there, please go there in the future instead of here.

#### 400 - Client Error - YOU did something wrong

* 400 - Bad Request - You sent me a request and I don't understand it.
* 401 - Unauthorized - You are not authenticated.
* 403 - Forbidden - You do not have access to this document.
* 404 - Page Not Found - There is nothing at that URI.
* 405 - Method Not Allowed - You sent a PUT, I don't allow PUTs on that resource.
* 409 - Conflict - This request would invalidate the state of the server. (usually, you tried to add something that already exists)
* 418* - I am a Teapot - You asked me to make a coffee, but I'm a teapot.
* 451* - Unavailable for Legal Reasons - Fahrenheit 451 (about government censorship). The title is suppposed to be the temperature at which books ignite. Content was taken down because the goverment requested it be removed. Usually used for copyright claims.

#### 500 - Server Error - I did something wrong

* 500 - Internal Server Error - Usually the code entered an error state. Threw an exception in Java.
* 503 - Service Unavailable - The server went down temporarily

## Richardson Maturity Model [Fowler](https://martinfowler.com/articles/richardsonMaturityModel.html)

How RESTful is your service? We aren't talking about Constraints, we're talking about the design of the service itself. How did you design your endpoints and how you interact with them. **Note, that the Richardson Maturity Model does not define a REST web service, it merely provides a way to discuss them.**

Constraints we aren't thinking about: Statelessness, Code on Demand, Layered System, Cacheability

* Level 0: Not RESTful at all - Utilizing Http at all. We are just using http as a transport protocol, but nothing else is defined.

We have an endpoint and we can send requests to that endpoint telling the service what to do.
Note, all requests use the same endpoint.

* Level 1: a little RESTful - Introduces Resources

Each resource has it's own endpoint that we can send requests to in order to accomplish tasks.

* Level 2: sorta RESTful - Introduce Http Verbs

We determine *what* we are doing with each request by examing the http verb used to make it.

* Level 3: Probably RESTful - HATEOAS

Once we are representing other resources within our resource in a way that allows our client to obtain that resource... once we're self-documenting, that's when we make it.


