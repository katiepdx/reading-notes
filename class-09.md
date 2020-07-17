# From the Duckett HTML book: Chapter 7: “Forms” (p.144-175)
- How to collect information from visitors 
- Different kinds of form controls
- New HTML5 form controls

There are several types of form controls that let you collect information. 
- Adding Text
    - Text input (single line)
    - Password Input 
    - Text area (multi-line) for comments and messages
- Making choices 
    - Radio buttons
    - Checkboxes 
    - Drop-down boxes
- Submitting forms 
    - Submit buttons
    - Image buttons 
- Uploading files
    - File upload

#### Form Process
- User fills out form 
- Server processes it
- Server creates a received message

Info sent to browser using `name/value` pairs. Careful changing the name of form control. 

### Form Structure 
Forms go inside a `<form></form>` element. This should contain an action attribute, method and id. The size of the input field can be done in CSS. 

```html
<form action="http://www.example.com/login.php">
    <p> Username: 
        <input type="text" name="username">
    </p>
    <!-- NOTE: Password is black dots, but info is not sent securely. For full security (for things like credit card info), server needs to be set up to communicate with browser using SSL Secure Sockets Layer. -->
    <p> Password: 
        <input type="password" name="password">
    </p>
</form>
```

#### Text Area - for messages and comments

```html
<form action="url">
    <p>What did you think about XYZ?</p>
    <textarea name="comments">
        Enter your comments here. This text shows up inside the block and needs to be deleted by the user.
    </textarea>
</form>
<!-- This form can also be styled in CSS -->
```

#### Radio button - only one can be checked in a group

```html
<!-- NOTE: rock is checked -->
<form action="url">
    <input type="radio" name="genre" value="rock" checked="checked"/> Rock
    <input type="radio" name="genre" value="pop"/> Pop
    <input type="radio" name="genre" value="jazz"/> Jazz
</form>
```

#### Checkbox - User can select or deselect as many as they want

```html
<!-- NOTE: rock is checked -->
<form action="url">
    <input type="checkbox" name="genre" value="rock" checked="checked"/> Rock 
    <input type="checkbox" name="genre" value="pop"/> Pop
    <input type="checkbox" name="genre" value="jazz"/> Jazz
</form>
```

#### Drop down list box (select box) - User can select from a list

```html
<form action="url">
    <!-- add (multiple="multiple") in select to allow user to select multiple options. User may need to hold control or command while selecting -->
    <select name="devices">
        <option value="ipod">Ipod</option>
        <option value="radio">Radio</option>
        <option value="computer">Computer</option>
    </select>
</form>
```

#### File Input Box 

```html
<!-- NOTE: Browse button lets user search for the file on their computer-->
<form action="url" method="post">
    <p>Upload your song in mp3 format</p>
    <input type="file" name="user-song"/><br/>
    <input type="submit" value="Upload"/>
</form>
```

#### Submit button - used to send the form to the server

```html
<!-- NOTE: Browse button lets user search for the file on their computer. Value of subscribe is printed in the submit button box.-->
<form action="url" method="post">
    <p>Subscribe to our email list</p>
    <input type="text" name="email"/><br/>
    <input type="submit" name="subscribe" value="subscribe"/>
</form>
```

#### IMage button - Using an image as a button

```html
<!-- NOTE: Browse button lets user search for the file on their computer. Value of subscribe is printed in the submit button box.-->
<form action="url" method="post">
    <p>Subscribe to our email list</p>
    <input type="text" name="email"/><br/>
    <input type="image" src="images/subscribe.jpg" width="100" height="20"/>
</form>
```

Adding a `type="hidden"` hides the field from the user but can still be seen in View Source.

```html
<!-- NOTE: Browse button lets user search for the file on their computer. Value of subscribe is printed in the submit button box.-->
<form action="url" method="post">
    <p>Subscribe to our email list</p>
    <input type="text" name="email"/><br/>
    <input type="image" src="images/subscribe.jpg" width="100" height="20"/>
</form>
```

#### Labeling For Controls
`<label>` used to label the button, field, etc. 

    ```html
    <!-- Method 1 -->
    <label for="Age">Age <input type="text" name="age"/></label>
    <!-- Method 2 -->
    <input id="apple" type="radio" name="fruit" value="fruit">
    <label for="apple"> Apple </label>
    ```

Can group form elements using `<fieldset>` or `<legend>`.

HTML5 Form Validation - `required="required"` makes field mandatory. 

Date Input - set `<input type="date">` to get date. 

Input Fields with  `<input type="email">` or  `<input type="url">` let smartphone keyboards display common symbols like @ or '.com'

Search input - Input Fields with  `<input type="search" placeholder="What are you looking for?">` creates a search box with placeholder text of the question.

# From the Duckett HTML book: Chapter 14: “Lists, Tables & Forms” (pp.330-357)
- Ordered List styles CSS
    - list-style-type: decimal
    - list-style-type: decimal-leading-zero
    - list-style-type: lower-alpha
    - list-style-type: upper-alpha
    - list-style-type: lower-roman
    - list-style-type: upper-roman

- Unordered List Style images CSS
    - list-style-image: url("images/star.png")

- Positioning the marker (bullet) in CSS
    - list-style-position: outside/inside

- List shorthand 
    - list-style: inside circle;

### Tables
- Table properties 
    - width
    - padding
    - text-transform (converts text to uppercase)
    - letter-spacing, font-size
    - border-top, border-bottom
    - text-align
    - background-color
    - :hover

- Border on empty cells (`empty-cells`)
    - `empty-cells: show;` shows borders of empty cells
    - `empty-cells: hide; ` hides borders of empty cells
    - `empty-cells: inherit;` inherits rules of containing table

- Gaps between cells (`border-spacing`, `border-collapse`)
    - `border-spacing: 5px 15px;` controls the gap
    - `border-collapse/separate; ` border collapses into a single border where possible.Separate: borders detach. 

### Styling forms 
Styling fields, buttons, legends, etc., can make form more interesting for the user to fill out. 

Cursor Styles (`cursor`)
    - `cursor: auto;`
    - `cursor: crosshair;`
    - `cursor: default;`
    - `cursor: pointer;`
    - `cursor: move;`
    - `cursor: text;`
    - `cursor: wait;`
    - `cursor: help;`
    - `cursor: url("cursor.gif");`

# From the Duckett JS book: Chapter 6: “Events” (pp.243-292)

Interactions create events -> Events trigger code -> Code responds to the users. 

Types of events include: `load`, `unload`, `error`, `resize`, ``scroll`, `keydown`, `keyup`, `keypress`, `click`, `dbclick`, `mousedown`, `mouseup`, `mousemove`, `mouseover`, `mouseout`, `focus`/`focusin`, `blur`/`focusout`, `input`, `change`, `submit`, `reset`, `cut`, `copy`, `paste`, `select`. MUTATION EVENTS: `DOMSubtreeModified`, `DOMNodeInserted`, etc.

Event handling - User interacts with HTML on page and JS is triggered. There are DOM event handlers (on+event ex. onblur) and DOM event listeners.
    - select element
    - specify event
    - trigger code

**DOM Event Listeners**
Older versions of IE do not support `addEventListener()` and need the alternative of `.attachEvent()`. 

    ```js
    element.addEventListener('event', functionName () {
        //do this
    });
    ```

**Event Flow** - The order in which an event is fired. It's important if your code has event handlers on an element AND one of its ancestors or descendant elements.
    - Event bubbling - the event starts at the most specific node and *flows outwards*.
    - Event capturing - the event starts at the least specific node and *flows inward* to the most specific one.

When an event occurs, the event object tells us information about the event and the element that it happened on. 

Event objects passed into a function: the letter "e" is often used as a parameter. "e" is for *event*. 

Change default behavior - `.preventDefault()` or `.stopPropagration()`. Sometimes seen in situation where they have `return false`. 

#### Different Types of Events
- W3C DOM events 
- HTML5 Events
- Browser OBject Model (BOW) events
    - Several of these events deal with touchscreen devices.

#### Focus and Blur Events (often used on forms)
Focus events are like when you click on a field to enter text, then blur is when you switch to another field. CSS now has a pseudo class `:focus` that solves this.

#### Where Events Occur
- Screen - screenX and screenY
- Page - pageX and pageY
- Client - clientX and clientY

#### Keyboard Events
- When a key is pressed, an ASCII code is returned. To get the converted keyboard equivalent, you can use `String.fromCharCode(event.keyCode)`.

#### Form Events
JS can be used to check if a user misses any required information on a form of it the info is incorrect. This is called *form validation*.

### Mutation
- Mutation events make the page feel slow and unresponsive. They are being replaced by mutation observers.
- Mutation observers wait until a script has finished its task before reacting, then batch report the changes instead of one at a time. Many browsers support this.

#### Popular HTML5 Events
- `DOMContentLoaded` - event fires when the DOM tree is formed (images, CSS, and JS might still be loading).
- `hashchange` - Event fires when URL hash changes (without the entire window refreshing).
- `beforeunload` - Event fires on the window object before the page is unloaded. Should only be used to help the user (not keep them on the site). Used to let user know that changes on a form have not been saved, etc.

