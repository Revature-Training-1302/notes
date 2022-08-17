## Maven
- Build automation tool
    - helps us build our projects
    - include dependencies, external libraries/packages that are necessary to work with (in this case) JDBC


## Installation
- Follow this link: https://maven.apache.org/install.html
- Download link: https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.zip
- For windows, unzip the folder in a place that you'll remember, I used the C drive
- Copy the address of the bin folder and add it to our PATH environment variable
- To test out the installation, type in mvn -v on command prompt

## Set up a Maven Project
### Adding Maven to an existing project
- In IntelliJ, we can right-click the project name in the left side panel and select "Add Framework Support"
- Select Maven and click OK
- You should see a POM XML file appear in your project

### Creating a Maven Project
- In IntelliJ, when we create a new project, there should be an option to create a Maven project
    - With this, we can select an archetype, which is like a template for our project
        - maven-archetype-quickstart - gives us a couple packages and a main file called App, pretty bare-bones
        - maven-archetype-webapp - gives us the bare-bones for a web app


## POM - Project Object Model
- contain information about the project including name, version
- dependencies - libraries that our project uses/depends on
- Make sure to sync the POM file whenever we change it
    - In IntelliJ, there's a blue button that pops up when we change something in the POM, we just have to click that

## Maven Central Repository
- Website where you can search for maven dependencies
- mvnrepository.com
- we can search for dependencies and find the xml code that we can put right in our pom.xml file


## Sample Maven POM:
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>groupId</groupId>
    <artifactId>Pet-Project</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
    </properties>

    <!-- We can write comments in here -->

    <dependencies>

        <!-- https://mvnrepository.com/artifact/org.postgresql/postgresql -->
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <version>42.4.1</version>
        </dependency>


    </dependencies>
    
</project>
```