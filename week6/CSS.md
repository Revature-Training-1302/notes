## CSS
- Cascading Style Sheets
- We define the look, style, colors, formatting of our web page
- https://www.w3schools.com/cssref/ check out this page for the different properties, links to more in-depth descriptions

### Different ways to apply CSS stylings
- External - you put stylings in a file with the .css extension
    - import into the HTML file
    - The best practice, because they're in separate files, they can be reused all over the project
- Internal - define your CSS stylings within the HTML document
- Inline - define your stylings right in the tag
    - The worst practice because if you have inline styles, they take the most precedence so they can overwrite changes made in other places
- CSS styles have keys and values
```css
color: red;
font-size: 20px;
```

### CSS Selectors
- * universal selector, will apply to all elements on the page
- element selector, will apply to all elements of that same tag
    - ex, selecting all of the paragraph elements on the page:
    ```css
    p {
        styles
    }
    ```
- class selector, will apply to all elements with that class
    - 
    ```css
    .className {
        styles
    }
    ```
- id selector, will apply to all elements with that id
    - 
    ```css
    #id {
        styles
    }
    ```
- pseudo class selectors, will apply to certain states single colon
    - ex: :hover, :active
- pseudo element selectors, double colons
    - ::first-letter, ::after

### Specifict/Precedence:
1. Inline - highest precedence, it will overwrite every other CSS(external, internal, id, class etc.)
2. ID Selector
3. class, pseudo-class selectors (.header, :hover)
4. element, pseudo-element selectors (p, ::after)

### CSS Box Model
- defines what each element is comprised of and its structure
![Box Model Image](https://www.washington.edu/accesscomputing/webd2/student/unit3/images/boxmodel.gif)
- content - the words or whatever you're trying to display on the page
    - words/sentences
    - numbers
    - data
- padding - the space between the content and the border (if there is a border)
- border - a shape that wraps around the content, it's between the padding and the margin
- margin - space between border and other elements

### Responsive Design
- Designing your application to work and look good on all sized devices
- Media queries to specify different stylings for different device sizes
- It's usually easiest to work on the small screen and then expand outwards
- We can use flex to organize some elements
    - https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox


### Design
#### Colors:
- https://coolors.co/?home, this website helps pick a good color scheme
- Black - luxury, wealth, elegance
- White - cleanliness, neatness
- Grey - emotionless
- Green - nature
- Blue - stability, reliability
- Yellow - joy
- Red - passion, love, danger

#### Contrast:
- Make sure colors aren't too similar, don't want to blend in and not be able to see the text

#### Alignment
- make sure items on the page are aligned
    - flex
    - bootstrap
    - text-align property

#### White Space
- Don't want the web page to feel claustrophobic
- Don't want too much white space between objects, not wasting space on the web page
- Padding, border, margin, height, width
- Number one rule, when in doubt, add padding

#### Scale and Visual Hierarchy
- Making sure that the size of the elements gives some indication of their importance
- Example: making the title of the page the biggest is a good idea
- On the other hand, making a random paragraph really big probably isn't
- Using header tags is useful to achieve this hierarchy

#### Typography
- It's good to pick a font that's not the default
- Usually best to pick 1-3 fonts for the website
- Find cooler fonts at this website: https://fonts.google.com/

### Bootstrap
- Open source framework for desinging responsive web pages
- Makes it really easy to make your websites look more professional
- Components that you can insert into your application and they come with built-in styling and functionality
- To include Bootstrap in your project, go to this link: https://getbootstrap.com/docs/4.6/getting-started/introduction/
    - We include the style tag for ths visuals and the JS scipts for the functionality (launching modals, navbar expand button)
- Once we have bootstrap set up in our project, we can go on their website and search for and include different components
- With each component, we have recurring themes of primary, seconary, success, danger, warning, light, dark, etc.
    - You want to get in the habit of using these corresondingly
        - ex: success button for withdrawing money
        - ex: danger button for deleting
        - ex: primary button for logging in
#### Bootstrap Grid System
- 12-based system
- rows and columns