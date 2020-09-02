## Promise
A promise used for when a value is “on it’s way”. There is a fulling, pending, and rejected state. Can chain promises using `promise.then()` and have a `promise.catch()` to handle rejected ones. 

Instance methods: 
- `promise.prototype.catch`
- `promise.prototype.then`
- `promise.prototype.finally`


## Destructuring assignments
- unpacking values and properties into separate variables. 

```js
//Example from site

let a, b, rest;
[a, b] = [10, 20];

[a, b, ...rest] = [10, 20, 30, 40, 50];  //rest if 30, 40, 50

```

- The rest keyword represents the rest of the values.

## Spread
Let’s iterables be expanded by just using ... three dots and the name. 

```js
//Example from site

const numbers = [1, 2, 3];
console.log(sum(...numbers));
//Numbers here is 1, 2, and 3 so the console log has the output of 6.
```

## Rest parameters
Three dots before restArgs. They are the rest of the arguments returned as an array. If there aren’t anymore arguments, an empty array is returned. 

### DevTernity 2017: Ian Cooper - TDD, Where Did It All Go Wrong?
- The Problem:
- TDD Rebooted
- Red-Green-Refactored 
- Clean Code When?
- Refactoring to Patterns
- Ports and Adapters
- Gears
- ATDD
- Behavior Driven Development 
- Mocks 


- Not wanting to write tests or pressure to skip tests.
- More test code than production code. 
- Write tests is part of writing code.
- Refactor and need to rewrite mock tests problem. 
-  2009-2010 against TDD because its slower.
    - Software dev to customers. Short code. No tests. When wanting to make changes, rewrite the code. 

- Duct Tape Programmer: quickly finishing but difficult maintain.

- Test-Driven Development by Kent Beck 
    - Test behaviors!
    - There’s something I want  the software to do, make a test for it. 
    - Test the API of the software (what does your software do for the world?)
    - What the software offers is the same (Test this), but how it does it may change. 
- Test Driven Development —> Behavior Driven Development 
    - Behavior is a good word to use...test the behavior...test the behaviors in the system. 
- RGR 
    - Red: write a broken test to make sure it will break appropriately
    - Green: Make it pass as fast as possible. How you WILL implement the requirements. Can be messy but make the test pass. 
    - Refactor it so its faster and cleaner but does not alter the external behavior. Improves the internal structure. 
- Test behaviors 

## What the heck is the event loop anyway? Philip Roberts
event loop inside JavaScript

- JS is a single threaded runtime. Can do one thing at a time.
- The stack tells us where we are in the code. 
- Blocking - code that is slow.
- Ex. On button click, blocking —> can’t do anything else. Browser is stuck. 
    - Fix: asynchronous callbacks
- Concurrency and the event loop 
        - Event loop, looks at task (callback) queue and stack. If stack (JS) is empty, first task in queue is pushed onto stack. 
        - 3 parts: Stack — setTimeout goes to webapis — task queue 
        - Render queue: when render queue is blocked, can’t click text on screen. 
        - Don’t block the event loop...
            - Slow work example: on scroll, do something. Doesn’t block, but queue is backed up.
