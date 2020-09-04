## 10 JavaScript array methods you should know FROM https://dev.to/frugencefidel/10-javascript-array-methods-you-should-know-4lk3

- forEach()
- includes()
- filter()
- map()
- reduce()
- some()
- every()
- sort()
- Array.from()
- Array.of()

## Cheat Sheet FROM https://jrsinclair.com/javascript-array-methods-cheat-sheet
Great cheat sheet for figuring out which array method to use. 

## Class basic syntax FROM https://javascript.info/class
Basic class syntax 

```js
// FROM SITE
class MyClass {
  // class methods
  constructor() { ... }
  method1() { ... }
  method2() { ... }
  method3() { ... }
  ...
}
```

In JS, a class is a kind of function, can be assigned, passed, returned, etc. Can use `get` and `set`. Class fields set to individual objects, not the prototype. 

## Classes FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
Classes - a template for creating objects. Built on prototypes. A "special function". There are class expressions and class declarations. Classes are not hoisted. 

Class expressions can be named or unnamed. 

```js
// UNNAMED  
let Rectangle = class {
  // class body
  // constructor
}
// NAMED
let Rectangle = class Rectangle2 {
  // class body
  // constructor
}
```

Use `extends` for subclasses. 

## MVC Architecture in 5 minutes: a tutorial for beginners FROM https://www.educative.io/blog/mvc-tutorial
Model View Controller (MVC)
- popular for web apps
- helpful for planning development 
- easier to maintain or modify
- each part can be tested (M, V, C)
- MVC don't depend on one another 


## MVC Framework - Introduction FROM https://www.tutorialspoint.com/mvc_framework/mvc_framework_introduction.htm#:~:text=The%20Model%2DView%2DController%20(,development%20aspects%20of%20an%20application
MVC - an architectural pattern used for separating application in 3 parts. 
Model - data 
View - UI / the customer view
Controller - Interface between model and view 

ASP.NET MVC - lightweight framework 
- Web pages 
- Web forms 
- MVC 


## MVC Explain in 4 minutes FROM https://www.youtube.com/watch?v=DUg2SWWK18I
- Popular pattern
- Model - View - Controller 
- Split into sections. 

- Controller receives request. Should never interact with the data logic. Responds based on model. 
- Model responsible for handling the data logic only. 
- View - dynamically renders HTML based on the data received. 

Model and view never interact with one another. This is done through the controller. 
