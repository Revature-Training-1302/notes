## Java Database Connectvitiy
- Connect Java to Database
- We already have a demo project set up that uses dummy data
- But today we are going to connect that project so that it can store data in the database

## Design Pattern
- A set of rules/structure we can follow when designing an application or a part of an application
- Guidelines that we follow to ensure organization, efficiency (storage or time), readability

### Factory Design Pattern
- Set up a class whose responsbility is to create or produce something
- For today's jdbc example, we will set up a connection factory that produce a connection to our database
- We use factory so we can have special logic when creating something
    - Rather than just using the "new" keyword to create something

### Singleton Design Pattern
- We only have a single instance of an object/data, rather than multiple instances
- Example, we only have one database that we're using for the project, so we can reuse the same exact connection to it throughout our project
    - instead of making a new connection every time we want to interact with the database

### DAO Design Pattern
- Data-Access-Object
- We set aside a class (and an interface) whose sole responsibility is interacting with the database
- Usually contain CRUD methods (Create, Read, Update Delete)

## Hiding the url, username, and password
- In IntelliJ, we can create a resources folder
    - Right click main, select new -> directory
    - Click the special option "resources"
    - In this folder, we will store a file containing our log-in information
- Right-click that resources folder and select new->file and name it DbConfig.properties
    - In this file, we will put our database connection configuration:
    ```
    url=jdbc:postgresql://localhost:5432/db_name
    username=postgres
    password=password
    ```
### git ignore file
- We can specify any files/folders that we want git to completely ignore (not push up to the repo)
- ex: src/main/resources/DbConfig.properties
- Even if use git add ., the properties file won't be pushed up

## Create a new database just for this project
- In DBeaver, we can run a command 
```sql
create database pets
```
- Once created, we just have to connect to it
- In DBeaver, I like to create a separate connection
- Database -> New Database Connection, and fill out the new information, just make sure to change the database name
- Whatever database we want to use, we set that as an active data source at the top of DBeaver
- Set up whatever tables you need, make sure the fields match exactly

## Set up our Driver
- can go to mvnrepository.com
- Search for postgresql
- https://mvnrepository.com/artifact/org.postgresql/postgresql
- Click on the latest version and add the dependency to the pom xml

## SQL Injection
- If we use string concatenation to create our SQL queries, then SQL Injection can occur
- For example, if the user types in a command like delete from pet;, then that command could make its way into the database
- Prepared statement

## ResultSet
- whenever we get return value from the database, we get a result set
- like a pointer, initially pointing to an empty set
- then we have to use resultSet.next() to increment
- finally, we use the index to choose which value of the set we are dealing with:
```
-> empty
     1    2        3
-> {id, name, species}
-> {id, name, species}
```

## JDBC API
- [Here](https://www.javatpoint.com/java-jdbc) is a good overview of the JDBC API
- We learned about these interfaces/classes:
    - Driver Manager
    - Simple Statement
    - Prepared Statement
    - Connection
    - ResultSet
