## Object initializer FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer

- There are multiple ways to initialize a new object
    - `new Object()`
    - `Object.create()`
    - literal notation
- There are also getters and settings for objects. 
- There are also spread operators that use three dots before the object name...it makes a copy of the object. 

## Inheritance and the prototype chain FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
When working with inheritance in JavaScript, `this` points to the inherited object. 

```js 
// Example from site
let o = {
    a: 2,
    m: function() {
        return this.a + 1;
    }
};

console.log(o.m()); // 3
```

In JS, all functions have the special "prototype" property. You can add to the prototype chain.  When accessing a property, the browser first looks if the property exists and if it doesn't it looks for the `__proto__`. 


## Classes FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
- Classes are a template for creating objects and are built on prototypes. Classes are "special functions" and have two components -- class expressions and class declarations. Function declarations must be *hoisted* (declaring at the top) whereas class declarations do not. Must declare the class to access it. Classes can be extended using the `extends` keyword. The `extends` keyword creates a class as a child of another class. When using `extends`, you will need to use `super` class constructor (ex. `super.speak();`). 

## Destructuring assignment FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
Destructuring unpacks values or properties into separate variables. `rest` word can be used in destructuring to account for the rest of the values in both arrays and objects. 

```js
// Examples from site
// Restructure example 
let a, b, rest;
[a, b] = [10, 20];
// a; --> 10
// b; --> 20

// Rest example
let {a, b, ...rest} = {a: 1, b: 2, c: 3, d: 4}
a; // is 1
b; // is 2
rest; // is the rest of the object -- {c: 3, d: 4}
```

