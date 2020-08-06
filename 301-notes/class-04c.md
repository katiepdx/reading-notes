## JavaScript Asynchronous Programming and Callbacks FROM https://flaviocopes.com/javascript-callbacks/
JS is synchronous and single threaded. Code cannot run parallel and create new threads. CALLBACKS: a function that's passed as a value to another function and only executed when that event happens. They can be used anywhere. Common example, timers. 
- Great for simple cases
- They are nested so code can get complicated quickly 


## Understanding JavaScript Promises FROM https://flaviocopes.com/javascript-promises/
Alternative way to handle asynchronous code in JS without lots of callbacks. It's a proxy for a value that is soon to be available. Waiting for promise - pending state. Returned promise - resolved state. Promise doesn't work - rejected state. 

Common APIs - the Battery API, the Fetch API, Service Works API

Create a promise: use `new Promise()` . In Fetch API, `fetch()` is the same as `new Promise()` 

Can chain promises. If a previous one was rejected, it goes to the nearest `catch()` down the chain. Can cascade errors using multiple catch(). 

`Promise.all()` - executes something when all promises are resolved. 
`Promise.race()` - runs as soon as one of the promises passed to it resolves, then it runs the callback once 

## Asynchronous JavaScript FROM https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous
Blocking code: when the browser can't continue to handle user input until web app returns control of the processor. 


## Introducing asynchronous JavaScript FROM https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing
Async callbacks - first param is event being listened for, second is callback that is run when event is fired.

Async operations such as promises are added to an **event queue** and runs after the main thread has finished. They don't block other JS code from running. 

Callbacks are considered old-fashioned. Pros of promises: chaining using `.then()` and handling errors with `.catch()`. 

Async vs asynchronous - depends on what you want to do. 

## Graceful asynchronous programming with Promises FROM https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises
Promises - has then, catch, and finally methods. Can chain finally to the end of the promise chain. Can have `resolve()` or `reject()`. 

## Using Promises FROM https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises

```js
//PROMISE EXAMPLE FROM SITE
const promise = createAudioFileAsync(audioSettings); 
promise.then(successCallback, failureCallback);
```

Pros of Promises: 
- the callback won't be called before the completion of the current run of JS event loop
- if it has a then(), it will be called regardless of success or failure of the async operation. 
- chaining

```js
//CHAINING EXAMPLE FROM SITE
new Promise((resolve, reject) => {
    console.log('Initial');

    resolve();
})
.then(() => {
    throw new Error('Something failed');
        
    console.log('Do this');
})
.catch(() => {
    console.error('Do that');
})
.then(() => {
    console.log('Do this, no matter what happened before');
});

//OUTPUT 
// Initial
// Do that
// Do this, no matter what happened before
```

## VIDEO  https://www.youtube.com/watch?v=IHjzyhjKxtc
"Promise" to hold this in case you want to use it in the future. 
Second function relies on first function. Run first function, get the value, and add it into second function. 
`function(resolve, reject)`

FETCH: Use fetch to get data from APIs. `fetch("url goes here")`. Let fetch know it is JSON. Add `.then(function(response))`

```js

fetch("url goes here")
    .then(function(response){
    //response is the promise value with all the events and data that we want.
    return response.json();
    //it's still a promise. 
    }).then(function(repose){
        //usable data now 
        console.log(response);
    })

```

## JavaScript Promises in Sixteen Minutes FROM https://medium.com/quick-code/javascript-promises-in-twenty-minutes-3aac5b65b887
A promise is an executor/some kind of function we are using, has an internal state that we cannot access of alter directly, has a value, and is followed by `.then()`.

Promise constructor to make a promise. They let us control the code more. An array of promises, they are not reliant on the others passing. 

Problem with promises: there isn't a simply way to make the info from a resolved promise available globally. 


## https://web.dev/promises/
Promises simplify deferred and async computations 

**Terminology**:  
- fulfilled - the promise succeeded
- rejected - promise failed
- pending - not yet fulfilled or rejected 
- settled - has been fulfilled or rejected

## https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch
Fetch API - lets you fetch resources asynchronous across the network. 

- Fetch promise don't reject on HTTP error status
- fetch() can receive cross site cookies
- fetch wont send cookies

Sending request with credentials included:
credentials: 'include', 'same-origin', 'omit'. 

## That data looks so fetching on you: Understanding the JS Fetch API FROM https://itnext.io/that-data-looks-so-fetching-on-you-understanding-the-js-fetch-api-880eae0c8d25?gi=edde091f0c18
Fetch can go to any URL even your own site. 