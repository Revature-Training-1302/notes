## Node
- We've seen Node being used as a run-time environment, letting us run JS files outside of a browser
    - node hello.js
- Node is also a package manager
    - NPM - Node Package Manager
    - We can use Node to install things, and manage external packages in our projects

## Angular
- A Framework used to create front-end, Single-Page-Applications
- Angular vs AngularJS
    - AngularJS is the older version of Angular (used JavaScript instead of TypeScript)
    - Versions of Angular:
        - AngularJS or Angular 1 - October 20, 2010
        - Angular 2 - September 14, 2016
        - Angular 4 - March 23, 2017
        - Angular 5 - November 1, 2017
        - Angular 6 - May 4th, 2018
        - Angular 7 - October 18, 2018
        - Angular 8 - May 28, 2019
        - Angular 9 - February 6, 2020
    - With Angular 4+, component based
        - Ex: component for adding a pet, viewing a pet, login, register
        - AngularJS used MVC architecture
    - Angular supports TypeScript whereas AngularJS supports JavaScript

### SPA (Single-Page Application)
- We can still have multiple pages/locations on our website
- The HTML, CSS, and JS code is loaded with one page load, no refreshing
- Dynamically sets what's on the page, without having to navigate to another location
- We use routing to achieve multiple "pages"
- Faster and more responsive than a multi-page application
- Examples of SPA's: Gmail, Google Maps, Facebook, Twitter, Trello

### How to install Angular
- npm install -g @angular/cli
    - install the Angular command line interface, let us create Angular projects and run them
    - To test installation, ng version

### How to create Angular Project:
- ng new <name>
    - ex: ```ng new pet-app``` - create a starter Angular application
    - When prompted if we want to add routing, enter y for yes
    - Select "CSS" for stylesheet format
    - Wait for project to build

### Structure of an Angular application
- src folder will contain our source code
- Within the src folder, we'll have the app folder which will contain all of our components
    - index.html - root page of our entire project
    - App Folder
        - contain all of our components and services
        - 
- Outside of the src folder:
    - package.json - tell us which packages/dependencies we've installed
        - Our package.json tells node which packages to install when we do npm install
        - But, if we're starting a new project, we'll need to manually install some packages (http, FormsModule)
    - .gitignore, very important because the node modules are very big so we wouldn't want to push those to a repo
    - node modules - a large amount of folders that contain the dependencies that our project uses
    - ReadMe - contains information about our pet application
    - tsconfig.json - contain configuration information about typescript (version, etc.)

### How to run an Angular project
- ```ng serve -o```
    - -o will open the project in browser automatically
    - Make sure we are in the Angular project

### How to create Components/Services
- Components - ng generate component instructions
    - Make sure we are in the Angular app

### Angular Components
- 4 parts:
    - app.component.ts - set up fields, methods
    - app.component.html - the visuals, an html page that shows up whenever we render this component
    - app.component.css - where we put our stylings for the component
    - app.component.spec.ts - where we set up testing for that component

### Lifecycle methods
- ngOnInit() - run whenever we initialize the component, we usually set up different properties
- ngOnDestroy() - invoked when component is destroyed
- constructor - dependency injection
- https://angular.io/guide/lifecycle-hooks

### App Module File
- @NgModule - takes some metadata to launch the app:
    - declarations - components, directives, and pipes that belong to this module
    - imports - list of modules that are used by the component templates (ex: BrowserModule)
    - providers - list of service providers
    - bootstrap - contains the root componet of the application
- main.ts is the entry point of our app
- we pass app.module.ts as an argument
- Angular anylzes this file and knows about app-root, allowing it to render in index.html

### Data-Binding
- The idea of binding values in our TypeScript files/code to the visual web page that's illustrated by our HTML pages

#### One-Way Binding
- Taking our data that we defined in our .ts file and displaying it on the page
- We don't actually listen for any changes made to the data on the web page
- String Interpolation
    - ```{{ ts code }}``` this will be rendered on the page
- Property Binding - using the string interpolation to render an attribute (such as a link)
- Event Binding - binding some event on the web page (ex: button click) to some method/function in our TS code

#### Two-Way Binding
- data flows from our ts to html and then back
    - some sort of form where we can alter the data and those changes are reflected in our code
    - We use the ngModel to map our input fields to our TS object
    - We need to include the FormsModule in order to use the ngModel

### Structural Directives
- Use to change/manipulate the DOM
#### ngIf
- choose whether to render an element based on some boolean condition
- if the condition evaluates to true, the element will be shown
- otherwise it will be hidden

#### ngFor
- repeat the same element for items in an array

### Attribute Directives
- ngClass - used to dynamically set the class of an element, based on some expression
- ngStyle - used to dynamically set the style of an element

### Services
- Just like components, we can create services in Angular
- ng generate service <service-name>
- contain business logic, make http requests to the back-end
- We can achieve dependency injection by placing the service class in the constructor of our component
    - This will allow us to use those methods within our component

### Routing
- Setting up our application so that a particular route in the address bar will route us to a particular component
    - ex: localhost:4200/pets -> that would show us all pets:
    - ex: localhost:4200/pet/3 -> pet with id 3
    - ex: localhost:4200/instructions -> show us the instructions:
- Define our routes in app.module.ts
    - an array that maps path to a component

#### Router Guards
- controlling who has access to certain pages
- Four different interfaces:
    - CanActivate - decides if a route can be activated
        - for example, make sure user is logged in before they can view adopted pets
    - CanActivateChild - decides if children of a route can be activated
    - CanLoad - decides if a route can be loaded
    - CanDeactivate - decides if user can leave a route
- ng generate guard auth
- https://stackoverflow.com/questions/42026045/difference-between-angulars-canload-and-canactivate

### HTTP Client
- In our service, we use the HTTPClient to send requests (POST, PUT, GET, DELETE, PATCH)
- These functions return observables
- We have to import the HTTPClient in our imports array
- ```npm install http```

### CORS
- Access to XMLHttpRequest at 'http://localhost:8080/pets' from origin 'http://localhost:4200' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
- To fix this, on our controller, we add an annotation to allow 

### Pipes
- A way to transform data
- https://angular.io/guide/pipes
- Make your own pipe
    - ng generate pipe pipe-name
    - fill out the tranform function to return a modified value
    - set the name of the pipe using the Pipe decorator

### Webpack
- Have a lot of script files in our project
- Loading these files separately is inefficient
- We use Webpack to bundle a group of JS modules and merge them into a single file which can then be loaded by the browser
- packages all modules in our application and serves it to the browser

### Event Emitters
- Passing events/data between components
- We've seen data/events passed aroung using services
- We also have access to 2 decorators that allow us to pass data/events around
    - @Input - specify what data we're taking in, use property binding to pass in some data from parent to child
    - @Output - specify what data we're sending out or what event we're emitting, use event binding to pass a callback function in to deal with the event that we're emitting

### Testing

#### Jasmine
- Testing framework
    - Comes with methods that we write the tests in
    - Write our Jasmine tests in the spec.ts files in our Angular project

#### Karma
- Take our tests and run them on the browser
    - Gives us feedback on the tests


