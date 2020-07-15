# Domain Modeling - https://github.com/codefellows/domain_modeling#domain-modeling

Domain Modeling is the process of creating a conceptual model in code for a specific problem. Storing data in properties and behaviors in methods is an **Object Oriented Model**. 

#### Object Oriented Programming In JavaScript
- The new keyword creates an object
- The constructor function initializes properties inside that object using the *this* keyword. 
- Use the *this* variable within methods so the object's properties and methods are accessible (from inside).
- The object is stored in a variable to use later (from outside).

.prototype

# From the Duckett HTML book: Chapter 6: “Tables” (pp.126-145)
How to create tables
What info suites tables
How to represent complex data in tables

Tables are often used for sports results, stock reports, train timelines, etc.
Each block is referred to as a table cell. In HTML, tables are written row by row. 

Table structure
```html
<table>
    <tr>
        <th></th> // table heading
        <td>Table data goes here<td>
    </tr>
</table>
```

Always have a <th> even if it’s empty. <th scope=“row”> means it’s bolded. 
Tables rows and columns can be stretched or spanned by using colspan=“2” or rowspan=“2”. 

**Long tables**

```html 
<thead>table headings should go here </thead>
<tbody>body should go here</tbody>
<tfoot>footer goes here</tfoot>
```

These are used used to help screen readers and are useful for CSS styles. 

# From the Duckett JS Book: Chapter 3: “Functions, Methods, and Objects” (pp.106-144)

```js
let hotel = {
    name: 'Quay',
    rooms: 40,
    booked: 25,
    checkAvailability: function() {
        return this.rooms - this.booked;
    }
}
```

`this` keyword is used to indicate that it is using the `rooms` and `booked` properties in *this* object. 

### Creating a New Object: Constructor Notation
The new keyword and constructor create a blank object that you can add properties and methods to using dot notation. 

```js
let hotel = new Object(); 
// add properties using dot notation
    hotel.name = 'Quay',
    hotel.rooms = 40,
    hotel.booked = 25,
    //method
    hotel.checkAvailability = function() {
        return this.rooms - this.booked;
    }
}

// updating the object using dot or bracket notation
hotel.name = 'Park';
hotel['name'] = 'Park';

// Delete a property using the delete keyword or empty string
delete hotel.name
delete hotel.name = '';
```

### Creating Many Objects: Constructor Notation

```js 
// the function called Hotel takes 3 parameters, setting the property value in the object
function Hotel(name, rooms, booked) {
    //properties 
    this.name = name;
    this.rooms = rooms;
    this.booked = booked;
    //method
    this.checkAvailability = function() {
        return this.rooms - this.booked;
    }
}

// Create instances of the object
// new keyword followed by calling the function (Hotel) creates a new object.

//Object is quayHotel. (name, rooms, booms booked)
let quayHotel = new Hotel ('Quay', 40, 25);
let parkHotel = new Hotel ('Park', 120, 77);
```

### This (keyword)
Commonly used inside functions and objects. It always refers to one object, usually the object in which the function operates.

### Storing Data
Can use variables, arrays and objects. If the order of the items is important, use an array.

- Variables 

    ```js
    let hotel = 'Quay';
    //retrieve data
    hotel;
    ```

- Arrays

    ```js
    let hotels = [
        'Quay',
        'Park',
        'Beach',
        'Bloomsbury'
    ]
    //retrieve Park
    hotels[1];
    ```

- Individual Objects

    ```js
    let hotel = {
        name: 'Quay',
        rooms: 40
    }
    //retrieve Quay
    hotel.name;
    ```

- Multiple Objects

    ```js
    function Hotel(name, rooms) {
        this.name = name;
        this.rooms = rooms;
    }

    // create instances of the object using new keyword then a call to the constructor function
    let hotel1 = new Hotel('Quay', 40);
    let hotel2 = new Hotel('Park', 120);

    //retrieve Parks
    hotel2.name;
    ```
    
**Arrays** are a special type of object. They have key/value pairs like objects, but the key (for each value) is the index number. 

For complex data structures, you can have arrays in objects and objects in arrays. 

### Built-In Objects
Browsers built-in objects are things like the browser window and current web page being displayed on that window. Built-in objects after often needed in scripts. Once page loads, the script can use them! Access them using dot notation. 

This has many tools useful and used when writing scripts. 

- Browser Object Model 
    - This contains objects that represent the current browser window or tab. Contains objects that model things like browser history and device's screen. 
    - Ex. `window.print()`, `window.screen.width`
- Document Object Model 
    - Uses objects to create representations of current page. Creates a new object for each element.
    - Ex. `document.getElementById('one')`
- Global Javascript Objects 
    - Represent things that JS needs to create a model of. Ex. Object for date and time. 
    - Ex. `hotel.toUpperCase()`, `Math.PI`.

### Global Objects: String Objects
If you have a value that is a string, there are many String objects that you can use. The String object is a **global object** because it works anywhere in the script. It is also a **wraper** object. 

```js 
let saying = 'Home sweet home ';
saying.length; // returns length
saying.toUpperCase(); // changes string to uppercase characters
saying.toLowerCase(); // changes string to lowercase
saying.charAt(0); // returns H
saying.indexOf('ee'); // returns 7
saying.substring(8,14); // returns 'et hom
saying.split(' '); // returns the array ['Home', 'sweet', 'home']
saying.trim(); // returns 'Home sweet home'
saying.replace('me', 'w'); // returns 'How sweet home'
```

### Global Objects - Number Object
When you have a value that is a number, you can use Number objects on it. 

- `.isNan()` - Checks if the value is not a number
- `.toFixed(2)` - rounds to a specified number of decimal places (returns a string). Here it's two decimal places.
- `.toPrecision()` - rounds to a total number of places (returns a string)
- `.toExponential()` - returns a string representing the number in exponential notation


### Global Objects - Math Object
- `Math.Pi` - returns pi
- `Math.round()` - returns num to nearest integer
- `Math.sqrt(n)` - returns square root of num (ex. Math.sqrt(9) returns 3)
- `Math.ceil()` - rounds num to nearest integer
- `Math.floor()` - rounds num down to nearest integer
- `Math.random()` - generates random num between (inclusive) 0 and 1 (not inclusive). Random num between 1-10 is `Math.floor(Math.random() * 10) + 1`

### Create an Instance of a Date Object
- `getTime()` or `setTime()` num of milliseconds since Jan 1, 1970, 00:00:00 UTC and a negative num for any time before. 
- Create date objects - `let today = new Date();`
