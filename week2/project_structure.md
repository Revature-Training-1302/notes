## Layers
- In Java, we set up our layers in packages
### Data
- DAO - Data Access Object - an object that helps us interact with data, usually in the form of a database
- Usually with DAO's, we create an interface for our different methods
- Some common data methods include:
    - insert - creating or inserting new data into the database
    - update - updating information that already exists in the database
    - read -  reading information (either single or multiple entries from the database)
    - delete - permanently deleting information in the database
- We will see these methods in today's demo.
- We usually have one interface for each entity, and each interface has multiple methods
### Service Layer
- The service layer will handle a lot of our "business" logic
    - In a lot of cases, our service layer is just a matter of calling the correct data methods
    - But if we need to any logic that pertains to the application itself, we can write that logic in the service layer
### Controller Layer
- The controller layer is how we accept requests from the front-end
- It parses the requests and forwards them to the correct service layer
- We will understand this more during week 4
    - For now, keep in mind that the controller layer is the closest layer to the front-end
    - In the case of our diagram, the controller layer would be close to the dotted line in the middle

### Order of Layers
- Client Request(Postman/Browser) -> Controller Layer -> Service Layer -> Data Layer -----JDBC-----> Database

### Persistent storage vs Temporary Storage
- In Java we have memory where we store our variables and data but once the program is over, that data is lost
- With persistent storage (database), the data will be available always


### Entity
- An entity, while not a layer is an important piece of the full-stack puzzle
- It let's us packae together information and send it around
- Entities are classes that represent physical objects in our app
    - ex: employee, manager, pet, user, ticket, etc.
- We use the entities at almost all, if not every layer
- In Java, we will use Encapsulation with our entities

### Exceptions
- Exceptions can store your custom Exception classes
- ex: RegisterException class that you can throw when something goes wrong with registering a user
    - username already exists

### Some Patterns we see often
- For each entity, we usually see a different controller, service, and data interface/class
    - So for a project with two entities, we would see 2 controllers, 2 services, 1-2 data interfaces, and 2 data classes that implement the interface(s)
- CRUD Operations - We will bring up this term a lot. It is a common theme in full-stack applications
    - Create
    - Read
    - Update
    - Delete
    - These operations exist on the controller, service, and data layers