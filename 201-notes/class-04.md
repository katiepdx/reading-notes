# HTML Chapter 4: Ch.4 “Links” (pp.74-93)
Clear links help users quickly find what they are looking for. 
**Linking to external sites**
Uses absolute urls
    ```html
    <a href="https://www.google.com/" target="_blank" >Google</a>
    ```
Note: can add `target="_blank` to links to open in a separate window.

**Linking to other pages on same sites**
Uses relative urls
    ```html
    <a href="index.html">Home</a>
    <a href="contact-us.html">Contact Us</a>
    ```
    
**Linking to other parts of the same page**
Set an id to another part of the page (ex. `id="top"` or `id="bottom"`)
    ```html
    <a href="#top">Home</a>
    <a href="#bottom">Footer</a>
    ```

### Directory Structures 
Directories have parent, child, grandparent, and grandchildren folders. 
The parent folder contains the index.html which is the homepage for the entire site. Folders inside with other sections of the sites would be the child. Another nested folder would make that the grandchild of the parent folder. 

**Relative urls can be used to link to other pages on the same site.** 
- Same folder: `<a href="reviews.html">Reviews</a>` same folder
- Child folder: `<a href="music/listings.html">Listings</a>` back a folder
- Grandchild folder: `<a href="movies/dvds/reviews.html">Reviews</a>` back two folders
- Parent folder: `<a href="../index.html">Home</a>` 
- Grandparent folder: `<a href="../../index.html">Reviews</a>` 

**Email Links** mailto: 
<a href="mailto:jon@email.com">Email Job</a>


# HTML Chapter 15: “Layout” (pp.358-404)
- Controlling the position of elements 
- Creating the layouts 
- Designing for different sized screens

CSS treats each HTML element as its own box and will *block-level* or *inline* box. If a block-level element has a nested block-level element, the outer one is the *containing/parent* and the inner one is the child. It is common to group elements in other block-level elements (e.g., `<div>`, `<section>`). 

#### Controlling the Position of Elements
Specify the positioning by using the `position` property. There is also the `float` property. When boxes are moved out of normal flow, sometimes they overlap. Overlap can be controlled using the `z-index`. 
- **CSS Positioning Schemes:**
    - **Normal Flow** (`position: static`)
        - Default width will be size of browswer 
        - This is the default behavior of block-level elements. They will appear lower down the page than the previous one.They will not appear next to each other by themselves. 
    - **Relative Positioning** (`position: relative`)

        ```css
        p.example {
        position: relative;
        top: 10px; 
        <!-- spaces it 10px down from the top element -->
        left: 100px; 
        <!-- adds 100px of space to the left of element, moving it right.  -->
        }
        ```

        - This moves the element from the position it would be in in normal flow and moves it to the top, right, bottom, or left of where it WOULD have been. This does not impact the other elements. They continue with the normal flow characteristics. 
    - **Absolute Positioning** (`position: absolute;`)
        - This positions the element in relation to its containing/parent element. It is taking out of the normal flow (default position) and the other surrounding elements ignore it and the space it would have taken up. Absolute positioned elements will move when the user scrolls up or down the page. Acts like its not there.
        - Can use this to create appearance of two columns. Article on left and title on right. 

        ```css
        h1 {
            position: absolute;
            top: 0px;
            left: 500px;
            width: 250px;
        } 

        p {
            width: 450px;
        }
        ```

- **CSS Box Offset:** This tells the browser how far from the top, bottom, left, or right the element should be placed. 
    - **Fixed positioning** (`position: fixed`)
        - This is similar to absolute position, but fixed positioning is relative to the browser window and not the containing/parent element. Elements with a fixed position do not effect surrounding elements positions and do not move when user scrolls. 
        - This can be used to keep heading fixed to the top of the page and have the content scroll behind it. 

        ```css
        h1 {
            position: fixed;
            top: 0px;
            left: 0px;
            padding: 10px;
            margin: 0px;
            width: 100%;
            background-color: lightgrey;
        }

        p.example {
            margin-top: 100px;
        }
        ```

    - **NOTE**: Using *relative, fixed, or absolute* positioning can cause overlapping `z-index` elements. To control which element is on top, use `z-index: number`. Send to front is the highest number. If there are 10 elements, a z-index of 10 would be the front most one. 

    - **Floating Elements** (`float: left/right`) 
        - Takes element out of normal (default) flow and position it to the far left or right or the containing box. It becomes a block-level element and other content around it can flow. Ex. When the first letter or word is 3 lines big and the rest of the article's paragraph flows around it. 
        - This can be used to push a quote off to the right side and have the rest of the content/text flow around it. 
        - This takes the quote out of normal flow and pushes it right. 
            The border top and bottom create the appearance of two bars 
            ```css
            blockquote {
                float: right;
                width: 275px;
                font-size: 130%;
                margin: 0px 0px 10px 10px;
                padding: 10px;
                border-top: 1px solid black;
                border-bottom: 1px solid black;
            }
            ```

#### Floats, floats, float...
Floats an be used to place elements side-by-side. Clearing floats (`clear: left/right/both/none`). Using this means that the element thinks that no other elements in the containing/parent element can touch the left or right or oth sides of it. If it is `none`, that means that elements can touch both sides of it. 

Note: If parent element only has float elements, some browsers think it is 0px tall. Fix: in same CSS element property, add `overflow: auto` and `width: 100%`. 

**Creating Multiple Column Layouts With Floats**
Create a class for each desired block-level section. 

- If you want **two cols**, create two divs with class of "col1of2" (larger) and "col2fo2" (smaller). Use `width`, `float`, and `margin`. 

    ```css
    .col1of2 {
        float: left;
        width: 620px;
        margin: 10px;
    }
    .col2of2 {
        float: left;
        width: 300px;
        margin: 10px;
    }
    ```

- If you want three cols, create three divs with class of "col1of3", "col2of3" and "col3of3". Use `width`, `float`, and `margin`. Each is evenly space and 10px apart and 300px wide. 

    ```css
    .col1of3, .col2of3, .col3of3 {
        float: left;
        width: 300;
        margin: 10px;
    }
    ```

#### Designing
When designing, be aware of screen sizes and different screen resolutions. Higher the resolution, the smaller then text appears. 

- General standard - **create web pages around 960px-1000px wide**. Aim to let the users know what the site is about within the **570px height**. After that, user will need to scroll. 

- **Fixed width layouts**: design doesn't change with browser window size. Measurements usually given in pixels. Good for being exact in measurements but can encounter issues when user zooms in. 
- **Liquid layouts**: stretch and contract with browser window. Tend to use percentages. Good for filling entire space, not needing to scroll with smaller window, and makes font size adjustable with page stretch. Design problems can occur if users window is very narrow or or lines appear long with wide windows. 

#### 960 Grid
**960 grid** used by many designers: continuity, predictable, easy to add on, easy to collaborate as people understand the design. 
    - 960 pixel wide 12 col grid
    - CSS 960.GS framework (www.960.gs)


#### Multiple Style Sheets
`@import url("tables.css")` The `@import` is a modular way to add stylesheets. 
`<link rel="stylesheet" type="text/css" href="css/typography.css" />` Can use `<link/>` to add outside style sheets. 

# JavaScript Chapter 3 (first part): “Functions, Methods, and Objects” (pp.86-99 ONLY)
- Functions: A series of statements that perform a specific task
    - Ask a function to do something is *calling* it. 
    - Info passed to a function are *parameters*. 
    - Getting something back is the *return* value

Declare a function using the `function` keyword.

```javascript
// Declaring the function 
function sayHello() {
    document.write('Hello');
}

// Calling the function 
sayHello()

// Functions with parameters
// declaring 
// width and height are parameters
function getArea(width, height) {
    return width * height;
    // parameters are used like variables
}

// calling 
getArea(3, 5); 

// arguments are variables 
wallWidth = 3;
wallHeight = 5;
getArea(wallWidth, wallHeight);

// Can get single or multiple values out of a function. 
// Single
function calculateArea(width, height) {
    let area = width * height;
    return area;
}

let wallOne = calculateArea(3, 5);
let wallTwo = calculateArea(8, 5);

// Multiple (using array)
function getSize(width, height, depth) {
    let area = width * height;
    let volume = width * height * depth;
    let sizes = [area, volume];
    return sizes; 
}

let areaOne = getSize(3, 2, 3)[0]; // index 0 of sizes array
let volumeOne = getSize(3, 2, 3)[1]; // index 1 of sizes array
```
#### Functions, functions, functions

    ```javascript
    // Functions like `getArea` are named functions. 
    function area(width, height) {
        return width * height;
    }
    let size = area(3, 4)

    // You can also store a function as a variable. **Anonymous function** has no name. 
    let area = function(width, height) {
        return width * height;
    }
    let size = area(3, 4)

    //  Immediately invoked function (IIFE)
    let area = (function() {
        let width = 3;
        let height = 2;
        return width * height;
    }());
    // The second () set of parenthesis tell the interpreter to call the function immediately. 
    ```

IIFEs and anonymous functions are good for running something once within a task. 

#### Scope
Local scope - function level scope. Two different functions can use a variable with the same name without problems because local scope keeps it within the particular function.  
global scope - global variables is stored in memory for as long as page is loaded. Be careful of naming conflicts. 

# 6 Reasons for Pair Programming
Link: https://www.codefellows.org/blog/6-reasons-for-pair-programming/

More people thinking about the same problem is better. Common set up is Driver (typer) and Navigator (speaking). 
- Greater efficiency: produces higher quality code that needs less troubleshooting because both are looking for mistakes. It can take longer to pair program, but in the long run it's more efficient than two people working alone. 
- Engaged collaboration: both highly engaged with code. Keep each other focused. 
- Learning from each other
- Improve social (communication) skills: Working with people with different code styles. Employers like this!
- Job interview readiness: ready for "pair programming" interview step which is between current employee and applicant. 
- Work environment readiness: good skill that helps you jump in and get started with the job