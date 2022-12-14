## Tips for Project
Projects can be stressful and intimidating. Here are some general tips to help with this first project. 

### 1. Break it into different pieces. 
- There are many ways to take the project specs and divide them into more easily managed components. The first way is through layers/packages. In our pet project, we've had the DAO layer, service layer, and command line layer. The command line layer will soon be replaced by the servlet/controller layer. Furthermore, you have the entity class which stores the data of an object (employee, manager, pet, person, etc.).

- Within each layer, you can break up the work further into classes. And within classes, you break it up into methods. If you work on the project method by method, you only have to deal with a few lines of code at a time. Look at out pet project for an example on how we break up the entire project into more managable pieces of code.

### 2. I also like to recommend to work from the bottom-up. 
- In other words, start at the data layer: set up your tables, columns, and relationships. Then work with the DAO layer. The DAO layer will be pretty similar for most objects. You will most likely need the CRUD methods (insert, update, delete, read/get) and possibly some additional layers. These DAO methods were implemented in our pet project, so definitely use that as a reference.

- Once you have the DAO layer completed, you can head to the service layer. At this point, you can start taking the project requirements and turning them into methods. The good news is that, a lot of the time, the service layer just needs to call a DAO method. Take register for example. Registering means you are creating a new user. So, the register method probably just needs to call the insert method in your DAO.

- Finally, once your service layer is set up, you can work on the controller layer which is all about getting the input from the user. For now we've been using a command line interface but we will see this week that it will be replaced by a servlet (more on that later). The cool thing about separating the project into layers is that we can isolate the logic, break up the pieces, and work on them step by step. 

- Working from the bottom up is helpful because it helps eliminate situations where you're relying on code that hasn't been written yet. For example, if you started working on the command line interface first, you would soon realize that a lot of the code relies on service methods, which rely on the DAO layer, which relies on the database and tables being created. 