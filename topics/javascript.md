# JavaScript

## Basic JavaScript info

- JavaScript uses a two-pass compiler when executing lines of code
  - meaning anytime we run JS in the browser, the browser will take two passes over our code
    - first pass builds up references to all of our code, declaring variables, functions, etc.
    - second pass applies values to the references that were found in the first pass, thus actually running the code

## Variables in JavaScript

### var
- function scoped, meaning the variable is only available inside of the function they are created in, unless the variable is declared globally.
- hoisted
- can be reassigned or overridden i.e redefined or updated

- Example of variable scope
![Variable Scope in JavaScript](../js-images/variable-scoping.png)

### let
- block scoped
- not hoisted
- can be reassigned, but NOT overridden

### const
- block scoped
- not hoisted
- immutable, cannot be reassigned or overridden
- the most strict of all variable keywords in JS, meaning it has the most rules applied 

### A Comparison of Variables
![Comparison of Variables in JavaScript](../js-images/jsvariablecomparison.png)

## Helpful Variable Info

- A great example of what a block is in JavaScript
```
function tester() {
  console.log('Hello from tester function');
}
// anything inside of curly brackets { } is a block
```
- Any time you see curly brackets { }, that's a block. 
  - Functions are also blocks
  - let and const are still going to be scoped to a function
  - when variables are declared inside of functions or other elements, they will be scoped to the closest set of curly brackets { }

### Lambda School Rule of Thumb
- When defining/declaring variables, use const until you can't, then use let

## Functions in JavaScript

- We have <strong>function declarations</strong>, <strong>function expressions</strong>, <strong>arrow functions</strong>
- Invoke a function means to call the function
- When we invoke a function, we often pass in values as well.
  - these values are known as arguments
  - the function receives the arguments as parameters, in the order they were called
- this is worth repeating, <strong>arguments are values that are passed into a function, the function receives the arguments as parameters</strong>
- Functions create their own scope
  - 2 types of scope in JavaScript
    - Global
    - Local
- Functions are simply a set of instructions to complete a task
- Functions are a Type in JS, just like bolean, number, string, etc

### The return statement

- When you see a return statement, inside of a block of code within a function, <strong>anything written after a return statement will not execute</strong>
- This is because the return statement terminates the function after running the line of statements within it


## Function Declaration

- Function declarations are made up of several syntactical parts
  - the <strong>function</strong> keyword
  - the <strong>name</strong> of the function
  - optional parameters
  - the <strong>statements</strong> inside of the block of code { }

- example of a simple function declaration below

``` 
function add(a, b) {
  return a + b;
}

// invoke function add
console.log(add(5, 8));

// add is the function name, (a, b) are the parameters, (5, 8) are the arguments
``` 

### Function Declaration Hoisting

- Remember how JavaScript utilizes a two-pass compiler? Function declarations are defined in the first pass.
- Both variable and function declarations are hoisted to the top of the execution order, i.e. added to the top upon code execution
  - The concept of putting a variable/function higher in the execution order for later use is known as <strong>hoisting</strong>
  - variables/functions can be called before they are declared
  
## Function Expression

- Function expressions have unique differences when compared against function declarations. 
  - A variable is used to store the function for later use
    ``` 
    let testFunction = function(testParam) { 
      console.log('hi from testFunction'); 
    } 
    ```
  - Anonymous functions are used. Notice in the above code block how the function isn't actually named, meaning it is an anonymous function
    - Because we are using a named variable, we don't need to name our function. 
  - Function expressions are not hoisted. 
    - they can only be invoked after a definition has been placed in the execution order, i.e. the function will only run after invocation
  - Why use a function expression over a function declaration?
    - more control over code
    - since a function expression can't be hoisted, we can tell it <strong>when</strong> to do it's job easier
    - can place functions within functions easier without having to name them

## Arrow Functions

- Arrow functions are fancy looking function expressions, with a major feature removed, the <strong>this</strong> keyword

- basic arrow function expression syntax
```
const add = (a, b) => a + b;
const add = (a, b) => {
  return a + b;
}
// both are valid, arrow functions allow for more streamlined code
// be careful with how slim(streamlined) you get, readability is always important
```

### When not to use arrow functions

- Event handlers (unless the event handler is inside a class constructor)
- Object methods
- Prototype methods

## Closure in JavaScript

- Big part of JavaScript language, look at closure like <strong><i>"What data do I currently have access to in my program?"</i></strong>
- <strong>Closure simplified</strong> - a function enclosed in another function
- <strong>"Technical" closure</strong> - the combination of aa function, and the lexical environment within which that function was declared
  - lexical = surrounding state
- Inner functions have access to outer functions
- In JS, closure is created every time a function is created
  - the variables or functions declared within that function have the ability to <strong>reach outwards</strong> for context, but <strong>never inwards</strong> - see example below
- In JS, all functions are also closures
- example of closure in JS
```
const foo = 'bar';

function returnFoo() {
  let testingClosure = 'hi from inside returnFoo';
  return foo;
}

console.log(returnFoo());
// the code inside of returnFoo has access to the outer scope, returnFoo is reaching outside of it's own scope to find a variable named foo, since foo does not exist within returnFoo's scope 

console.log(testingClosure);
// will log 'testingClosure is not defined'
// remember, we can reach outwards for context, never inwards
```

- <strong>Simply put,</strong> if a function can't find a variable within it's own scope, the function will look outside of it's scope to find the variable
- this is what closure is all about

## Callback Functions in JavaScript

### What is a Callback Function?

- <strong>Simply put:</strong> Callback functions are just functions passed into other functions as arguments. A callback is a function that is to be executed, after another function has finished executing. Hence the name 'callback'

- <strong>Complexly put:</strong> In JavaScript, functions are objects. Functions can take other functions as arguments, and can be returned by other functions. 
  - Functions that do this are called <strong>Higher-Order functions</strong>
- Any function that is passed as an argument is called a <strong>callback function</strong>
- From <strong>MDN:</strong> A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

### About Callback Functions

- callbacks are a way to make sure certain code doesn't execute, until other code has finished executing.
- example of a callback function from MDN
```
function greeting(name) {
  alert('Hello ' + name)
}

function processUserInput(callback) {
  let name = prompt('Please enter your name');
  callback(name);
}

processUserInput(greeting);

// a bit confusing at first
// the above example is a synchronous callback, because it is executed immediately
```

