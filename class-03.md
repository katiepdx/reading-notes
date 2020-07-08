From the Duckett HTML book:
# HTML Chapter 3: “Lists” (pp.62-73)
Three Types of Lists: 
- Numbered lists
- Bullet lists
- Definition lists

### Ordered Lists (1, 2, 3, etc.)
```html 
    <ol>
        <li> Number 1</li>
        <li> Number 2</li>
        <li> Number 3</li>
    </ol>
```

### Unordered Lists (bullets)
```html 
    <ul>
        <li> Bulleted </li>
        <li> Bulleted </li>
        <li> Bulleted </li>
    </ul>
```

### Definition Lists (word/definition)
Note: definitions are indented in. 
```html 
    <dl>
        <dt> Word </dt>
        <dd> Definition goes here </dd>
        <dt> Word </dt>
        <dd> Definition goes here </dd>
        <dt> Word </dt>
        <dd> Definition goes here </dd>
    </dl>
```
### Nested Lists (bullet point, no fill bullet point)
```html 
    <ul>
        <li> Bulleted </li>
            <ul>
                <li> White bullet points </li>
                <li> White bullet points  </li>
            </ul>
    </ul>
```
Nested List Example:
- Example
- Example 
    - example 


# HTML Chapter 13: “Boxes” (pp.300-329)
- Controlling size of boxes 
- Box model and borders, margin, and padding
- Displaying and hiding boxes

### Box Dimensions 
Just big enough to hold content. Can size the `width` and `height` using pixels, percentages, ems.

- Limit the width or height using: `min-width`, `max-width`, `min-height`, and `max-height`. These are the smallest or largest dimensions it can be.

- Overflow content: 
    - use `overflow: hidden` to hide any of the extra content that doesn't fit in the box. 
    - use `overflow: scroll` to create a scrollbar for overflow content. 

### Border, Margin, Padding 
Text Content --> Padding --> Border --> Margin. These are added when box height and width are specified. Margin and Padding used to add __whites space__ which is good for design. 

#### Border
- `border-width` can also specify which side specifically using `border-top-width`. 
- `border-style` can be set to solid, dotted, dashed, inset, outset, etc. Can also specify which side specifically using `border-top-style`. 
- `border-color` Can also specify which side specifically using `border-top-color`.
- Shorthand `border: 3px dotted black`

#### Padding
- `padding` or `padding-top`
- `margin` or `margin-top`. Also has `margin: top right bottom left` `margin: 2px 3px 2px 3px`.

#### Centering Content
Center a box: set `left-margin` and `right-margin` to `auto`. Browser will make an equal gap on left and right side of box. 

#### Change inline/block (display)
Let you switch inline to block and visa-a-versa using `display`.
- `display: inline`: causes block-level to inline
- `display: block` causes inline to act like  block
- `display: inline-block` Causes block-level elements to flow like inline elements but keep block-level features.
- `display: none` acts like element isn't on page.

#### Hiding Boxes
`visibility: visible/hidden` can hide boxes but still leave the space of where it was. 

### CSS3: Border Images
- box must have a border. 
- `border-image: url("img path") 11 11 11 11 stretch/repeat/round` applies an image to the border of the box. 
- CSS box shadows: `box-shadow` and can do horizontal offset, vertical offset, blur distance, spread of shadow. *inset* used before above values makes box have an inner-shadow. 
- `border-radius` rounds the corners.Can also have `border-top-right-radius` etc. to target specific corners.

From the Duckett JS book:

# JavaScript Chapter 4: “Decisions and Loops” from switch statements on (pp.162-182)

### Switch Statements 
- Switch statements start with a switch value. 
- Has a **default** option that is run if none of the cases match. 
- Once case code runs, br*eak statement stops everything, thus making it perform better than multiple if statements. 

```javascript
var msg; // Message
var level = 2; // level 2, which is case 2

//Determines message based on level (which is 2 in this case). If none match, default would run)
switch (level) {
    case 'One': 
    msg = 'Good luck on the first test';
    break;

    case 'Two':
    msg = 'Second of three - keep going!';
    break;

    case 'Three':
    msg = 'Final round, almost there!';
    break;

    default:
    msg = 'Good luck!';
    break;
}

// In the answer area, the msg will print. 
var el = document.getElementById('answer');
el.textContent = msg;
```

#### Type Coercion & Weak Typing 
Type coersion: Where you can change the datatype behind the scene . '1' string one to number 1. This can cause errors. Best to use strict equals `===` or `!==`. 

#### Truthy Falsy
Truthy - treated as if it were true.
Falsy - treated as if it were false. 
```javascript
//Falsy examples (0)
var highScore = false; // Boolean false
var highScore = 0; // Num is zero
var highScore = ''; // Empty str
var highScore = 10/'score'; // NaN 
var highScore; // no value assigned to variable 

//Truthy examples (1)
var highScore = true; // Boolean true
var highScore = 3; // Num other than zero
var highScore = 'good'; // str with content
var highScore = 10/5; // num calc 
var highScore = 'true'; // true written as str
var highScore = '0'; // 0 written as str
var highScore = 'false'; // false written as str

```

#### Short Circuit Values
Logical operators processed left to right. Once truthy value is found, the rest aren't checked.
- OR || Put code most likely to return true first
- AND && Put false first 
- Requiring more processing power, put them last in case earlier ones return true. 

#### Loops
- `for` - counter usually used to tell it how many times to run. Good for looping through arrays.

    ```javascript
    for (let i = 0; i < 10; i++) {
        //do this
    }

    // let - initialization
    // i < 10 - condition 
    // i++ - update
    ```

- `while` runs as long as statement is true

    ```javascript
    while (i < 10)) {
        //do this
    }
    ```

- `do while` - similar to while. runs once even if condition is false. 
    ```javascript
    let i = 1;

    do {
        // do this 
        i++
    } while (i < 1);

    // i is already 1 but code runs at least once in do while. Condition is checked after block runs once.
    ```

Be care of indefinite loops. Breaks will terminate a loop and go to next statement of code outside of loop. 
