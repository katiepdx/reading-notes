# JavaScript book, Ch. 10, “Error Handling & Debugging”
- The console and dev tools
- Common problems
- Handling errors

Understanding the order of execution can be helpful for when looking for the source of an error. 

**Execution Contents** 
- Execution context: Every statement in JS lives in one of these 3 contexts.
    - Global context: only one global context in any page.
    - Function context: Code run within a function. Each function has its own function context. 
    - Eval context: text executed like code in an internal function called `eval()`.

- Variable scope (global and function context deal with scope)
    - Global scope: a variable declared outside a function and can be used anywhere. 
    - Function-level scope: variable is declared in the function and only accessibly within the function. 

Javascript interpreter processes one code line at a time and stacks (or piles) when a statement needs data from another function. Functions can be dependant on another function, therefore cannot complete a task until another function has finished it's task. Once the function finished its task and has returned a value, it is removed from the stack. 

**Execution Content and Hoisting** 
Prepare: create variables, functions, arguments, etc.
Execute: Assign values to variables, reference functions and run their code, execute statements.

*Hoisting*: This is when you call a function BEFORE it has been declared. Hoisting works when the first statement and the function are in the same execution context. 
```js
//Hoisting OK example
let greeting = greetUser();
function greetUser() {
    //create greeting
};

// NOT OK Hoisting example
let greeting = greetUser();
function getName() {
    function greetUser() {
        //create greeting
    }
    //return name with greeting
}
```

In Javascript, it will throw an error then an exception. Then, the interpreter will stop and look for *exception-handling* code. The exception-handling code should tell the user where the problem is. 

**Error Objects** Help us find the location of the mistakes. The browser dev tools also help. 
- Error Object (properties)
    - PROPERTY - DESCRIPTION
    - `name` Type of error
    - `message` Description
    - `fileNumber` Name of the JS file 
    - `lineNumber` Line number of error

- 7 Built-in error objects in JS
    - OBJECT DESCRIPTION 
    - `Error` Generic error
    - `SyntaxError` Syntax has not been followed 
    - `ReferenceError` Tried to reference a variable that is not declared or within scope
    - `TypeError` Unexpected data type that cannot be coerced 
    - `RangeError` Numbers not in acceptable range. `NaN` Not a Number error. 
    - `URIError` encodeURI(), decodeURI(), and similar methods incorrectly used
    - `EvalError` eval() function used incorrectly 

#### How to Deal with Errors
After identifying the error and how the browser is treating them, do the following...
- Debug the script to fix errors: (chrome) dev tools help wit this
- Handle errors gracefully: using `try`, `catch`, `throw`, and `finally` statements.

**Debugging Workflow** 
- Where is the problem? 
    - Use breakpoints and dev tools. Inspect the values.
- What is the problem exactly?
    - Breakdown or breakout parts of code and test the functionality of them in smaller parts.

**Console and Dev Tools**
Look for dev tools in the browsers. You can type code into console. To clear console hit clear. In Chrome, to clear hit the no-entry sign or type `clear()`. Logging (`console.log()`) data can be helpful to check you are getting the expected values or to find problems. 

#### Console
- Console methods
    - `console.info()` used for general information
    - `console.warn()` used for warnings
    - `console.error() `used for holding errors 

- Grouping methods 
    - `console.group()` used for grouping messages 

        ```js
        //group example
        //start group
        console.group('Area calculations');
            // write out the width 
            console.info('Width ', width);
            // write out the height
            console.info('Height', height);
            //write out the area
            console.log(area);
        //end group
        console.groupEnd();
        ```

- `console.table()` method is used to out a table showing objects, arrays that contain other objects for arrays. Ex. contacts object. `console.table(contacts)` will put all the data from the contacts object into a nice table (e.g., Index, tel num, country). 
- `console.assert()` -used to test if a condition is met and is only logged to the console if it evaluates to false. 
- Breakpoints in the sources stop code at a certain line. Can drop multiple breakpoints and move through code one point at a time. HOver over a variable and you can see what values are stored to it at that given time. 
    - Breakpoint buttons 
        - 1st button - Pause to pase at a breakpoint. 
        - 2nd button - Play button to go/step through the lines.
        - 3rd button - Step into a function call  
        - 4th button - Step out of the function you just stepped into.  
    - Conditional breakpoints 
        - Inc Chrome, select "add conditional breakpoint" and it will only stop at that line if the condition is true. 
- `debugger;` keyword in VSCode. Can add this to stop the code in dev tools. 

**Handling Exceptions**
`Try`, `catch`, and `finally` are useful for if you know the code might fail. Used together. 

```js
try {
    //try to execute this code
} catch (exception) {
    //if there is an exception, run this code
} finally {
    //this will always get executed
};
```

**Throwing Errors**
If you think there might be a problem, you can create an error by using `throw new Error('descriptive error message here');` 

**Common Errors when working with third parties**
- JSON that contain s a formatting error 
- Numeric data that occasionally isn't a numeric value 
- Error from remote server 
- Missing value in an information set

**Throwing Errors For NaN (Not a Number)**
If you need a number and you think a user might enter a string, you can have a error ready that will notify the user to enter a number. This prevents issues from happening in other parts of the code if user knows the error earlier. Two errors are displayed. One of the page for hte user and one in the dev tools console for developers. 

#### Debugging Tips
- Try another browser and see if error still occurs. Some are browser specific.
- Add numbers to the console and see which item is logged. See how far the code gets. 
- Strip it back - remove (comment out) parts of code to the minimum needed amount and see what runs. 
- Explain the code - talk it out with someone else. 
- Search - try Stack Overflow or other Q&A sites or do a Google search
- Code Playgrounds forums
- Validation tools 
    - Javascript
        -  http://www.jslint.com  
        -  http://www.jshint.com
    - JSON 
        - http://www.jsonlint.com
    - JQUERY 
        - debugger plugin available for chrome in web store. 

#### Common Errors
- Go back to basics
    - check casing 
    - variable scope 
    - single vs double quotes match properly 
    - not using reserved keywords for variable names
    - escaped quotes in variable names
    - HTML values of id attributes are unique 

- Missed or Extra Characters 
    - check for extra and missing semicolons
    - commas are in correct areas
    - brackets are correctly placed (missing or extras?)
    - parenthesis are around conditions
    - undefined vs null
    - scripts have loaded
    - conflicts between script files 

- Data Type Issues
    - = vs ===
    - check switch statements 
