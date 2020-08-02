# Readings 
## JS Templates
### Template literals (Template strings) from (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

Template literals are template strings with expressions inside them. They are a simpler way to concatenate strings and strings with variables or functions. They start and end with back ticks and the variables or functions inside are enclosed like so \`${variable or function}\`. To add a back tick inside the template literal, you must use `\` then add the back tick. 

### Getting Literal With ES6 Template Strings FROM (https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

```js
//STRING
// Simple string substitution
let name = "John Smith";
console.log(`Hello, ${name}!`);

// Log: "Hello, John Smith!"

//MATH
let favNum1 = 13;
let favNum2 = 6;
console.log(`My two favorite numbers added together equals ${favNum1+favNum2}.`);

//FUNCTIONS
function example() { return "Here is an example"; }
console.log(`HELLO ${example()} BYE-BYE`);
//log: HELLO Here is an example BYE-BYE

//METHODS 
let name = {favDrink: 'coffee'};
console.log(`My favorite drink is ${name.favDrink.toUpperCase()}.`);

// log: "My favorite drink is COFFEE";
```

### Template Literals FROM (https://css-tricks.com/template-literals/)

Template literals can be multi line as well, by just entering down a line. You don’t need to type `\n` for a new line like with concatenation. 

```js
//MULTI LINE
let exampleMultiString= `This will be
on two lines!`;


//COMPLEX OBJECTS
let person = {
    firstName: `John`,
    lastName: `Smith`,
    sayName() {
        return `Hi my name is ${this.firstName} ${this.lastName}`;
    }
};
```

## ARRAY METHODS (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) and (https://medium.com/@abustamam/for-loops-vs-foreach-in-javascript-7a977278a39e)
.forEach can replace for loop. It can also take a callback so it takes 3 arguments.
```js
//.forEach can replace for loops. 
const names = ['name1', 'name2', 'name3']
const copyOfNames = []

// before
for (let i = 0; i < names.length; i++) {
  copyOfNames.push(names[i])
}

// after
names.forEach(function(name){
  copyOfNames.push(name)
})
```
