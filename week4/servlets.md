## Servlet
- a technology that's used to create web applications (creating the server)
- In this case, we'll be building our servlets in Java
- Interfaces/classes: Servlet, GenericServlet, HttpServlet
- Accept requests from client-side (browser, Postman, front-end)

## Advantages
1. Better performance - thread for each request, allow requests to happen concurrently, at the same time
2. Familiar Language - using Java to set up our servlets
3. Robust - JVM manages our servlets, so we don't have to worry about memory leaks, garbage collection
4. Secure - uses Java language

## Interfaces
1. Servlet - we create classes that implement the Servlet and therefore lets us create methods
2. Servlet Request - represents the request that we get from the client
3. ServletConfig - gives us configuration information about the servlet
4. RequestDispatcher - how can we forward/redirect to other paths

## Servlet Methods (5)
### Servlet Lifecycle (3 methods)
1. init - think of it as short for initialize or creating something (this is going to run whenever we create a servlet)
- void init(servletConfig)
2. service - run anytime the servlet receives a request
- void service(ServletRequest, ServletResponse)
3. destroy - whenever the servlet is being destroyed, or the end of the lifecycle

### Non-Lifecycle methods
1. getServletConfig - returns the configuration of the servlet, information about the servlet
2. getServletInfo - returns human-readable information about the servlet

## How to set up Web-App
### Installing Apache Tomcat
- Tomcat is the software that we use to run our servers
- So we have to install it before we can run any web servers that rely on Tomcat
- Head to the [apache tomcat website](https://tomcat.apache.org/download-80.cgi)
- Download under core the zip file and place it in your C drive or anywhere where you can remember where it is
    - Unzip it


### Admin Port

### Next, we create Java web app project
- Luckily, maven makes this super easy for us:
    - Create a new project, and then select the maven archetype "maven-archetype-webapp"
    - Give it a proper name
- After it's built, take a look at what the template is
    - Inside the web-app folder, we have index.jsp as well as another folder called WEB-INF
        - the index.jsp file should have some default text like "Hello World". We can replace that with a custom message
    - Inside the WEB_INF, we see a file called web.xml

### Install Smart Tomcat plugin 
- plugin for intelliJ that connects our Java project to our Tomcat installation and lets us run these web apps
- In intelliJ, we can press ctrl-alt-s to bring up settings
- Then we click on plugins
- Click on marketplace tab, search for Smart Tomcat and click install once you find it
    - may need to restart IntelliJ

### Put it all together:
- Click on "Add Configuration" on the top right
- Click "Add New" or the plus button on the top left
- Find Smart Tomcat in the list of programs
- Give it a name like "Tomcat Configuration" if we want

![Tomcat Configuration](tomcat_config.png)
#### Fields
- Tomcat Server - we want to select the folder where we installed Tomcat
    - should look something like ApaceTomcat/8.5...
- Deployment directory - want to select the webapp folder that was auto-generated by maven
- Context Patj - we can leave it as a single / or leave te default (this will preface all of our requests)
- Server port - 8080, leave it the default
- Admin port - leave as default

### Add a Servlet
- First, we have to add a Java directory
    - Right-click main -> new -> directory -> java
- Make some packages and create a class called MyServlet
- Make the class implement Servlet interface so we can fill out those 5 methods (init, service, destroy, config, info)
- Right-click and click context actions, and implement methods
- After we create the servlet class, we have to configure it in the deployment descriptor (web.xml) to make sure we can access it from our address


## Deployment Descriptor
- web.xml
- we set up our servlets and connect them to different url patterns
- In a nutshell, we say something like "If we go to localhost:8080/pet, then we run the pet servlet class"
- For every servlet class we set up, we have to do something like this in the web.xml
```xml
<!-- in the servlet tag, we map the class to a name -->
  <servlet>
    <servlet-name>first</servlet-name>
    <servlet-class>com.revature.FirstServlet</servlet-class>
  </servlet>
  <!-- In the servlet mapping tag, we connect the servlet name with a url-pattern -->
  <servlet-mapping>
    <!-- here it is very important that we match what set as the name in the servlet tag -->
    <servlet-name>first</servlet-name>
    <url-pattern>/first</url-pattern>
  </servlet-mapping>
  ```
- In this case, going to localhost:8080/.../first, we should invoke the servlet in the class com.revature.FirstServlet

## Resources
- https://www.tutorialspoint.com/servlets/servlets_overview.htm