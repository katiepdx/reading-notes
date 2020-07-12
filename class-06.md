# Chapter 3: “Object Literals” (pp.100-105)
#### What is an Object?
- Objects group together a set of variables and functions to create a model of something you'd recognize. The variables and functions take on new names. 
    - Variables become properties, which tell us about the object. Ex. Object = hotel. Variable/property = rooms: 40. 
    - Functions become methods and these are tasks associated with the object. 
    - Literal notion is the easiest and most popular way of creating an object.
        - Strings are put in quotes and arrays are in brackets like usual. 
    - Accessing an object: Use *dot notation* or *bracket notation*
    - To create more object literals on the same page, set the variables to different names.

    ```js
    // Object example
    let hotel = {
        //Properties (key value pairs)
        name: 'Quay',
        rooms: 40,
        booked: 25,
        gym: true, 
        roomTypes: ['twin', 'double', 'suite'],
        //Methods
        checkAvailability: function () {
            return this.rooms - this.booked;
        }
    };

    //Access an object using DOT notation
    // SYNTAX let variable = object.property/method name;
    let hotelName = hotel.name;
    let roomsFree = hotel.checkAvailability();
    //Access an object using BRACKET notation
    // SYNTAX let variable = object['property/method name'];
    let hotelName = hotel.['name'];
    let roomsFree = hotel.['checkAvailability']();
    
    //Displays name and rooms available in the boxes using .textContent and getElementById
    let elName = document.getElementById('hotelName');
    elName.textContent = hotel.name;

    let elRooms = document.getElementById('rooms');
    elRooms.textContent = hotel.checkAvailability();
    ```

# Chapter 5: “Document Object Model” (pp.183-242)
When a browser opens a page, a model of the pages goes to the memory. The DOM specifies the way a browser should structure the model using a *DOM tree*. The DOM tree is a model of a web page. 
- The DOM is made of objects. 
- The DOM is also called API Application Programming Interact. 
    - APIs let programs (and scripts) talk to each other.

- **The Document Node**
    -The document node represents the entire page. It's at the top of the DOM tree.
- **Element Nodes**
    - These are HTML elements. To access the DOM tree you will be looking for the element nodes you want. 
- **Attribute Nodes**
    - The opening tags of HTML elements can have attributes in them that are represented by attribute nodes in the DOM tree. These nodes are not children of the element. You can change the values of a class attribute to trigger new CSS rules. 
- **Text Nodes**
    - After accessing the element node, you can access the text within that element. That text is stored inside its own text node. These nodes do not have children. If there is a child, it's the child of the containing element. 

Methods that find elements in the DOM tree are called DOM queries. If you need to access an element again, the result of the query should be stored in a variable. Ex. `let itemOne = getElementById('one')` the variable 'itemOne' is stored in the DOM tree and can be accessed like this `itemOne.textContent`. Ids return a single node because ids are unique and only one element can have one. `QuerySelector('css selector')` only *returns one* element because it returns just the first element that matches the selector.DOM queries can also return more than one element which would be a *NodeList* (a collection of nodes). Ex. `getElementsByClassName('class'), getElementsByTagName('tagname'), and querySelectorAll('css selector')` 

#### NodeList
These look like and are numbered like arrays (starting at 0), but they are NOT arrays. They are a type of object called a **collection**. You can select one element from the NodeList or Loop through each item in theNodeList adn perform the same statements on each of the nodes. 
- **Live NodeList** - when a script updates a page, the live NodeList is also updated.These can be faster than static node lists.
- **Static NodeList** - not updated when a script updates the page. 

#### Selecting an Element From a NodeList
- `item()` Method 
    ```js
    let elements = document.getElementsByClassName('hot')
    if (elements.length >= 1) {
        let firstItem = elements.item(0);
    }
    ```
- Array Syntax (Preferred method because it's faster!)
    ```js
    let elements = document.getElementsByClassName('hot')
    if (elements.length >= 1) {
        let firstItem = elements.item[0];
    }
    ```
- Change class attributes 
    ```js
    // Example 1
    let elements = document.getElementsByClassName('hot'); // Find hot items and run the following
    if (elements.length > 2) { // If 3 or more elements are found in the node list
        let el = elements[2]; // Select the third element in the node list
        el.className = 'cool'; // Change the value of class to 'cool' from 'hot'
    }

    // Example 2
    // Only one
    let el = document.querySelector('li.hot'); // Returns only the first match
    el.className = 'cool'; // changes the first <li> item with the class="hot" to class="cool".
    
    // returns a NodeList
    // The second matching element (3rd item on list) is selected and changed
    let els = document.querySelectorAll('li.hot'); // Returns only the first match
    els[1].className = 'cool'; 
    }
    ```
    NOTE: In the DOM tree, now there is only one `<li>` element with the `class="hot"` and two `<li>` elements with the `class="cool"`.

#### Looping Through NodeLists
Can use a for loop to loop through and change a Nodelist

    ```js
    // Updates all <li> elements with the class of hot to class="cool".
    let hotItems = document.querySelectorAll('li.hot');
    // If the hotItems list contains items, run the for loop 
    if (hotItems.length > 0) {
        for (let i = 0; i < hotItems.length; i++) {
        hotItems[i].className = 'cool';
        }
    }
    ```

#### Traversing the DOM
For the scenario - 
```
-------ul-------
|li||li||li||li|
```

- parentNode 
    - parentNode of the first `<li>` would be the `<ul>`
- previousSibling or nextSibling
    - For the first `<li>`, there is no previousSibling since it's the first. nextSibling would be the `<li>` to the right. 
- firstChild or lastChild
    - If you start at `<ul>` at the top, the firstChild would be the node representing the first `<li>` and the last being the node representing the last `<li>`. 
NOTE: If a property is used and a node doesn't exist, the result is `null`. 

#### Whitespace Nodes
Sometimes browsers assign a text node whenever there is whitespace between elements. 
- IE - ignores whitespace and doesn't create extra nodes
- Chrome, Firefox, Safari, Opera - creates whitespace text nodes

#### Access and update a Text Node with nodeValue
To use **nodeValue**, you must be on a text node. 
- Access and change text node
    ```js
    // NODE VALUE
    // Get second list item
    let itemTwo = document.getElementById('two');
    // Get the text content 
    let elText = itemTwo.firstChild.nodeValue;
    // Change pine nuts to kale  
    elText = elText.replace('pine nuts', 'kale');
    // Update the list item
    itemTwo.firstChild.nodeValue = elText; 

    // TEXT CONTENT - this replaces all content (including any markup)
    document.getElementById('one').textContent;

    // INNER TEXT - avoid using it
        // When getting innerHTML, the content and any markup (e.g., `<em>` or `<strong>`) is also returned as a long string. Ex. <li id="one"><em>fresh</em> figs</li>
    // Updating text with innerHTML
    // Store first list item in a variable
    let firstItem = document.getElementById('one');
    //Get the content of the first list item
    let itemContent = firstItem.innerHTML;
    // Update the content so it's a link
    firstItem.innerHTML = '<a href=\"http://example.org\"> + itemContent + '</a>';
    ```

#### ADDING Elements
- Using DOM Manipulation
    - `createElement()`  create the element
    - `createTextNode()` creates new text node
    - `appendChild()` adds the node to the DOM tree

    ```js
    // Create a new <li> element and store it in a variable
    let newEl = document.createElement('li');
    // Create a text node and store it in a variable
    let newText = document.createTextNode('quinoa');
    // Attach the new text node to the new <li> element
    newEl.appendChild(newText);
    // Find the position where the new element should be added
    let position = document.getElementsByTagName('ul')[0];
    // Place or insert the new element into that position
    position.appendChild(newEl);
    ```

    - `document.write()` is a method that adds content. Rarely used now. 
    
#### REMOVING Elements
- Removing DOM elements also removes the child elements.
    - store the element to be removed in a variable
    - store the parentNode of the element you want to remove
    - Remove the element from its containing element using `removeChild(The parameter here is the element you want to remove)` with the parameter being the element you no longer want.

    ```js
    // The element to remove
    let removeEl = document.get ElementsByTagName('li')[3];
    // Its containing/parent element
    let containerEl = removeEl.parentNode;
    // Remove the element
    containerEl.removeChild(removeEl);
    ```

#### Cross-Site Scripting Attacks (XSS)
Be careful of XSS if using innerHTML. XXS is when malicious code is placed in a site. Attacks can gain access to the users' accounts. 

**Defending Against XSS**
- VALIDATE INPUT going to the server
    - Only let visits input needed characters when giving information. This is **validation**. Do not allow untrusted users to submit HTML markup or JS.
    - Double check validation on server before showing user content and storing it to a database.
    - Database stores, not processes, the markup and JS. 
- ESCAPE DATA coming from the server and database
    - As data leaves the database, potentially dangerous characters should be escaped
    - Only insert content generated by users into certain parts of the template files
    - Do not create DOM fragments containing HTML from untrusted sources. Only add text once it has been escaped.
innerHTML can be used safely to add markup to a page if you trust the source. Content from untrusted sources should be escaped and added as text (not mark up) by using the *textContent*  or the like. 

**User's content should NOT go in the following places**:
- Script tags `<script> not here </script>`
- HTML comments `<!-- not here -->`
- Tag names `<notHere href="/test" />`
- Attributes `<div notHere="norHere" />`
- CSS Values `{color: not here}`

Any content given by users that contains characters used in code should be escaped on the server. Control markup added to page. 
    - Escaping: some functions help strip out/escape malicious code. 
    - Strip out/escape the & so it is not processed as `&amp;`. 
    - NEVER include data from untrusted sources in JS. Escape all non-alphanumeric ASCII characters with a value less than 256.
    - Adding content: After escaped on the server, it should still be uploaded as text. 

**Attributes**
- `setAttribute()` method
- `removeAttribute()` - takes in one parameter, the name of the attribute you want to remove

    ```js
    // Gets the first item
    let firstItem = document.getElementById('one');
    // If it has a class attribute
    if (firstItem.hasAttribute('class')) {
        // remove the class attribute
        firstItem.removeAttribute('class');
    }
    ```

You can examine the DOM using *inspect* in Chrome. 


# https://simpleprogrammer.com/understanding-the-problem-domain-is-the-hardest-part-of-programming

#### Common Tricky Problems When Writing Code
- Learning a new technology 
- Naming things
- Testing the code 
- Debugging 
- Fixing the bugs
- Making the software maintainable
- and, more.
- **LEARNING THE PROBLEM DOMAIN**

It can be difficult to learn two things at once (e.g., problem domain and the new technology). Writing code is like putting a jigsaw puzzle together. Problem domains are like puzzles with blurry or absent pictures. Programmers sometimes are given incomplete information about the problem domain, so that means there isn't enough information to even understand it.

UNDERSTANDING THE PROBLEM IS A CRUCIAL PART TO BEING ABLE TO WRITE CODE EASILY. 

#### What to do if you don't understand the problem domain? 
- Make the problem domain easier 
    - This can often be done by cutting out cases and narrowing the focus to a certain part of the problem. Understand one part of the problem and go from there. Games (like Starcraft) are examples of starting with basic and small problems so you are not overwhelmed and gradually add harder and new concepts with each level advancement.
- Get better at understanding it
    - Talk the problem out. Be sure you know the problem really well before starting to code. Redoing something can be expensive and time consuming. Best to get it done correctly the first time around. 









