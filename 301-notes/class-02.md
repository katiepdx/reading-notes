# Applying Atomic Design 
## Visually Breaking Down UI Components using Atomic Design — Part 1 FROM (https://medium.com/backticks-tildes/visually-breaking-down-ui-components-using-atomic-design-part-1-476e1ddd73ca) Part 2 FROM (https://medium.com/backticks-tildes/visually-breaking-down-ui-components-using-atomic-design-and-building-with-react-part-2-20eb8aabab4b)

#### Atomic Design - 5 levels
- **Breaking down site design**: BIG TO SMALL. Break sites down into smaller parts - pages -> templates -> organisms -> molecules -> atoms.
- **Building site components**: SMALL TO BIG. 
    - File tree: Best to separate components into different folders by their atomic stages. 
    - Components: Small, independent, reusable
    - Delivery app example: 
        - Text component: heading, subheading, paragraph
        - RestaurantImage: 
        - SingleRestaurantListing.js renders BOTH Text and RestaurantImage.
        - Section

## The art of transforming UI features into components FROM (https://theiconic.tech/the-art-of-transforming-ui-features-into-components-e86de5560fd7)
 UI Components or component-driven front-end development 
 Storybook (https://storybook.js.org/) helpful for component maintenance
 Nested components - can reuse styling patterns 
 Focus on composition of components - UI architecture 

 ## Thinking in React FROM (https://reactjs.org/docs/thinking-in-react.html)
 Step 1: Break The UI Into A Component Hierarchy
    - Draw boxes around the different components 
    - Arrange based on hierarchy 
    - Single Responsibility Principle - one component should do one thing

## UI Components By Design FROM (https://www.thoughtworks.com/insights/blog/ui-components-design)
**Two Types of Components**
- Foundation Components - Design team UI developers build them 
- Application Components - Specific to app being built. App team builds them 

**A component-centric workflow** 
    - Design 
    - Isolate 
    - Elaborate 
    - Build
    - Integrate 
    - Learn 
    - REPEAT

# Callbacks   
## Back to Basics: What are Callbacks in JavaScript? FROM (https://www.sitepoint.com/callbacks-javascript/)
Callback Function is a function executed after another function

```js
//EXAMPLE FROM SITE 
function doHomework(subject, callback) {
  alert(`Starting my ${subject} homework.`);
  callback();
}

doHomework('math', function() {
  alert('Finished my homework');
});

// OUTPUT
// "Starting my math homework."
// "Finished my homework"
```

## JavaScript Callback Functions FROM (https://www.dashingd3js.com/lessons/javascript-callback-functions)
Video notes:  
Functions are objects in JavaScript 
Passing functions: Function one can be used in function two. 
Functions can take in many arguments. 
Callback: Synchronous - immediate call back. Asynchronous - called back later
Can pass in as many callback functions as you'd like. 
Can callback a function many times in a function.



## First Class Function FROM (https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function)
When a function can be treated like any other variable. 
- Assign a function to a variable
- Pass a function as an Argument
- Return a function

## Callback Function FROM (https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
A function passed in as an argument and is invoke inside the outer function 

```js
//Synchronous example from site
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```

## JavaScript Classes FROM (https://javascript.info/class)
A class is a kind of function 
No commas between class methods

```js
//Class Example from site
class User {

  constructor(name) {
    this.name = name;
  }

  sayHi() {
    alert(this.name);
  }

}

// Usage:
let user = new User("John");
user.sayHi();

//OUTPUT alerts John
```

## An intro to object-oriented programming in JavaScript: objects, prototypes, and classes FROM (https://www.freecodecamp.org/news/an-intro-to-object-oriented-programming-in-javascript-objects-prototypes-and-classes-5d135e7361b1/)

There are data objects and objects with functions inside like so:

```js
//Example from site 
//object with functions
const point1 = {
  x: 1,
  y: 1,
  toString() {
    return `(${this.x},${this.y})`;
  }
};

const point2 = {
  x: 2,
  y: 2,
  toString() {
    return `(${this.x},${this.y})`;
  }
};
```

- Classes are often related to inheritance. They extend - `extends`.
- Create an object from a class using `new`
- `this` accesses current instance
- `super` to access super class

Class syntax for ECMAScript6
Prototype syntax for ECMAScript5

## Object methods, "this" (https://javascript.info/object-methods)
Value of "this" is defined at run-time

```js
//From site. this.name refers to the user John
let user = {
  name: "John",
  age: 30,

  sayHi() {
    // "this" is the "current object"
    alert(this.name);
  }

//Arrow function example
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // Ilya
};

user.sayHi(); // John
```
