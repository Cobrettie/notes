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
    let testFunction = function(testParam) { console.log('hi from testFunction') }; 
    ```
  - Anonymous functions are used. Notice in the above code block how the function isn't actually named, meaning it is an anonymous function
  - Function expressions are not hoisted. 
    - they can only be invoked after a definition has been placed in the execution order