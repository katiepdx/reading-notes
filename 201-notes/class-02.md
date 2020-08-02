# HTML Chapter 2 Text (p. 40-61)
- Headings and paragraphs
- Bold, italic, emphasis
- Structural and semantic markup 

Tags (markup) let browsers know what to do and display the correct structure. There are two types of structure: 1) **Structural markup** (elements describe both heads and paragraphs) 2) **Semantic markup** (provides extra info like `<em>` for emphasis.)

### Structural Markup 
- Headings - has six levels of headings 
    - `<h1></h1>` - Biggest - Used for titles 
    - `<h2></h2>` - Second biggest - Used for subtitles 
    - `<h3></h3>` - Smaller...
    - `<h4></h4>` - Smaller... 
    - `<h5></h5>` - Even smaller... 
    - `<h6></h6>` - Smallest heading
    Examples: 
    <h1>h1</h1>
    <h2>h2</h2>
    <h3>h3</h3>
    <h4>h4</h4>
    <h5>h5</h5>
    <h6>h6</h6>

- Paragraphs `<p></p>`
    - New paragraphs are on next line. 
- **Bold** `<b></b>` & *Italics* `<i></i>`
- <sup>Superscript</sup> `<sup></sup>` & <sub>Subscript</sub> `<sub></sub>`
- White Space - makes things easier to read sometimes. Browser *white space collapse*, meaning that it treats one or more spaces as one space and a return as a space as well. 
- Line breaks `<br/>` 
    ```html 
    This will break <br/>
    the line.  
    ```

    Output: <br/>
    This will break <br/>
    the line.

-Horizontal rules `<hr/>` - adds a horizontal line

### Visual Editors 
Visual editors look a lot like work processors but features vary. Mac visual editor is TextEdit and PCs is Notepad. You can use *code views* to see a preview of your code while you're working. 

### Semantic Markup 
These elements don't impact the structure of the page, but add additional information. For example, `<em>` and `<blockquote>` change the appears slightly but they also the voice of screen readers. The voice may change when the screen reader sees these types of element tags. 

**Strong vs Emphasis**
- `<strong></strong>` - used to show strong importance (ex., beware). Browsers show this as bold. 
- `<em></em>` - shows importance but in italics. 

**Quotations**
- `<blockquote>` - used for paragraph quotes
- `<q></q>` - inline quotes. 

**Abbreviations & Acronyms**
When the abbreviation <abbr title="Professor">Prof</abbr> is hovered over, the full word will appear.

```html
<abbr title="Professor">Prof</abbr>
```

**Citations & Definitions**
Cite turns the text inside italics.

```html 
<cite>test</cite>
```
<cite>test</cite>

Used when it's the first time using an academic term. Appearance doesn't change in Safari or Chrome.

```html
<dfn>Word goes here.</dnf>
```

**Author Detail**
- `<address></address>` contact info can go here like phone numbers and email address. 

**Changes to Content**
- `<ins></ins>` used to show content that has been <ins>inserted</ins> into a document. Shows as underline. 
- `<del></del>` show <del>removed</del>. Shows as strike through. 
- `<s></s>` shows info that's <s>not</s> longer relevant. Shows as strike through. 


# HTML Chapter 10 Introducing CSS (p. 226-245)
- What CSS does
- How CSS works
- Rules, properties, and values

CSS makes webpages more attractive. Think of invisible boxes around HTML page that CSS can change and make pretty. Remember there are *block-line* (`<p></p>`)and *inline* elements (`<i></i>`). 

### Styles 
- **Boxes** have width, height, borders (colors, width, styles), background colors, etc.
- **Text** has typeface, size, color, italics, etc. 
- **Specific** can contain elements using styles like lists, tables, and forms. 

A **CSS rule** has a *selector(s)* and a *declaration(s)*. The selectors tell us which elements we are wanting to add the declaration style to. Declarations have a property and value (ex. Property is color: value is yellow;). 

```css
h1, h2, p {
    font-family: Arial;
    color: yellow;
}
```

### External CSS
Advantages: External CSS sheets means all the webpages can share the same styles. You can change a style in one sheet rather than on every single page if it's internal CSS. 

Before using CSS, you need to link your file-name.css file to your file-name.html file using the `<link/>`

```html
<link href="path to file.css" type="text/css" ref="stylesheet"/>
```

### Internal CSS
To use internal CSS, add a `<style type="text/css"></style>` tag in the head with the selectors and decorations styled as normal. 

```css
<head>
    <style type="text/css">
        h1, h2, p {
        font-family: Arial;
        color: yellow;
        }
</head>
```

### CSS Selectors 
CSS selectors are case sensitive and must match the attribute values exactly. 

| Selector                  | Meaning                                                                                                                                                                                    | Example            |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| Universal Selector        | applies to all elements on the page                                                                                                                                                        | * {}               |
| Type Selector             | Matches element names                                                                                                                                                                      | h1, h2 {}          |
| Class Selector            | Matches a class name of note p.note targets p elements with class of note                                                                                                                  | .note {} p.note {} |
| Id Selector               | matches id                                                                                                                                                                                 | #intros {}         |
| Child Selector            | matches an element that is a direct child of another This targets all `<a>` elements that are direct children of `<li>`                                                                    | li>a {}            |
| Descendant Selector       | targets element that is a descendent of another element (not just child) This targets any `<a>` elements that are inside a `<p>` element... ...even if other elements are nested between.  | p a {}             |
| Adjacent Sibling Selector | targets next sibling Targets first `<p>` after any `<h1>` but NOT the `<p>` elements.                                                                                                      | h1+p {}            |
| General Sibling Selector  | Targets `<h1>` siblings of `<p>` but doesn't need to be directly preceding                                                                                                                 | h1~p {}            |

### How CSS Rules Cascade
- ***Last rule** will apply* even if there is another rule applying to that element earlier int he page. 
- Specificity - more specific rules take priority. 
    - h1 is more specific than *
    - p b wins over p
    - p# wins over p
- Important - `!important` means this is the most important and takes priority regardless. 

### Inheritance 
Can have child elements inhert parent elements stylings by setting the declaration's property (color) value (yellow) as `inherit;` . 


# JavaScript Chapter 2 Basic JavaScript Instructions (p. 53-84)

### Statements
A script's individual steps is a **statement**. Note JavaScript is case sensitive. Each statement starts on new line. Organized into code blocks. The statement is `greeting = 'Good morning';` and `greeting = 'Welcome!';`.

```javascript 
if (hourNow > 18) {
    greeting = 'Good morning';
} else {
    greeting = 'Welcome!';
}
document.write(greeting);
```

### Comments 
Used to explain what the code does. Makes it easier to read. 
 - Multi-line comment `/* Commented out*/`
- Single line comment `// Commented out `

### What's a Variable?
Temporary stored info goes into a variable (remembered). The data stored can vary each time a script runs. `area = width x height`. The weight and height can change each time. Can store a string, number, boolean. 
- Declaring a variable.
    - Older way: `var`
    - `let` (variable value can change) or `const` (variable value can't change)

    ```javascript 
    let quantity; // Declaring. variable keyword and variable name.
    quantity = 3; // Variable name =  variable value

    //Shorthand
    var price, quantity, total;
    price = 5;
    quantity = 14;
    total = price * quantity;

    var price = 5, quantity = 14;
    var total = price * quantity;

    ```

Can change the value of a variable later in the same script. 

### Data Types 
- Numeric `0.8`
- String `'Hi, Katie'` 
    - When quoting inside a string, use double quotes for the string and the quote in single quotes or `\` before quotes. 
- Boolean `true` or `false` like on/off.

### Variable Names Rules:
- Can't start with a number
- Can only have letters, $ or _
- can't be keywords or reserved words
- Case sensitive 
- Should be descriptive of stored value
- useCamelCaseIfWordIsMoreThanTwoWords

### Arrays
Stores a list of values separated by commas that are related to one another. 

```javascript
// Array literal
colors = ['red', 'blue', 'yellow'];

// Array index starts at 0. Red is 0. Blue is 1. Yellow is 2.

// Access an item in array 
color[2];

// Length of array
colors.length; 

// Update value in array - change blue to green.
color[1] = 'green';

colors = ['red', 
          'blue', 
          'yellow'];

// Array constructors Array()
var colors = new Array ('red', 
          'blue', 
          'yellow');
```
## More JS Concepts

```javascript 
// EXPRESSIONS
// Assign value 
var color = 'green';

//Expressions with 2+ values and return a single value
var area = 3 * 2; // value of area is 6

// OPERATORS 
// Assignment operators 
color = 'purple';

// Arithmetic Operators (+, -, /, *, ++ adds one to current number, -- subs one from current number, % returns remainder of divided numbers)
area = 3 * 2;


// String Operators 
greeting = 'Hi ' + 'Katie';
myFavNum = '7'; // 7 is a string because it's in quotes.

// Comparison Operators 
buy = 3 > 5; // value of buy is false

// Logical Operators (&& both must be true) ( || only one needs to be true)
buy = (5 >3 ) && (2 < 4);
```

# JavaScript 4 Decisions and Loops (p. 145-162) - only up to switch statements section
Browser can run different code depending on situation. Creating and controlling the flow of data is important so scripts can handle different situations. 
- **Evaluations**: analyze values in scripts to determine if they match expected results
- **Decisions**: use the results of evaluations to decide which path your script should take.
- **Loops**: Repeats a set of steps again and again. 

Flowcharts with statements (ex. is score greater than x) and booleans (true false) help with planning paths.  

### Evaluating Conditions and Conditional Statements 
Decisions: 
1. An expression is evaluated and returns a value
1. a conditional statement says what to do in a given situation. 

```javascript
if (condition score > 50) {
    //do this
    document.write('You passed');
} else {
    //do this
    document.write('try again');
}

// COMPARISON OPERATORS for evaluating conditions

== // equal to
!= // not equal to

=== // strict equal 
'3' === 3 returns false
!== // strict not equal to
'3' === 3 returns true

> // greater than 
>= // greater than or equal to
<  // less than 
<= // less than or equal to
```

```javascript
// STRUCTURING COMPARISONS with 2 operands (score and pass) and comparison operator
var pass = 50;
var score = 60;

(score >= pass); 

//declare the four variables here 
((score1 + score2) > (highScore1 + highScore2));
```

```javascript 
// LOGICAL OPERATORS 
&& // logical and: both must be true to return true
|| // logical or: only one needs to be true to return true 
! // logical not: inverts boolean value 
!(2 < 1) // returns true. 2 is not less than 1 so...false, then add NOT so true!
```

```javascript 
// If Statements - if statement is true, then run what's in the block. 
if (score >= 50) {
    congratulate();
}

// If...Else... - if if is false, then/else do this. 
if (score >= 50) {
    congratulate();
} else {
    encourage();
}
```

# Additional Resources - https://chris.beams.io/posts/git-commit/

# How to write a git commit message
- Can have a **subject and body**, but not all commits use a body. Separate subject and body with a blank line.

    ```git
    git commit -m"Fix typo in introduction to user guide"

    // Note: This needs to have a body explaining more. To add a body, you will need to type message in text editor first. 
    ```

- Subject line: Give simple and detailed messages logging what changes were made.
- Subject Line RULES 
    - 50 characters or less
    - Capitalize subject line
    - Do NOT end it with a period
    - Use imperative mood in subject line like 'Clean your room)' or 'Release version 1.0.0'
    - Subject should be able to finish the sentence "If applied, this commit will *subject line goes here*" (ex. If applied, this commit will release version 1.0.0).

- Commit body
    - Wrap the body at 72 characters (can use text wrap for this)
    - Body *should explain the what and why* vs. how

```git 
EXAMPLE OF GOOD BODY COMMIT FROM BITCOIN'S GITHUB

commit eb0b56b19017ab5c16c745e6da39c53126924ed6
Author: Pieter Wuille <pieter.wuille@gmail.com>
Date:   Fri Aug 1 22:57:55 2014 +0200

   Simplify serialize.h's exception handling

   Remove the 'state' and 'exceptmask' from serialize.h's stream
   implementations, as well as related methods.

   As exceptmask always included 'failbit', and setstate was always
   called with bits = failbit, all it did was immediately raise an
   exception. Get rid of those variables, and replace the setstate
   with direct exception throwing (which also removes some dead
   code).

   As a result, good() is never reached after a failure (there are
   only 2 calls, one of which is in tests), and can just be replaced
   by !eof().

   fail(), clear(n) and exceptions() are just never called. Delete
   them.
```
- Useful for referring back on them later down the road. 
- Follow the programming language's commit conventions and styles. 
- Use the command line



