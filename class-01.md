# Class 01 Reading Notes
# HTML Book & CSS by Jon Duckett 
# Introduction (P. 2-11) 
Access the web: 
- Browsers 
- Web Servers
- Devices (desktop computers, laptop, etc.)
- Screen Readers

All websites use HTML (HyperTextMarkupLanguage) and CSS (Cascade Styling Sheets). Current versions are HTML5 and CSS3. 

Visiting a site: 
- webserver can be anywhere in the world. 
- to access web servers location, browser first connects to a DNS (Domain Name System) server. 

# HTML Chapter 1 "Structure" (P. 12-39)

## Understanding Structure 
Website structure is similar to that of a newspaper and other documents (e.g., heading, text, images, etc.). 

HTML has **elements** that usually have an opening (e.g., `<h1>`) and a closing **tag** `</h1>` with some exceptions. Tags are like containers. 

**Attributes** tell us more about elements. They are made up of a *name* (lang) and *value* (en-us). Attributes are in the opening tags.  
```html 
<p lang="en-us"> English paragraph</p> 
```

**Elements** 
```html 
<body></body>
<head></head>
<title></title>
```
Templates vary depending on need. Ex. e-commerce might have more (product) boxes. 

**Creating**: Can use TextEdit on Mac or another code editor application (e.g., VSCode). There are also content management systems (CMS).  

Can view a pages code by right clicking and inspecting or using view source.

# HTML Chapter 8 Extra Markup (p. 176-199)- Specifying different versions of HTML

- Identifying and grouping elements
- Comments, meta information and iframes

### Evolution of HTML 
- HTML4 released in 1997
- XHTML 1.0 released in 2000
- HTML5 now (should work on all browsers now)
    - `<!DOCTYPE html>` used for HTML5

* **Comments** in HTML `<!-- This is commented out text --> `
    - Note, these are visible int he source code of your page even though they are visible in your browser.
- **id** attribute (unique) -  `<p id="quote">Text</p>` 
- **class** attributes (reusable) 

    ```html
    <p class="countries">China</p>
    <p class="countries">USA</p>
    ``` 

- **Block elements** are started on a new line (e.g., `<h1>, <p>, <ul>, and <li>`).
- **Inline elements** always continue on the same line (e.g., `<a>, <b>, <em>, and <img>`).
- **Grouping text** and elements in a **block** level box `<div></div>` 
- **Grouping text** and elements in an **inline** level `<span></span>` 
- **Iframes** are a little window into another page on your page. Good for maps and media.

    ```html
    <iframe width="450" height="350" src="url here" frameborder="0" scrolling="yes/no/auto"></iframe>
    ```

## Information About Pages
- `<meta>` (no closing tag) goes inside the `<head>`. Not visible to users. Useful for search engines to know about the page. 
    - description - usually 155 characters about page. 
    - keywords - list of words user might search for separated by commas. 
    - robots - *noindex* if page shouldn't be added to results. *nofollow* if search engine should add page but not any pages that it links to. 
    - author
    - pragma - stops browser from caching the page (saving it locally so it loads faster).
    - expires - tells when page should expire (no longer be cached). Date must be like this: 04 Apr 2014 23:59:59 GMT

- Escape Characters (e.g. `&copy;` for copyright symbol. &copy; ). Full list online. 

# HTML Chapter 17 Extra Markup (p. 428-451)
- HTML5 layout elements
- How old browsers understand new elements 
- Styling HTML5 layout elements with CSS

Traditional HTML layouts used many divs with ids of header, nav, etc. to divide up the page. HTML5 has element names like `<header>, <nav>`, etc. and doesn't rely on divs and ids. This makes code easier to read. 

## HTML5 Elements
- `<header></header>` Top of page. Nav usually goes here. 
   
    ```html 
        <nav>
            <ul>
                <li>Nav links go here</li>
                <li>Nav links go here</li>
            </ul>
        </nav>
    ```  
    
- `<footer></footer>` Bottom of page. Contact or copyrights can go here. 
- `<article></article>` Good for stand alone sections like an article, blog, comment, etc. Can be nested. 
- `<aside></aside>` 1. If in an article, it's used to add non-essential information. 2. outside of article, it's used to link to other parts of page or for a search box, or for recent tweets from author, etc. 
- `<section></section>` Groups related content together and usually has it's own heading. 
- `<hgroup></hgroup>` Heading groups are used for headings like title and subtitle. 
- `<figure></figure>` and `<figcaption></figcaption>` used for images, videos, graphs, diagrams, code samples, etc. Note: figures should contain a figcaption. 
- `<div></div>` Divs are section elements are used to group elements together when other suitable named elements are not suitable. 
- `<a href="intro.html">Block of code goes here. </a>` Turns entire block of code into a link.

NOTE: Older browsers that don't use HTML5 treat those elements as inline. Include CSS with HTML5 elements and set display: block; to solve this problem. 

# HTML Chapter 18 Process & Design (p. 452-475)
- How to approach building a site 
- Understanding your audience and their needs
- How to present information visitors want to see. 

## Building Professional and Attractive Sites 
 1. Who is the site for?
    - Websites should be designed for your target audience. 
    - Questions to think about your target audience 
        - **Individuals** -- Age range, Gender, Countries visitors live in, urban or rural areas, income, education, marital status, occupation, working hours, how often they use the web, device used to access web?  
        - **Companies** -- size of company or department, position of people in the company who visit the site, visits using the site for themselves or for someone else, what's the budget?

 1. Think about why people are visiting the site. What are their *motivations* (for entertainment or to achieve a task, essential or luxury) and *goals* (general info, are they already familiar with topic or product, do they need to contact us)? 

 1. Now, figure out what info visitors need to achieve their goals quickly and effectively. Provide info relevant to the visitor. 
    - Example key info: Think about if the visitor is already familiar with topic or needs an intro. 

1. How often does the site need to be updated? News needs constant updating. Sometimes products can stay if inventory is in stock. 

1. Site maps - a diagram of website's page structure. Card sorting - placing pages on index cards and sorting them into groups. 

1. Make wireframes - these are simple sketches of key information that goes on site page and idea of sizing. Good to show client the design so everyone is on the same page and less issues arise after site has been built. Wireframes do not include color scheme, font styles, backgrounds, or images. Just key info like logo, nav names, headings, main bodies of text, user logins, etc. 

1. Designing to get your message across
 - Organize and prioritize information by **grouping**. Grouping _examples_ on page 469 in book. 
    - Nav bars should concise, clear, consistent in design, and selective (only contain necessary sections). User should know which tab they are on through interactiveness (e.g., link changes in appearance when user hovers over it and clicks it)
 - Keep **similar visual styles** for similar elements. 
 - Have a **visual hierarchy**. 
    - Size, color, style to make info pop. Images create high visual contrast and can attract the eye first. 

# JavaScript & JQuery by Jon Duckett 

# Introduction (p. 4-11)
JavaScript makes webpages more interactive by accessing content, modifying content, adding program rules (like a calculator, animation, etc.), and by reacting to events (e.g., button pressed, info added to form, etc.)

- Javascript...
    1. Access the content of the page
    1. Modify the content of the page
    1. Program rules or instructions the browser can follow.
    1. React to events triggered by the user or browser. 

Examples: Display slide shows, check if forms have been filled in correctly, reload part of a page, filter data. 


# Chapter 1 The ABC of Programming (p. 11-52)
## 1/a What is a script and how do I get one?
A script is series of instructions a computer uses to reach a goal just like humans follow cooking recipes, handbooks, and manuals. They are step-by-step and can be run in different sections of code/the page and response to the situation appropriately. 

### Writing a Script 
1. State the end goal and the steps needed to achieve it
1. Start big and break the goal into smaller steps. 
    - Define goal
    - Design the script
    This can be done using a flowchart with yes/no options. Ex. Check each room. Does it need cleaning? No. Skip it and go to the next room. If yes, clean it (using these steps...step 1, step 2, etc.). Go to next room.
    - Code the script
    *Vocabulary*: Words computers understand. 
    *Syntax*: grammar
    *Programmatically* code it in a way the computer understands. 

## 1/b How do computers fit in with the world around them?
Computers create models of the world assign data. 

**Objects (things)**
- Object types (car, hotel, etc.) can have properties, events, and methods. 

**Properties (characteristics)**
- The object type car can have characteristics like color, model, size, etc. using *name/value* pairs (color: blue). 

**Events (interactions that change the object's properties)**
- Event Examples: The car accelerator makes the car go faster. Brake makes it slow down. 
- Events trigger a specific part section of code to run. 

**Methods** (what people need to do with the objects/retrieve and update values of objects properties)
- Car Method Example: changeSpeed() increases or decreases the value of the changeSpeed property. 
Hotel example: makeBooking() method increases the value of bookings in bookings property. 

**These are relate to one another.**

Car Example:
Object type: car
1. Event accelerate 
1. Method changeSpeed()
1. Properties currentSpeed 45 mph

**HTML Webpages as an object**
- Object type Document
- Properties URL, lastModified, title
- Event load, click, key press
- Method write() adds new content to document a.k.a webpage and getElementById()

**Browsers and Web Pages**
1. Receives HTML code
1. Create a model of page and stores it in memory
1. Uses a rendering engine to show the page on the screen. This is the part we see. 

All major browsers can use Javascript 

## 1/c How do I write a script for a web page?
HTML, CSS, and Javascript fit together
- HTML (index.html) - content
- CSS (style.css) - presentation layer. Makes site pretty. 
- Javascript (index.js) - behavior layer

#### Creating a script
1. Create .js file
1. Link JS file to HTML page where you want to script using the following. JS runs where it is found in the html
    ```html 
    <script src="file-name.js"></script>
    ```
1. document represents the entire web page. write() method allows new content...whatever is between the single quotes between the ()... to be added to the web page. 
    ```javascript
    document.write('Good Afternoon!');
    ```