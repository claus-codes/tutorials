# JavaScript tutorial: from beginner to programmer
> This document is very much a work in progress and subject to change often based on feedback.
>
> If you find yourself struggling to understand the lessons or the assignments, please contact me so I can make improvements.

This tutorial aims to be a beginner friendly crash course to programming with [JavaScript](https://en.wikipedia.org/wiki/JavaScript) which is the language running in every Internet browser and powering the web as we know it.


## About this tutorial
This tutorial features N lessons each introducing you to new concepts. Each lesson is followed by an assignment which asks you to write some code.


### Lesson structure
Each lesson is broken into chapters that teach different concepts. As we are learning a programming language it is important to be able to distinguish between the different types of information presented.

Whenever you see text formatted `like this`, it means we are discussing about something in `programming terms`.

```js
console.log('This code is syntax highlighted.');
```
Like the one seen above, sample code is always followed by an explanation, and is always *syntax highlighted* which means different things have different colors based on semantic rules. JavaScript, like all programming languages, is very strict about syntax, which is the set of rules that govern the structure of a language.

```
if (condition) {
  ...
}
```
*Syntax examples* teach you how JavaScript code is structured with an example of syntax, always followed by an explanation. Unlike sample code syntax examples are *never* syntax highlighted as they are not actual code.

Lessons feature the following recurrent sections at the end:

#### Summary
> The Summary section contains a list of links to documentation for the things discussed during the lesson, with a short description of each. The documentation contains more information and sample code, so be curious and explore.

#### Useful things
> Useful things did not have a good place in the tutorial, but are things you *should* know about.


### Assignments
The assignments after each lesson are designed to use new and previously learned information. They ask you to write new code, or modify code written during previous assignments.

Assignments can have multiple tasks for you to complete, which may be broken into smaller steps. The tasks and steps should be completed in the order they are presented.


### Workflow
This tutorial is intended to be used with [CodePen](https://codepen.io/pen/) which offers a free coding playground, where you can write code that runs and saves automatically.

We use the *developer console* exclusively for displaying information so you can keep track of what's happening. You can open the developer console in **CodePen** from the **bottom-left corner** of the workspace from the *"Console"* button.

Sample code provided in each lesson can be copied to the editor and will work **unless** it specifically mentions *throwing an Error*. Copying the sample code is not necessary as the expected output is shown as *comments* in most cases. You will soon learn about comments in [Lesson 1](#lesson-1-hello-world).


---


## Lesson 1: Hello World!
All software is just data processing and manipulation. Let me introduce you to two primitive data types found in JavaScript:

#### [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
> The `Number` data type represents *any real numbers* like `42`, `3.14159` or `-1000000`.

#### [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
> The `String` data type represents sequences of characters.  
> They are commonly wrapped in quotes like `'single'`, or `"double"`.  
> This tutorial uses double-quotes when discussing string values, and single-quotes when used in sample code.

### A humble beginning
```
functionName(parameter, parameter)
```
This is the syntax example for a **function call**; it starts with the *name of the function* followed with an opening parenthesis `(`, an *optional* list of *parameters* separated by comma `,` with a closing parenthesis `)` at the end.

```js
console.log('Hello World!');
```
The first part, [`console.log`](https://developer.mozilla.org/en-US/docs/Web/API/console/log), is the name of a built-in function in JavaScript that lets us write, or *log*, to the developer console. It gets passed a single parameter: `String` value of `"Hello World!"`.

The trailing semicolon `;` after a statement is *entirely optional* in JavaScript. Their use is recommended as code can break in unexpected ways when you do not include them. This tutorial includes them in sample code but not in syntax examples.

[Lesson 3](#lesson-3-functions) is dedicated to functions but for now think of a function as code that can be called with or without parameters.


### Comments
```js
console.log('Hello again!'); // "Hello again!"
```
In this example `// "Hello again!"` is the comment. Anything written after a double backslash `//` is interpreted as not being part of the executable code in JavaScript.

During most of this tutorial the output of `console.log()` will have the output as a comment next to the call, or a description of the output.

```js
/* this is
   a multi-line
   comment */
```
JavaScript also supports multi-line comments, started with `/*`, and terminated with a pairing `*/`.

It's good practice to comment your code and explain what is happening. It can be a very valuable learning tool, and a potential favor to anyone who might have to try to understand your code later.


### Summary
- [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) is a primitive data type that represents a numeric value.
- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) is a primitive data type that represents a sequence of characters.
- [`console.log()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/log) logs all parameters from each call made to it and is incredibly useful for figuring out what is happening.


### Assignment 1
The first assignment is an easy one:

> Write code that calls `console.log()` with your own message.


---


## Lesson 2: Values, variables and expressions
To store and manipulate values, like `Number` or `String`, we need to use variables. Variables are like boxes with a label that can contain a single thing: a value.

```
let variableName = expression
```
Variables are declared with the keyword [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), followed by the name of the variable, followed by an *optional* [Assignment `=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) operation to set an initial value which is evaluated from the *expression*. Expressions are explained later in this lesson.

```js
let num = 9;
let text = 'piece of text';
```
The code above declares two variables:
- `num` is assigned `Number` value of `9`.
- `text` is assigned `String` value of `"piece of text"`.

```
let variableName = expression,
    variableName = expression
```
Multiple variables can be defined with a single `let` keyword by separating each variable declaration with a comma `,`.

### Empty values
```js
let emptyVar;
console.log(emptyVar); // undefined
```
Variables can be declared with assigning an initial value. The variable `emptyVar` gets a special *empty value* called [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined), which means it has not been given a value.

Empty values are discussed more in [Lesson 4](#lesson-4-booleans-comparisons-and-conditional-operations).


### Constant values
```js
const immutableValue = 'I cannot be overwritten';
immutableValue = 'this will not work'; // This line will throw an Error
```
The [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) keyword creates a constant value, which acts like a variable but it's value cannot be changed after it's declaration.

When it is known that a value will not change during execution, it is preferred to use `const` over `let`.


### Logging variables
```js
console.log('Value of num', num); // "Number" 9
console.log('Value of text', text); // "Message" "string value"
```
Variables can be used as parameters just like `Number` and `String` values. It is good practice to add some context before when *logging* values as it's easy to lose track of what value is relevant in the logs if there is a lot of output.

For the sake of readability I will omit the context messages going forward.


### Changing the value of a variable
```js
text = 'JavaScript';
console.log('Value of text after change', text) // "JavaScript"

num = num * 3;
console.log('After multiplication', num); // 27
```
Variables can have their value changed by assigning them a new value.

Variable `text` is assigned a new `String` value of `"JS"`, after which the new value is logged to see it is changed.

Variable `num` is assigned `num * 3`, an *expression*, which evaluates to the `Number` value of `27` as the value of `num` was `9` before evaluation.


### Expressions
```js
console.log('Nice', 23 * 3); // 69
```
The code above calls `console.log()` again, but this time it gets passed the *expression* `23 * 3` instead of a single value or variable. It is a multiplication operation on numbers 23 and 3 which evaluates to `Number` value of `69`.

When referring to a value, a variable or an operation in code you are using an expression. Simply put: *expressions are pieces of code that return a value.*

`Number` values can be used to perform calculations using various mathematical operators.

#### [Addition `+`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition)
> The addition operator adds numbers together, producing a sum of values.  
> `1 + 2` = `3` 

#### [Subtraction `-`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction)
> The subtraction operator subtracts two numbers from one another, producing their difference.  
> `2 - 1` = `1`

#### [Multiplication `*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication)
> The multiplication operator multiplies numbers, producing the product of the numbers.  
> `3 * 3` = `9`

#### [Division `/`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division)
> The division operator divides the left number, the dividend, with the right, the divisor.  
> `9 / 3` = `3`

#### [Remainder `%`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder)
> The remainder operator returns the remainder left over when left number is divided with right number.  
> `83 % 10` = `3`, because `83 / 10` = `8` with `3` as the remainder.  
> 
> `4 % 2` = `0`, because `4` is an even number, while odd numbers would produce `1`.

#### [Exponentation `**`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)
> The exponentation operator returns the result of raising left number to the power of the right number.  
> `3 ** 2` = `9` because `3 * 3` = `9`  
> 
> `10 ** 3` = `1000` because: `10 * 10 * 10` = `1000`

```js
console.log('Complex calculation', (11 * 367) - (num * 100)); // 1337
```
Parenthesis can be used to group operations together which helps writing complex calculations where maintaining a strict [order of operations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is necessary. Any expression inside a pair of matching parenthesis `()` is evaluated before other operations can take place.

> Expression `11 * 367` evaluates to `4037`.
> 
> Expression `num * 100` evaluates to `2700` as variable `num` has the value of `27`.  
>
> After the expressions inside parenthesis `()` are first evaluated to values `2700` and `4037`, the remaining subtraction operation `4037 - 2700` produces the final result of `1337`:  
> `4037 - 2700` = `1337`.


### Not-a-Number
```js
const numberValue = 13;
const notNumberValue = 'hello';
console.log('Math fail', numberValue / notNumberValue); // NaN
```
When a mathematical operations are attempted with values that are not `Number` types, a special [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) value is used which stands for *Not-a-Number*.


### String interpolation
```js
let text1 = 'mb',
    text2 = 'ed',
    text3 = 'in',
    text4 = 'co';
console.log('Text can be', text4 + text1 + text2 + text3); // "combined" 
```
Instead of performing addition like on `Number` values, the addition `+` operator with `String` values joins them together.

```js
console.log(`${text} is amazing`); // "JavaScript is amazing" 
```
The backtick `` ` `` syntax declares a [template literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) which allows values to be inserted inside a `String` by wrapping the value with `${expression}`, like `${name}` in the sample code.

```js
let title = 'My Website';
let multiLineText = 'two\nlines';
let templateLiteralString = `
<!DOCTYPE html>
<html>
<head>
  <title>${title}</title>
</head>
<body>
  <pre>${multiLineText}</pre>  
</body>
</html>
`;
console.log(templateLiteralString); // filled template
```
Line-breaks in normal strings are signified with the *escape-character* `\n`, while template literals use existing line breaks in the code.


### Naming variables

```js
let variable_with_underscores = 'This is called snake_case';
let variableWithCapitals = 'This is called camelCase';
let VARIABLE_WITH_UPPER_CASE = 'ALL CAPS AAAHHHH!!!!';
```
Variables can be named almost anything with a few restrictions; a variable's name cannot start with a number and should be alpha-numeric, or the underscore `_` character.

What styles of naming *you* adopt does not matter as it is a personal preference. More importantly you should always strive to be as descriptive as possible when naming things, as it can help make the program logic easier to follow and reason about.


### Summary
- [Variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables) are containers for values defined with the [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) keyword.
- [Assignment `=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) is used to assign a value to a variable.
- [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is a primitive value that means no value has been assigned.
- [`const` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) is used to define constant values which cannot be changed.
- [Remainder `%` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder) returns the remainder left over from a division. 
- [Exponentiation `**` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation) returns the result of raising a number to the power of another number.
- [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is a concept from classic mathematics about the order in which calculations should be evaluated.
- [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) is a value that is produced as the result from mathematical operations with values that are not `Number` types.
 - [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) make it easy to construct complex `String` values.


### Useful things
- TODO


### Assignment 2
In this assignment you will work with variables, expressions and template literals.


#### Task 1: "Hello world" with string interpolation
Template literals introduced in this lesson can be used to inject values inside `String` variables.

##### Step 1
> Define a variable named `greeting`.  
> Assign it a `String` value that is a greeting like `"Hello`.

##### Step 2
> Define a variable named `name`.  
> Assign it your own name as a `String` value.

##### Step 3
> Call `console.log()` and use template literals to inject `greeting` and `name` to the output.  
> The console should log out `"Hello Claus!"`, where `"Claus"` is your name.


#### Task 2: Financial transaction
In this task you will define variables and perform calculations on them using expressions.

##### Step 1
> Define a variable named `price`.  
> Assign it any `Number` value above zero `0`.

##### Step 2
> Define a variable named `money`.  
> Assign it a `Number` value higher than the value of `price`.

##### Step 3
> Define a variable named `affordAmount`.  
> Assign it an expression that divides `money` by `price`.

##### Step 4
> Define a variable named `change`.  
> Assign it the expression of getting the *remainder* of dividing `money` by `price`.

##### Step 5
> Define a variable named `itemAmount`.  
> Assign it an expression where you first subtract `change` from `money`, then divide the result with `price`.

##### Step 6
> Define a variable named `totalPrice`.  
> Assign it an expression where you multiply `itemAmount` with `price`.

##### Step 7
> Call `console.log()` to inspect the values of the variables you defined.  
> Use template literals to make it look nice.

##### Step 8
> Change the value of `money` with an expression where `totalPrice` is subtracted from `money`.

##### Step 9
> Call `console.log()` to inspect the new value of `money`, which should be equal to the value of `change`.  
> Use template literals again to format the output.


---


## Lesson 3: Functions
As mentioned in [Lesson 1](#lesson-1-hello-world), a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) is essentially a block of code that can be called with parameters.

```
function functionName(parameters) {
  ...
  return expression
}
```
New functions are declared with a [`function` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function), followed by the name of the function. Similar to calling a function with parameters, there is an opening parenthesis `(`, an *optional* list of parameters separated by comma `,` and a closing parenthesis `)`.

Next is an opening curly bracket `{` that starts the *function body*. The `...` inside the function body signifies that your code goes here.

The function ends with an *optional* [`return`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return) statement followed by an expression for the return value. The function body ends with a closing curly bracket `}`.

```js
function addNumbers(a, b) {
  return a + b;
}
```
The code above defines a new function named `addNumbers` that expects two parameters: `a` and `b`. Parameters are variables that are used to receive input values. These input values, also known as arguments, are passed to the function when it is called. Inside the function body is a return statement that evaluates the expression `a + b`, returning the sum of `a` and `b`.


### Parameters and values
```js
let firstNumber = 12;
let secondNumber = 30;
let sum = addNumbers(firstNumber, secondNumber);
console.log('Return value of addNumbers()', sum); // 42
```
The code above first defines two variables: `firstNumber` and `secondNumber`.  
Both are assigned `Number` values.

A third variable `sum` is declared, and assigned the return value of `addNumbers(firstNumber, secondNumber)`.

Inside `addNumbers()` parameter `a` receives the value `12`, parameter `b` receives the value `30`, and the function returns the sum of the values which is `42`.


### Documenting your code
```js
/**
 * Adds two numbers together.
 * @param {number} a - First number
 * @param {number} b - Second number
 * @return {number} The sum of two numbers
 **/
function addNumbers(a, b) {
  return a + b;
}

/**
 * This is very important number.
 * @type {number}
 **/
let important = 42;
```
This oddly formatted block-level comment before the `addNumbers()` function and variable `important` is called [JSDoc](https://jsdoc.app). It is a standard way to write descriptions for JavaScript code and there are tools that generate documentation from annotated code like this.

Good documentation can be invaluable as projects or teams grow in size and complexity.


### Default parameters
```
function functionName(requiredParameter, optionalParameter = value) {
  ...
  return expression
}
```
Some functions are often called with the same parameters. Parameters can be assigned a default value, like `optionalParameter` above, which make them optional. Optional parameters are always defined after parameters which do not have a default value.

```js
/**
 * Rounds a number to an arbitrary decimal precision.
 * @param {number} value - The number to be rounded
 * @param {number} precision - The number of decimal places
 * @return {number} Rounded number
 **/
function roundNumber(value, precision = 2) {
  const precisionFactor = 10 ** precision;
  return Math.floor(value * precisionFactor) / precisionFactor;
}
```
Function `roundNumber()` defined above accepts two parameters:
- `value` which is required because it has no default value.
- `precision` which is optional because it has a default value of `2`. 

```js
const PI = 3.14159265;
console.log('PI with 4 decimals', roundNumber(PI, 4)); // 3.1415
console.log('PI with 2 decimals', roundNumber(PI)); // 3.14
```
The first call to `roundNumber()` above passes the value `4` as parameter `precision` resulting in a value with 4 decimal digits: `3.1415`

The second call omits the second parameter which sets the value of `precision` to `2` resulting in a value with 2 decimal digits: `3.14`

### Functions as values
```
variable = function(parameters) {
  ...
}
```
Functions can be used as values with the [`function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The syntax is the same as [`function` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) except the function name can be omitted.

```js
let divide = function(dividend, divisor) {
  return dividend / divisor;
}
console.log('Result of divide()', divide(8022, 6)); // 1337 
```
Variable `divide` is assigned a function expression as a value. Variables behave like functions when their value is a function, and they can be called just the same.


### Arrow functions
```
(parameters) => expression
```
JavaScript has a compact alternative to a traditional function expression called the [arrow `function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions). The curly brackets `{}` normally surrounding the function body can be omitted, in which case the `return` keyword can be omitted as well.

Arrow functions are always used as values, and the expression after the fat arrow `=>` symbol evaluates to the return value.

```js
divide = (dividend, divisor) => dividend / divisor;
console.log('Result of divide()', divide(8022, 6)); // 1337
```
Both versions of `divide()` are functionally identical.

```
parameter => expression
```
If a single parameter is used, the parenthesis `()` can also be omitted.

```js
const square = number => number * number;
console.log(square(4)); // 16
```
The `square` variable contains a function that returns the value from expression `number * number`.

```
(parameters) => {
  ...
  return expression
}
```
Arrow functions `=>` support code blocks with the curly brackets `{}`, but require a `return` statement to return a value like regular functions.


### Higher-order functions
```js
function createPowerFunction(exponent) {
  return value => value ** exponent;
}
let powerOfTwo = createPowerFunction(2);
console.log('Power function', powerOfTwo(4)) // 16
```
Functions can *return* other functions. This is a very useful and powerful feature of JavaScript. It allows creating functions that can define, or override, the default parameters of other functions.

Function `createPowerFunction()` accepts a single parameter: `exponent`.

`createPowerFunction()` returns an arrow function that accepts a single parameter: `value`.

This arrow function returns the expression `value ** exponent`, where parameter `exponent` comes from the *scope* of `createPowerFunction()`. The concept of *scopes* is discussed in [Lesson N]().

Variable `powerOfTwo` is assigned the return value of `createPowerFunction(2)` which is an arrow function.

Calling `powerOfTwo()` then evaluates evaluates the expression `value ** 2`.

```js
function createLogFunction(logFunction) {
  return value => logFunction('Value', value)
}
let log = createLogFunction(console.log)
log(1234) // "Value" 1234
```
Functions can also *accept functions as parameters* and call them inside the function body.

Function `createLogFunction` accepts a single parameter: `logFunction`.

Variable `log` is assigned the return value of `createLogFunction(console.log)` which is an arrow function.

Calling `log()` evaluates to the expression `console.log('Value', value)` where `value` is the parameter accepted by `log()`.


### Summary
- [`function` declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) is used to create functions.
- [`function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function) is used to create a function as a value.
- [`return`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return) statement is used inside a function to return a value.
- [Arrow `function` expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) are a more compact way to define functions.
- [JSDoc](https://jsdoc.app/) is used to describe code in block-level comments.
- [JSDoc cheatsheet](https://devhints.io/jsdoc) is a quick reference guide to the syntax of JSDoc.


### Useful things
- 


### Assignment 3
In this assignment you will utilize your new knowledge of functions.


#### Task 1: Greeting function
Modify the code from [Task 1](#task-1-hello-world-with-string-interpolation) of Assignment 2: *"Hello world" with string interpolation*.

##### Step 1
> Write a new function `greet()` that accepts two parameters:  
> `name` that has no default value and is required.  
> `greeting` that has the default `String` value of `"Greetings"`.

##### Step 2
> Make the function `greet()` return the template literal that was passed to `console.log()` previously.

##### Step 3
> Pass the return values of `greet()` to `console.log()` when using different parameters.  
> Ensure the default value is used when the `greeting` parameter is omitted.


#### Task 2: Financial transaction functions
Modify the code from [Task 2](#task-2-financial-transaction) of Assignment 2: *Financial transaction*.

##### Step 1
> Write a new function `calculateAffordableItemCount()` which accepts two parameters: `price` and `money`.

##### Step 2
> Move the code from the *"Financial transaction"* task inside the function `calculateAffordableItemCount()`.
> 
> Modify the code so the values of `price` and `money` are the parameters, and not created with the `let` keyword.

##### Step 3
> Make `calculateAffordableItemCount()` return the value of `itemAmount`.

##### Step 4
> Write a new function `calculateTotalPrice()` which accepts two parameters: `price` and `amount`.  
> The function should return the result of multiplying `price` with `amount`.

##### Step 5
> Define the variables `price` and `money` again outside of the functions.  
> Assign them `Number` values, like you did previously.

##### Step 6
> Define a variable named `itemCount`.  
> Assign it the return value of `calculateAffordableItemCount()` with `price` and `money` as the parameters.

##### Step 7
> Define a variable named `totalPrice`.  
> Assign it the return value of `calculateTotalPrice()` with `price` and `itemCount` as the parameters.

##### Step 8
> Define a variable named `moneyAfter`.  
> Assign it an expression where you subtract `totalPrice` from `money`.

##### Step 9
> Call `console.log()` to inspect the variables defined after Step 5.  
> Use template literals to format the output, detailing the transaction.


---


## Lesson 4: Boolean values, comparisons and conditional operations
There is a third important primitive data type.

#### [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
> The `Boolean` data type has only two possible values: `true` and `false`.

```js
console.log('NOT true', !true); // false
console.log('NOT false', !false); // true 
```
`Boolean` values can be inversed with the [logical NOT `!` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT).

Comparison operations, discussed next, produce `Boolean` values when evaluated.


### Empty values and truthiness
The concept of empty values was touched mentioned in [Lesson 2](#lesson-2-values-and-variables) where 
when we learned about `undefined` which we can use to say something is actually nothing. Another way to do that in JavaScript is the `null` value.

The difference is that `undefined` happens when a value was not ever defined to begin with, and `null` is a value that someone purposefully uses to indicate a lack of value.

```js
false
0 // (zero)
'' // (empty string)
""
``
null
undefined
NaN // Not a Number
```
All of the values in the list above are always *"falsy"* which means they produce the `Boolean` value `false` when used as booleans.

All other values will always by *"truthy"* which means they produce the `Boolean` value `true` when used as booleans.


### Equality and sameness
```js
console.log(1 === 1); // true
console.log(1 !== 1); // false
```
It is recommended to use the [strict equality `===` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality) to check if two values are *equal*.

For the inverse the [strict inequality `!==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality) should be used to check if two values are *NOT equal*.

```js
// Equality
console.log(1 == '1'); // true
console.log(1 != '1'); // false

// Strict equality
console.log(1 === '1'); // false
console.log(1 !== '1'); // true
```
JavaScript has *non-strict* equality operators which *do not check the type* of the values being compared.

The above code first uses the [equality `==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) and the [inequality `!=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality) to compare a `Number` value of `1` to a `String` value of `"1"`, which are *the same*. They are considered equal because these operators not compare the *type* of a value.

This can lead to strange side effects, and so their use is discouraged. Using the *strict* equality operators is recommended as they are *type safe*.

### Comparing numbers
```js
console.log(4 > 3); // greater than, true
console.log(3 >= 3); // greater than or equals, true

console.log(4 < 3); // false, less than
console.log(4 <= 3); // false, less than or equals
```
`Number` values can be compared to each other with using comparison operators.

#### [Greater than `>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than)
> The "greater than" operator returns `true` if the left value is greater than the right value, and `false` otherwise.

#### [Greater than or equal `>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal)
> The "greater than or equal" operator returns `true` if the left value is greater than or equal to the right value, and `false` otherwise.

#### [Less than `<`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than)
> The "less than" operator returns `true` if the left value is less than the right value, and `false` otherwise.

#### [Less than or equal `<=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than_or_equal)
> The "less than or equal" operator returns `true` if the left value is less than or equal to the right value, and `false` otherwise.


### Conditional execution of code
```
if (condition) {
  ...
}
else {
  ...
}
```
A major part of software is *conditional execution of code*. The [`if...else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) statement allows execution of code when the *condition*, which is an expression, evaluates as `true`.

Conditional execution starts with the `if` keyword, followed by an opening parenthesis `(`, a condition expression, and a closing parenthesis `)`.

Next is an opening curly bracket `{` that starts a code block. The `...` signifies that code can be placed here. Code block ends with a matching closing curly bracket `}`.

An *optional* `else` block will execute if the condition expression evaluates as `false`.

```js
if ('value' === 'value') {
  console.log('Values are equal'); // "Values are equal"
}
if (1 !== 1) {
  console.log('This is never called because 1 === 1');
}
```
The code above will execute the first `console.log()` call, but not second.

```
if (condition) {
  ...
}
else if (condition) {
  ...
}
else {
  ...
}
```
Multiple `if...else` statements can be nested to create an `else if` clause that will execute the first code block where the condition evaluates as true, or the *optional* `else` block if one exists.

```js
if (false) {
  console.log('If');
}
else if (false) {
  console.log('Else if');
}
else {
  console.log('Else'); // "Else"
}
```
Because both `if` and `else if` conditions evaluate to `false`, the `else` block is executed.


### Ternary operator
```
condition ? trueExpression : falseExpression
```
The [Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) allows for a shorter way to perform simple `if...else` operations. It behaves like a conditional expression.

TODO: write about the syntax

If the `condition` evaluates as `true`, the `trueExpression` is evaluated, otherwise `falseExpression` is evaluated.

```js
let conditionalVar = 3 === 4 ? 'Yay' : 'Nah';
console.log('False expression', conditionalVar); // "Nah"
```
The variable `conditionalVar` receives the value `"Nah"` as the expression `3 === 4` evaluates as `false`.

```js
conditionalVar = 4 === 4
  ? 'Yay'
  : 'Nah';
console.log('True expression', conditionalVar); // "Yay"
```
Using white space can help readability.


### Logical operators
```
expression && expression
```
Using the [logical AND `&&` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND) it is possible to chain *truthiness* checks into a *combined expression* which are evaluated sequentially, and *return* a value *for* the combined expression.

The conditions evaluate left to right, and if a *falsy* value is encountered the combined expression returns that *falsy* value. Otherwise the last *truthy* value is returned.

```js
console.log(true && true); // true
console.log(true && false); // false (in any order)
console.log(false && false); // false
```
Above is a the *truth table* for the AND `&&` operator with the different combinations of `Boolean` values, and what they evaluate as. 

```
expression || expression
```
With the [logical OR `||` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR) conditions evaluate left to right, and if a *truthy* value is encountered the combined expression returns that *truthy* value. Otherwise it returns `false`.

```js
console.log(true || true) // true
console.log(true || false) // true (in any order)
console.log(false || false) // false
```
Above is a the *truth table* for the OR `||` operator with the different combinations of `Boolean` values, and what they evaluate as.


### Summary
- [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) is a primitive data type that can be `true` or `false`.
- [Logical NOT `!` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT) inverses the value of a `Boolean`.
- [Equality `==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) checks if two values are the same, but does not care about type.
- [Strict equality `===` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality) checks if two values are equal while being *type safe*.
- [Inequality `!=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality) checks for if two values are NOT the same, but does not care about type.
- [Strict inequality `!==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality) checks if two values are NOT equal while being *type safe*. 
- [Greater than `>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than) TODO
- [Greater than or equal `>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal) TODO
- [Less than `<`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than) TODO
- [Less than or equal `<=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than_or_equal) TODO
- [`if...else` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) TODO
- [Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) TODO
- [Logical AND `&&` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND) TODO
- [logical OR `||` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR) TODO


### Useful things
- 


### Assignment 4: TODO


#### Extra credit
-


---


## Lesson 5: Arrays and loops

Sometimes you want to store more than a single value in a variable, and JavaScript offers two different solution to this problem. The first we will look at in this lesson is called an `Array`.

```js
const countries = ['Finland', 'Canada', 'Iceland']
console.log(countries[0]) // "Finland"
console.log(countries[1]) // "Canada"
console.log(countries[2]) // "Iceland"
```
An `Array` is an ordered list of values. The easiest way to define an array is to wrap the elements between hard brackets `[]`. To access an element at a specific index of an array we use hard brackets with an index `[0]` after the name of the array, counting from zero `0` upwards. The `countries` array contains `String` values.

```js
console.log(countries.length) // 3
```
Arrays have a property `length`, that is a `Number` value that equals to the amount of items in the array. The maximum index in an array is always `length - 1`.


### Adding and removing values

```js
countries.push('Russia')
console.log(countries) // ["Finland", "Canada", "Iceland", "Russia"]

let removedCountry = countries.pop()
console.log(countries) // ["Finland", "Canada", "Iceland"]

countries.unshift(removedCountry)
console.log(countries) // ["Russia", "Finland", "Canada", "Iceland"]

removedCountry = countries.shift()
console.log(countries) // ["Finland", "Canada", "Iceland"]
```
To add new elements to the end of an array we can use `Array.push()` method and to remove the last element and return it's value we can use `Array.pop()` method.

To add elements to the beginning of an array we can use `Array.unshift()` method, and to remove the first element and return it's value we can use `Array.shift()` method.


### Splicing values in and out an array

```js
countries.splice(1, 0, 'Egypt')
console.log(countries) // ["Finland", "Egypt", "Canada", "Iceland"]

const removedCountries = countries.splice(1, 2)
console.log(removedCountries) // ["Egypt", "Canada"]
console.log(countries) // ["Finland", "Iceland"]

countries.splice(2, 0, 'Norway', 'Denmark')
console.log(countries) // ["Finland", "Norway", "Denmark", "Iceland"]
```
There are more ways to manipulate arrays than simply adding or removing elements to the beginning or end of an array. `Array.splice()` lets you pick an index in an array and remove and/or add items at that location.

We first splice in `'Egypt'` at index `1`. We then call `countries.splice(1, 2)` to splice out 2 elements from index 1. We finally splice in `'Norway'` and `'Denmark'` at index 2.


### Cloning an array

```js
let countriesClone = Array.from(countries)
console.log('These are the same instance', countries === countriesClone) // false
```
You can clone an array using `Array.from()` which accepts any iteratable data type as a parameter. You can also clone with the spread `...` operator, but we will touch that at a later part of the tutorial.


### Enter the loop

```js
for (let index = 0; index < countries.length; index++) {
  const country = countries[index]
  console.log(country) // "Finland", "Norway", "Denmark" and "Iceland" in sequence
}
```
You will often find yourself needing to repeat some code. For these cases we usually use something like the `for`-loop.

The keyword `for` is followed by a pair of parenthesis `()`. Inside the parenthesis are three optional expressions separated by semicolons `;`

**Initialization**
: Evaluated once before the loop begins. This is where we set up any variables we might use in the loop, like `index` which we gave the value of zero `0` as we plan to count indices upwards.

**Condition**
: Evaluated once before each loop iteration. If the expression evaluates to `Boolean` value of `true`, the code inside the loop is executed and if the expression evaluates to `Boolean` value of `false`, the loop ends. With `index < countries.length` we are checking if `index` is smaller than the `length` property of the `countries` array. This evaluates as `Boolean` value of `true` until `index` has a value of `countries.length - 1` which is the maximum index we can access.

**Afterthought**
: Evaluated at the end of loop iteration. Here we usually update our counters. The expression `i++` is using the increment `++` operator, increading the value of `index` by 1.

After the loop definition we have a block of code inside curly braces `{}` that gets executed every iteration. We define a constant value `country` that has the value of the item at `index` on the `countries` array, which we then log to console.

```js
for (const country of countries) {
  console.log(country) // "Finland", "Norway", "Denmark" and "Iceland" in sequence
}
```
There are a few different forms of `for` loops. Using `for` and `of` keywords we more easily go through the values in an `Array` if we have no use for index.

```js
let counter = 1
while (counter <= 10) {
  console.log('while', counter) // "while" 1...10
  counter += 1
}

counter = 1
do {
  console.log('do while', counter) // "do while" 1...10
  counter++
} while (counter <= 10)
```
Other types of loops important to know are the `while` and `do...while`-loops. Each type of loop works slightly differently and have their use cases.


### Summary
- [`Array` type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [`Array.push`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
- [`Array.pop`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
- [`Array.unshift`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
- [`Array.shift`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
- [`Array.splice`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
- [`for` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
- [`while` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
- [`do...while` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
- [Increment `++` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment)


### Useful things
- 


### Assignment 5: Create an array of numbers, and remove values from it

Write a function called `createNumberList()` that accepts a single parameter called `maximumNumber`. The function must return a new `Array` containing numbers going from `1` up to the value of `maximumNumber` in sequential order.

```js
const numbers = createNumberList(9)
console.log(numbers) // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
The function should produce the above result when called with the same parameter.

Write another function called `pluckElementFromArray()` that accepts two parameters; `array` and `index`. It should remove a single value from `array` at `index` and return the removed value.

Write logging for the return value of the `pluckElementFromArry()` call multiple times with different parameters. Log the value of `numbers` after that.


---


## Lesson 6: Math functions

JavaScript comes with several built-in *global objects* that give us tools to solve problems with one of the most useful being `Math`.

```js
console.log(Math.floor(1.998)) // 1, round down
console.log(Math.round(1.500)) // 2
console.log(Math.ceil(1.001)) // 2, round up
```
Some of the basic functionality in the `Math` object includes functions for rounding numbers.

```js
console.log(Math.random())
console.log(Math.random())
console.log(Math.random())
```
Sometimes we want to add random values to our code. `Math.random()` returns a new random `Number` value each time the function is called. The returned value is a fractional value between `0.0` an `1.0`.


### Summary
- [`Math.floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
- [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)
- [`Math.ceil()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil)
- [`Math.random()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)
- [`Math` object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)


### Useful things
- 

### Assignment 6: Generate random array indexes

Write a function called `getRandomIndex()` that accepts a single parameter called `array`. The function must return a random index from the `array` parameter.


---


## Lesson 7: Objects

The `Object` type in JavaScript lets us define more complex data structures by allowing us to aggregate data that has some kind of connection between them.

```js
const testObject = {
  textProperty: 'words are fun',
  numberProperty: 58008,
}
```
Objects definitions are `key: value` pairs inside curly brackets `{}` separated by commass `,`.

```js
console.log(testObject.textProperty) // "words are fun"
console.log(testObject['numberProperty']) // 58008
```
You can access an object's property by using the dot `.` notation, or by using the key inside hard brackets `[]`.

```js
let person = {
  name: 'John Smith',
  age: 27,
  address: {
    street: 'Fake street 1',
    postalCode: '12345',
    city: 'Faketown',
    country: 'Fantasyland',
  }
}
console.log(person.address.street) // "Fake street 1"
```
Because an object's property can have any value, we can quickly compose more complex structures by nesting objects, like `person` having property `address` that is also an object with it's own properties.

```js
const addressKey = 'postalCode'
console.log(person.address[addressKey]) // "12345"
```
As keys of properties are `String` values, we can access them flexibly by specifying the property name we want to access in a variable, and using that variable as the key inside hard brackets `[]`.


### Useful things

Object.keys(object)
: This returns all the keys inside an object as an array of `String` values.

Object.values(object)
: This returns all the values inside an object in an order that matches `Object.keys()`


### JSON

```js
const jsonString = JSON.stringify(exampleObject)
console.log(jsonString) // "{'property':'value','anotherProperty':2}"

const parsedObject = JSON.parse(jsonString)
console.log(parsedObject) // copy of exampleObject
```
JavaScript Object Notation, or JSON for short, is a way of representing data the same way JavaScript represents data. JSON is being used by most websites on the planet as it works seamlessly with JavaScript with the `JSON.stringify()` and `JSON.parse()` functions.

```js
const prettyJsonString = JSON.stringify(person, null, 2)
console.log(prettyJsonString) // person as formatted JSON
```
The `JSON.stringify()` function can format the values for better readability with the right parameters.


### Summary
- [`Object` type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [`JSON.stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)


### Assignment 7: TODO

TODO


---


## Lesson 8: Destructuring and the spread syntax

### Summary
- [Spread syntax `...`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

### Assignment 8: Lottery system part 3 - finishing up the number system

Write a function called `pluckRandomElementsFromArray()` that accepts two parameters; `array` and `count`. The function should return `count` number of random elements from `array` parameter.

Write another function called `pickLotteryNumbers()` that acceps two parameters; `array` and `count`. The function should work like `pluckRandomElementsFromArray()` but **not** modify the parameter `array` that was passed to it by cloning it.

Write code to generate a series of numbers, and then use `pickLotteryNumbers()` to select random numbers from the list.
