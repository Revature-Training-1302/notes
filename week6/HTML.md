## HTML
- HyperText Markup Language
- NOT a programming language
- This is the language that we use to define a "skeleton" of our front-end page
- We define which elements are on the page
- Leaving styling and logic to CSS and JS

### Terms/Definitions
- Element - something on a web page
    - ex: button, title, paragraph of text, image
- Tag - in the HTML code, we use tags to define elements
    - opening/closing tag: <div>child content</div>
    - self-closing tag: <img src = "url.com"/>
- Attribute - property of an element
    - ex: class, name, id, width, height
    - <div class = "login"></div>
- DOM - Document Object Model
    - represents the conent of the page, elements
    - underlying structure is a tree
    - ![DOM example image](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png)


### Structure of an HTML page:
- root html tag which contains head and body
- Head - metadata about the project, title, stylings, scripts
- Body - content goes in the body, we also see scripts usually
- In VScode
    - Type "html:5" and hit tab
    - Type out an ! and hit tab

### How to View HTML page
- Find the file in your file directory and open in browser
    - requires us to refresh every time we make a change
- The more responsive way is to install an extension in Visual Studio Code called Live Server
    - To install this, go to the extensions menu in VScode, look up Live Servet
    - Click on the extension and "Install"
    - Once it's installed, we can right-click an HTML file and select "Open with Live Server"
    - Notice the address bar, example: "http://127.0.0.1:5500/hello.html"
    - to change port number, click the Gear icon next to the extension and go down to port number, you will have to edit the settings.json

### Elements
- Headers
    - h1- h6, number indicates precedence, 1 being the highest
- Paragraph tag
    - p - used for text
    - VScode tip: type "lorem" and enter to get some dummy text
- Div tag
    - div - used to divide sections of the web page
    - almost like containers for different pieces of your web page
- Lists 
    - Unordered Lists
        - doesn't have numbers
    - Ordered Lists
        - does have numbers/letters
    - Used to store a list of values/data
    - Tags: ol (ordered list), ul (unordered list), and li (list item)
- Anchor tag
    - used to click links and redirect to a different page
    - can do public urls like google.com or the path to a local file
    - a tag with href attribute
        - ex: <a href = "http://google.com">Click me</a>
- Images and Videos
    - used to put media on web page
    - src attribute contains the link/location to the resource

### Inline vs Block elements
- Inline means that 2 or more elements can share horizontal space
- Block elements start a new line every time
- Examples of inline: a tags, image tags, span tags
- Examples of block: headers, paragraph, divs
- We can use the break tag to start a new line regardless of whether it's inline or block

### Tables
- used to store multi-field, multi-dimensional information
- tags:
    - table - represents the entire table
    - tbody - represents the table body
    - thead - represents the table head
    - tr - table row
    - td - table data, an indidual cell in the table
    - th - header item

### Forms
- tags:
    - form - root element of the entire form
        - onSubmit - dictate what happens when we submit the form
    - input - any element that takes in data from the user
        - type attribute can be "text", "email", "password", "submit", "radio", "checkbox"
            - determine what type of input is gathered
        - name - indicates the name of the input (username, password, birthday)
        - value - the value of the data itself ("admin", "password123", ...)
        - placeholder - puts a placeholder value in the text box, but doesn't actually affect the value
        - required - indicates that the input is required
        - checked - for checkboxes, indicates that the box is initially checked
    - button - click it to make something happen
        - the "something" is whatever we define in our JavaScript
    - label - gives labels or descriptions of what the inputs do, what kind of data they're taking in
        - for - give the id that corresponds to the related element
    - textarea - kind of like a textbox but allows for a lot more space so is therefore useful for more characters
    - select - gives a drop down of different values
    - option tags within the select give you the different options
- different types of inputs:
    - radio - only select at most one
    - password - hide the data
    - check box - select 0 or more
- If we add the "required" attribute to any of our inputs, we will need a value in order to submit the form, otherwise, we'll get the message that the field is required (form validation)
- We can use the names as keys and values as values
    - <input name = "username" value = "admin"> means that for the field "username" the value is "admin"


### Semantic Tags
- Introduced in HTML 5
- They're used to organize your web pages
- Normally on a web page, we have a header, footer, navbar, side panel, main content, etc.
- Semantic Tags:
    - header
    - footer
    - aside
    - article
    - section
    - nav
- https://www.w3schools.com/html/html5_semantic_elements.asp 