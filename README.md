# JavaScript: from beginner to programmer
> This document is very much a work in progress and subject to change often based on feedback.
>
> If you find yourself struggling to understand the lessons or the assignments, please contact me so I can make improvements.

This tutorial aims to be a beginner friendly crash course to programming with [JavaScript](https://en.wikipedia.org/wiki/JavaScript), which is the language running in every Internet browser and powering the web as we know it.


## Table of Contents
**[About this tutorial](#about-this-tutorial)**
- [Lesson structure](#lesson-structure)
- [Workflow](#workflow)

**[Lesson 1: Hello World!](#lesson-1-hello-world)**
- [A humble beginning](#a-humble-beginning)
- [Comments](#comments)

**[Lesson 2: Values, variables and expressions](#lesson-2-values-variables-and-expressions)**
- [Constants](#constants)
- [Empty values](#empty-values)
- [Variables as parameters](#variables-as-parameters)
- [Changing the value of a variable](#changing-the-value-of-a-variable)
- [Expressions](#expressions)
- [Not-a-Number](#not-a-number)
- [Joining strings](#joining-strings)
- [Template literals](#template-literals)
- [Checking the type of variables](#checking-the-type-of-variables)
- [Naming variables](#naming-variables)

**[Lesson 3: Functions](#lesson-3-functions)**
- [Parameters and values](#parameters-and-values)
- [Default parameters](#default-parameters)
- [Functions as values](#functions-as-values)
- [Arrow functions](#arrow-functions)
- [Scope](#scope)
- [Higher-order functions](#higher-order-functions)

**[Lesson 4: Boolean values, comparisons and conditional operations](#lesson-4-boolean-values-comparisons-and-conditional-operations)**
- [Empty values and truthiness](#empty-values-and-truthiness)
- [Equality and sameness](#equality-and-sameness)
- [Comparing numbers](#comparing-numbers)
- [Conditional execution of code](#conditional-execution-of-code)
- [Ternary operator](#ternary-operator)
- [Logical operators](#logical-operators)

**[Lesson 5: Objects](#lesson-5-objects)**
- [Accessing properties](#accessing-properties)
- [Nesting objects](#nesting-objects)
- [Object instances](#object-instances)
- [Iterating objects](#iterating-objects)
- [This](#this)
- [JSON](#json)

**[Lesson 6: Arrays and loops](#lesson-6-arrays-and-loops)**
- [Adding and removing values](#adding-and-removing-values)
- [Splicing values in and out an array](#splicing-values-in-and-out-an-array)
- [Loops](#loops)
- [Map](#map)
- [Filter](#filter)
- [Reduce](#reduce)
- [Cloning an array](#cloning-an-array)

**[Lesson 7: Built-in objects](#lesson-7-built-in-objects)**




## About this tutorial
This tutorial features N lessons, each introducing you to new concepts. The lesson is followed by a *Summary* and an *Assignment*.


### Lesson structure
Each lesson is broken into sections that teach different concepts. When learning a programming language it is important to be able to distinguish between the different types of information presented.

Whenever you see text formatted `like this`, it means we are discussing about something in `programming terms`.

#### Example code
```js
console.log('This example is syntax highlighted.');
```
Example code, like the one seen above, is always followed by an explanation and is <ins>always</ins> *syntax highlighted*. This means different things have different colors based on semantic rules.

JavaScript, like all programming languages, is very strict about syntax, which is the *set of rules that govern the structure of a language*.

#### Syntax example
```
if (condition) {
  ...
}
```
Syntax examples teach you how JavaScript code is structured with an example of the syntax, and are always followed by an explanation. Unlike example code they are <ins>never</ins> syntax highlighted as they are not *actual code*.

#### Summary
At the end of each lesson is the *Summary* section. This section contains a list of links to documentation for the things discussed during the lesson, with a short description of each to refresh your memory. The documentation contains more information and example code, so be curious and explore.

#### Assignment
After the *Summary* section is an *Assignment*. The assignments after each lesson are designed to use information taught so far. They ask you to write new code, or modify code written during previous assignments.

Assignments can have multiple *tasks*, which are broken into smaller *steps* so they are easier to follow. The tasks, and steps, should be completed in the order they are presented. Some tasks will include a *Show solution* part, which will reveal the solution for the task when clicked open - you should only view the solution as a last resort.


### Workflow
This tutorial is intended to be used with [CodePen](https://codepen.io/pen/) which offers a free coding playground, where you can write code that runs and saves automatically.

This tutorial uses the *developer console* exclusively for displaying information so you can keep track of what's happening. You can open the developer console in **CodePen** from the **bottom-left corner** of the workspace from the *"Console"* button.

Example code provided in each lesson can be copied to the editor in sequence and will work **unless** it specifically mentions *throwing an Error*. Copying the example code is not necessary as the expected output is shown as *comments* in most cases. You will soon learn about comments in [Lesson 1: Hello World!](#lesson-1-hello-world).

---

## Lesson 1: Hello World!
All software is just data processing and manipulation. Here are the first two primitive data types found in JavaScript:

[`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
> The `Number` data type represents any *real number* like `42`, `3.14159` or `-1000000`.

[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
> The `String` data type represents sequences of characters.
>  
> They are commonly wrapped in quotes like `'single'`, or `"double"`.
> 
> This tutorial uses single-quotes in example code, and double-quotes when discussing string values.


### A humble beginning
```
functionName(parameter, parameter)
```
This is the syntax example for a *function call*; it starts with the *name of the function* followed with an opening parenthesis `(`, an *optional* list of *parameters* separated by comma `,` with a closing parenthesis `)` at the end.

```js
console.log('Hello World!');
```
The first part, [`console.log`](https://developer.mozilla.org/en-US/docs/Web/API/Console/log), is the name of a built-in function in JavaScript that lets us write, or *log*, to the developer console. It gets passed a single parameter: `String` value of `"Hello World!"`.

The trailing semicolon `;` after a statement is *entirely optional* in JavaScript. Their use is recommended as code can break in unexpected ways when you do not include them. This tutorial includes them in example code, but not in syntax examples.

[Lesson 3: Functions](#lesson-3-functions) is dedicated to functions, but for now think of a function as code that can be called with parameters.


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
This first assignment is an easy one:

> Write code that calls `console.log()` with your own message.

---

## Lesson 2: Values, variables and expressions
To store and manipulate values, like `Number` or `String`, we need to use [variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables). Variables are like boxes with a label that can contain a single thing: *a value*.

```
let variableName = expression
```
Variables are declared with the keyword [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), followed by the name of the variable, followed by an *optional* [Assignment `=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) operation to set an initial value which is evaluated from the *expression*. Expressions are explained later in this lesson.

```js
let num = 9;
let text = 'piece of text';
```
This code declares two variables:
- `num`, which is assigned the `Number` value of `9`.
- `text`, which is assigned the `String` value of `"piece of text"`.

```
let variableName = expression,
    variableName = expression
```
Multiple variables can be defined with a single `let` keyword by separating each variable declaration with a comma `,`.


### Constants
```js
const immutableValue = 'I cannot be overwritten';
immutableValue = 'This will not work'; // This will throw an Error
```
The [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) keyword creates a *constant variable*, also know simply as a *constant*. A constant variable's value cannot be changed after it's declaration.

When it is known that a variable's value will not change during execution, it is preferred to use `const` over `let`.


### Empty values
```js
let emptyVar;
console.log(emptyVar); // undefined
```
Variables can be declared without an initial value. The variable `emptyVar` gets a special *empty value* called [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined), which means it has not been given a value.

Empty values are discussed in more detail in [Lesson 4: Boolean values, comparisons and conditional operations](#lesson-4-boolean-values-comparisons-and-conditional-operations).


### Variables as parameters
```js
console.log('Value of num', num); // "Number" 9
console.log('Value of text', text); // "Message" "string value"
```
Variables can be used as parameters just like raw `Number` and `String` values. It is good practice to add some context before when *logging* values with `console.log()`, as it's easy to lose track of what value is relevant in the logs if there is a lot of output.

For the sake of readability I will omit the context messages going forward.


### Changing the value of a variable
```js
text = 'JavaScript';
console.log('Value of text after change', text) // "JavaScript"

num = num * 3;
console.log('After multiplication', num); // 27
```
Variables can have their value changed by assigning them a new value.

Variable `text` is assigned a new `String` value of `"JavaScript"`, after which the new value is logged with `console.log()` to see it is changed.

Variable `num` is assigned `num * 3`, an *expression*, which evaluates to the `Number` value of `27` as the value of `num` was `9` before evaluation.


### Expressions
```js
console.log('Nice', 23 * 3); // 69
```
The code above calls `console.log()` again, but this time it gets passed the *expression* `23 * 3` instead of a single value or variable. It is a multiplication operation on numbers `23` and `3` which evaluates to `69`.

When referring to a value, a variable or an operation in code you are using an expression. Simply put: *expressions are pieces of code that return a value.*

`Number` values can be used to perform calculations using various mathematical operators.

[Addition `+`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition)
> The addition operator adds numbers together, producing a sum of values.  
> `1 + 2` = `3` 

[Subtraction `-`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction)
> The subtraction operator subtracts two numbers from one another, producing their difference.  
> `2 - 1` = `1`

[Multiplication `*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication)
> The multiplication operator multiplies numbers, producing the product of the numbers.  
> `3 * 3` = `9`

[Division `/`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division)
> The division operator divides the left number, the dividend, with the right, the divisor.  
> `9 / 3` = `3`

[Remainder `%`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder)
> The remainder operator returns the remainder left over when left number is divided with right number.  
> `83 % 10` = `3` because  
> `83 / 10` = `8` with `3` as the remainder.  
> 
> `4 % 2` = `0` because  
> `4 / 2` = `2` with `0` as the remainder.

[Exponentation `**`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)
> The exponentation operator returns the result of raising left number to the power of the right number.  
> `3 ** 2` = `9` because  
> `3 * 3` = `9`  
> 
> `10 ** 3` = `1000` because  
> `10 * 10 * 10` = `1000`

```js
console.log('Complex calculation', (11 * 367) - (num * 100)); // 1337
```
When writing complex calculations, where maintaining a strict *order of operations* with is necessary, parenthesis `()` can be used to group operations together along with [operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence).

Any expression inside a pair of matching parenthesis is evaluated *before* other operations are executed.

> Expression `(11 * 367)` evaluates to `4037`.
> 
> Expression `(num * 100)` evaluates to `2700` because variable `num` contains the value `27`.  
>
> The remaining subtraction operation produces the final value `1337`.    
> `4037 - 2700` = `1337`.


### Not-a-Number
```js
const numberValue = 13;
const notNumberValue = 'hello';
console.log('This is not a number', numberValue / notNumberValue); // NaN
```
When mathematical operations are attempted with values that are not `Number` values, a special [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) value is returned, which stands for *Not-a-Number*.


### Joining strings
```js
let text1 = 'mb',
    text2 = 'ed',
    text3 = 'in',
    text4 = 'co';
console.log('Text can be', text4 + text1 + text3 + text2); // "combined" 
```
Instead of performing addition like on `Number` values, the addition `+` operator with `String` values joins them together.

Variables `text1`, `text2`, `text3` and `text4` are defined, which all have a `String` value.

They are joined with the addition `+` operator in a *specific sequence*:
> `"co"` + `"mb"` + `"in"` + `"ed"` = `"combined"`.


### Template literals
```
`...${expression}...`
```
The backtick `` ` `` syntax declares a [template literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), a *fancy* `String`, which allows variables or expressions to be placed into placeholders. The `...` in the syntax example indicates any text.

Each placeholder begins with the dollar sing `$`, then an opening curly bracket `{` followed by the variable or expression, and ends with a closing curly bracket `}`.

```js
console.log(`${text} is amazing`); // "JavaScript is amazing" 
```
The variable `text` is inserted in the template literal with the placeholder `${text}`, which produces the `String` value of `"JavaScript is amazing"` when evaluated.

```js
const title = 'My Website';
const multiLineText = 'two\nlines';
const templateLiteralString = `
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
Constant `title` is assigned the value `"My website"`, and `multilineText` is assigned a string with an *escape character* `"\n"`, which means *new line* or *line break*. The value is `"two"` and `"lines"` separated by a new line.

Constant `templateLiteralString` is assigned a multi-line template literal. Template literals do not need the `"\n"` escape character, but rather uses the line breaks from the JavaScript code itself.

The definition begins and ends with the backtick `` ` `` character, and includes a small template which has both `title` and `multilineText` placed inside. When it is evaluated, the template is filled:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>
</head>
<body>
  <pre>two
lines</pre>
</body>
</html>
```
This output is syntax highlighted for *HTML* for the sake of clarity, and is <ins>not</ins> JavaScript code.


### Checking the type of variables
```js
console.log('Type of num', typeof num); // "number"
console.log('Type of text', typeof text); // "string"
console.log('Type of emptyVar', typeof emptyVar); // "undefined"
```
Each value in JavaScript has a type like `Number` or `String`. The [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) operator can be used to check the type of a value, which it returns as a `String` value like seen above.

There are more types in JavaScript that will be discussed in later lessons.


### Naming variables
```js
let variable_with_underscores = 'This is called snake_case';
let variableWithCapitals = 'This is called camelCase';
let VARIABLE_WITH_UPPER_CASE = 'ALL CAPS AAAHHHH!!!!';
```
Variables in JavaScript can be named almost anything with a few restrictions. A variable's name cannot start with a number and should be alpha-numeric, or the underscore `_` character.

> What styles of naming *you* adopt does not matter as it is a personal preference. More importantly you should always strive to be as descriptive as possible when naming things because it can help make the program logic easier to follow and reason about.


### Summary
- [Variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables) are containers for variables.
- [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) keyword is used to define variables.
- [Assignment `=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) is used to assign a value to a variable.
- [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is a primitive value that means no value has been assigned.
- [`const` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) is used to define constant variables which cannot be changed.
- [Remainder `%` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder) returns the remainder left over from a division. 
- [Exponentiation `**` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation) returns the result of raising a number to the power of another number.
- [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is a concept from classic mathematics about the order in which calculations should be evaluated.
- [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) is a value that is produced as the result from mathematical operations with values that are not `Number` types.
- [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) make it easy to construct complex `String` values.
- [`typeof` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) returns the *type* of a value as a `String`.


### Assignment 2
In this assignment you will work with variables, expressions and template literals.


#### Task 1: "Hello world" with template literals
Template literals introduced in this lesson can be used to inject variables or expressions inside `String` values.

##### Step 1
> Define a variable named `greeting`.  
> Assign it a `String` value that is a greeting like `"Hello`.

##### Step 2
> Define a variable named `name`.  
> Assign it your own name as a `String` value.

##### Step 3
> Call `console.log()` and use template literals to inject `greeting` and `name` to the output.
> 
> The console should log out something like `"Hello Claus!"`, where `"Hello"` is your greeting and `"Claus"` is your name.

<details>
  <summary>Show solution</summary>

```js
let greeting = 'Aloha';
let name = 'Anonymous';
console.log(`${greeting}, ${name}!`);
```
</details>


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
> Define a variable named `remainder`.  
> Assign it the expression of getting the *remainder* of dividing `money` by `price`.

##### Step 5
> Define a variable named `itemAmount`.  
> Assign it an expression, where you first subtract `remainder` from `money`, then divide the result with `price`.

##### Step 6
> Define a variable named `totalPrice`.  
> Assign it an expression where you multiply `itemAmount` with `price`.

##### Step 7
> Call `console.log()` to inspect the values of the variables you defined and use template literals to format the output.

##### Step 8
> Change the value of `money` with an expression where `totalPrice` is subtracted from `money`.

##### Step 9
> Call `console.log()` again to inspect the new value of `money`.

<details>
  <summary>Show solution</summary>

```js
const PRICE_UNIT = 'squirrel skins';

let price = 5;
let money = 37;
let affordAmount = money / price;
let remainder = money % price;
let itemAmount = (money - remainder) / price;
let totalPrice = itemAmount * price;

console.log(`I have ${money} ${PRICE_UNIT}.
The thing costs ${price} ${PRICE_UNIT}, so I can buy ${itemAmount} things.
After purchase I should have ${remainder} ${PRICE_UNIT} left.`);

money = money - totalPrice;
console.log(`I have ${money} ${PRICE_UNIT} left after the purchase.`);
```
</details>

---

## Lesson 3: Functions
As mentioned in [Lesson 1: Hello World!](#lesson-1-hello-world), a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) is essentially a block of code that can be called with parameters. They are used to encapsulate logic that can be reused.

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
A new function named `addNumbers` is defined. It accepts two parameters: `a` and `b`.

Parameters are variables that are used to receive *input values*. These input values, also known as *arguments*, are passed to the function when it is called. Inside the function body is a return statement that evaluates the expression `a + b` which returns the sum of `a` and `b`.

Functions follow the same [naming conventions](#naming-conventions) as variables.

```js
console.log('Type of addNumbers', typeof addNumbers); // "function"
```
The `typeof` operator shown in [Lesson 2: Values, variables and expressions](#lesson-2-values-variables-and-expressions) returns `"function"` for all functions.


### Parameters and values
```js
let firstNumber = 12;
let secondNumber = 30;
let sum = addNumbers(firstNumber, secondNumber);
console.log('Return value of addNumbers()', sum); // 42
```
The code above first defines two variables: `firstNumber` and `secondNumber` and both are assigned `Number` values.

A third variable `sum` is declared, and assigned the return value of calling `addNumbers(firstNumber, secondNumber)`.

Inside `addNumbers()` parameter `a` receives the value `12` from `firstNumber`, and parameter `b` receives the value `30` from `secondNumber`.

The function returns the sum of the values which is `42` by evaluating the expression `12 + 30`.


### Default parameters
```
function functionName(requiredParameter, optionalParameter = value) {
  ...
  return expression
}
```
Some functions are often called with the same parameters. Parameters can be assigned a default value, like `optionalParameter` above, which make them *optional*. Optional parameters are always defined after parameters which do not have a default value.

```js
function roundNumber(value, precision = 2) {
  const precisionFactor = 10 ** precision;
  return Math.floor(value * precisionFactor) / precisionFactor;
}
```
Functions can define their own variables in their *scope*, and call other functions, among many other things. The concept of *function scope* is explained later this lesson.

Defined function `roundNumber()` accepts two parameters:
- `value` which is required because it has no default value.
- `precision` which is optional because it has a default value of `2`.

Inside the constant `precisionFactor` is assigned the expression `10 ** precision`, which uses the exponentation `**` operator raising `10` to the power of `precision`.

> When `precision` is the default value `2`, the expression is    
> `10 ** 2` = `10 * 19` = `100`  
>
> When `precision` is `4`, the expression is  
> `10 ** 4` = `10 * 10 * 10 * 10` = `10000`.  

The return statement uses `Math.floor()`, another built-in function, to round down the value returned by the expression `value * precisionFactor`, which is then divided by `precisionFactor`.

The returned value is the `value` parameter rounded to an arbitrary decimal `precision` with the above operation.

More about built-in functions in [Lesson 7: Built-in objects](#lesson-7-built-in-objects).

```js
const PI = 3.14159265;
console.log('PI with 4 decimals', roundNumber(PI, 4)); // 3.1415
console.log('PI with 2 decimals', roundNumber(PI)); // 3.14
```
Constant `PI` is defined with an approximate value of pi. It is then used as the first parameter to `roundNumber()`.

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
Variable `divide` is assigned a function expression as a value that performs simple division. 

`divide()` is then *called like function*, because it's *value is a function*, executing the function code in the example.

const log = console.log;
log('I got tired of writing console all the time'); // "I got tired of writing console all the time"
Functions can be passed around like any value, with some limitations.


### Arrow functions
```
(parameters) => expression
```
JavaScript has a compact alternative to a traditional function expression called the [arrow `function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions). The curly brackets `{}` normally surrounding the function body can be omitted, in which case the `return` keyword can be omitted as well.

The expression after the fat arrow `=>` symbol evaluates to the return value.

```js
divide = (dividend, divisor) => dividend / divisor;
console.log('Result of divide()', divide(8022, 6)); // 1337
```
Both versions of `divide()` are functionally identical and only the syntax used varies.

```
parameter => expression
```
If a single parameter is used, the parenthesis `()` around the parameter list can also be omitted.

```js
const square = number => number * number;
console.log('Result of square()', square(4)); // 16
```
The constant `square`, when called, evaluates the expression `number * number`.

```
(parameters) => {
  ...
  return expression
}
```
Arrow functions `=>` also support code blocks with the curly brackets `{}`, but require a `return` statement to return a value like regular functions.


### Scope
```js
let outside = 'I am from outside the function';
let override = 'I will be overridden by function scope';
let parameter = 'I will be overridden as a parameter';

function scopeTest(parameter) {
  let override = 'I am defined inside the function scope';
  console.log(outside); // "I am from outside the function"
  console.log(override); // "I am defined inside the function scope"
  console.log(parameter); // "I am the parameter"
}

scopeTest('I am the parameter');
```
Scope refers to the *current context of code execution*. It determines the *accessibility of variables* and other resources in the code. Functions can read the variables outside of it's scope as long as they are *declared before the function itself*.

Variables `outside`, `override` and `parameter` are defined *outside* of function `scopeTest()`.

Inside `scopeTest()` a *local variable* `override` is defined, which results in the variable of the same name outside of the function body to not be used. The same happens with `parameter`, while the variable `outside` retains it's value inside the function.


### Higher-order functions
```js
function createPowerFunction(exponent) {
  return value => value ** exponent;
}
let powerOfTwo = createPowerFunction(2);
console.log('Result of powerOfTwo()', powerOfTwo(4)); // 16
```
Functions can *return* other functions. This is a very powerful feature of JavaScript as it allows creating functions that can define, or override, the default parameters of other functions.

Function `createPowerFunction()` accepts a single parameter: `exponent`.

`createPowerFunction()` returns an arrow function that accepts a single parameter: `value`.

The returned arrow function itself returns the expression `value ** exponent`, where parameter `exponent` comes from the *scope* of `createPowerFunction()`.

Variable `powerOfTwo` is assigned the return value of `createPowerFunction(2)`, which is the arrow function accepting `value` as the parameter.

Calling `powerOfTwo()` then evaluates evaluates the expression `value ** 2`.

```js
function wrapLoggerPrefix(logger) {
  return value => logger('WHAT', value);
}
const log = wrapLoggerPrefix(console.log);
log(1234); // "WHAT" 1234
```
Functions can also *accept functions as parameters* and call them inside the function body.

Function `wrapLoggerPrefix` accepts a single parameter:
- `logger` which is expected to be a function.

Constant `log` is assigned the return value of `wrapLoggerPrefix()` with `console.log` (without calling parenthesis) as the parameter `logger`.

Calling `log()` evaluates the expression `console.log('WHAT', value)`, where `value` is the parameter accepted by `log()`, which is the arrow function returned by `wrapLoggerPrefix()`.


### Summary
- [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) is a type that can be called to perform logic.
- [`function` declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) is used to create a function.
- [`function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function) is used to create a function as a value.
- [`return`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return) statement is used inside a function to return a value.
- [Arrow `function` expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) are a more compact way to define functions.
- [JSDoc](https://jsdoc.app) is used to describe code in block-level comments.
- [JSDoc cheatsheet](https://devhints.io/jsdoc) is a quick reference guide to the syntax of JSDoc.


### Assignment 3
In this assignment you will utilize your new knowledge of functions.


#### Task 1: Greeting function
Modify the code from [Task 1 of Assignment 2: *"Hello world" with template literals*](#task-1-hello-world-with-string-interpolation).

##### Step 1
> Write a new function `greet()` that accepts two parameters:  
> `name` that has no default value and is required.  
> `greeting` that has the default `String` value of `"Hello"`.

##### Step 2
> Make the function `greet()` return the template literal that was passed to `console.log()` previously.

##### Step 3
> Try passing the return value of `greet()` to `console.log()` when using different parameters.
>   
> Ensure the default value is used when the `greeting` parameter is omitted.

##### Step 4
> Write a higher-order function `createGreet()` that accepts a single parameter: `greeting`
> 
> The `createGreet()` function should *return a function*, which accepts a single parameter: `name`  
>
> The function returned by `createGreet()` should call `greet()` with the appropriate parameters.

##### Step 5
> Create a few functions with `createGreet()` and test their return values with `console.log()`.

<details>
  <summary>Show solution</summary>

```js
function greet(name, greeting = 'Hello') {
  return `${greeting}, ${name}!`;
}

function createGreet(greeting) {
  return name => greet(name, greeting);
}

const greetFinland = createGreet('Terve');
const greetHawaii = createGreet('Aloha');
console.log(greetFinland('Anonymous'));
console.log(greetHawaii('Anonymous'));
```
</details>


#### Task 2: Financial transaction functions
Modify the code from [Task 2 of Assignment 2: *Financial transaction*](#task-2-financial-transaction).

##### Step 1
> Write a new function `calculateAffordableItemAmount()` which accepts two parameters: `price` and `money`.

##### Step 2
> Move the code from the *"Financial transaction"* task inside the function `calculateAffordableItemAmount()`.
> 
> Modify the code so the values of `price` and `money` are the parameters and not variables.

##### Step 3
> Make `calculateAffordableItemAmount()` return the value of `itemAmount`.

##### Step 4
> Write a new function `calculateTotalPrice()` which accepts two parameters: `price` and `amount`.  
> The function should return the result of multiplying `price` with `amount`.

##### Step 5
> Define the variables `price` and `money` again outside of the functions.  
> Assign them `Number` values, like you did previously.

##### Step 6
> Define a variable named `itemAmount`.  
> Assign it the return value of `calculateAffordableItemAmount()` with variables `price` and `money` as the parameters.

##### Step 7
> Define a variable named `totalPrice`.  
> Assign it the return value of `calculateTotalPrice()` with variables `price` and `itemAmount` as the parameters.

##### Step 8
> Define a variable named `remainder`.  
> Assign it an expression where you subtract `totalPrice` from `money`.

##### Step 9
> Call `console.log()` to inspect the variables defined after Step 5.  
> Use template literals to format the output, detailing the transaction.

<details>
  <summary>Show solution</summary>

```js
function calculateAffordableItemAmount(price, money) {
  let affordAmount = money / price;
  let remainder = money % price;
  let itemAmount = (money - remainder) / price;
  return itemAmount;
}

function calculateTotalPrice(price, itemCount) {
  return price * itemCount;
}

const PRICE_UNIT = 'dollaroos';

let price = 5;
let money = 37;

let itemAmount = calculateAffordableItemAmount(price, money);
let totalPrice = calculateTotalPrice(price, itemAmount);
let remainder = money - totalPrice;

console.log(`I have ${money} ${PRICE_UNIT}.
The thing costs ${price} ${PRICE_UNIT}, so I can buy ${itemAmount} things.
After purchase I have ${remainder} ${PRICE_UNIT} left.`);
```
</details>
s
---

## Lesson 4: Boolean values, comparisons and conditional operations
JavaScript has a third important primitive data type which enables conditional logic.

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
> The `Boolean` data type has only two possible values: `true` and `false`.

```js
console.log('NOT true', !true); // false
console.log('NOT false', !false); // true 
```
`Boolean` values can be inversed with the [logical NOT `!` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT).


### Empty values and truthiness
```js
let nullValue = null;
console.log('No value', nullValue); // null
```
The concept of empty values was mentioned in [Lesson 2: Values, variables and expressions](#lesson-2-values-variables-and-expressions), where `undefined` was introduced to indicate there is no value. Another way to do that in JavaScript is the [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) value.

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
*Comparison operators* return `Boolean` values when evaluated. These include checking if two values are equal.

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

The above code first uses the [equality `==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) and the [inequality `!=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality) to compare a `Number` value of `1` to a `String` value of `"1"`, which are *the same*. They are considered same because these operators not compare the *type* of a value.

This can lead to strange side effects, and so their use is discouraged. Using the *strict* equality operators is recommended as they are *type safe*.

### Comparing numbers
```js
console.log(4 > 3); // greater than, true
console.log(3 >= 3); // greater than or equals, true

console.log(4 < 3); // false, less than
console.log(4 <= 3); // false, less than or equals
```
`Number` values can be compared to each other by using numeric comparison operators.

[Greater than `>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than)
> The "greater than" operator returns `true` if the left value is greater than the right value, and `false` otherwise.

[Greater than or equal `>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal)
> The "greater than or equal" operator returns `true` if the left value is greater than or equal to the right value, and `false` otherwise.

[Less than `<`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than)
> The "less than" operator returns `true` if the left value is less than the right value, and `false` otherwise.

[Less than or equal `<=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than_or_equal)
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
A major part of software is *conditional execution of code*. The [`if...else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) statement allows execution of code when the *condition*, an expression, evaluates as `true`.

Conditional execution starts with the `if` keyword, followed by an opening parenthesis `(`, a condition expression, and a closing parenthesis `)`.

Next is an opening curly bracket `{` that starts a code block. The `...` signifies that code can be placed here. The code block ends with a matching closing curly bracket `}`.

An *optional* `else` block will execute if the condition expression evaluates as `false`.

```js
if ('value' === 'value') {
  console.log('Values are equal'); // "Values are equal"
}
if (1 !== 1) {
  console.log('This is never called because 1 === 1');
}
```
The first `console.log()` call is executed because it's condition evaluates as `true`, while the second will not.

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
Multiple `if...else` statements can be nested to create an `else if` clause. It will execute the first code block where the condition evaluates as true, or the *optional* `else` block if one exists.

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
The [conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) allows for a shorter way to perform simple `if...else` operations.

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
Using white space can help readability. Here `conditionalVar` receives the value `"Yay"` as the expression `4 === 4` evaluates as `true`.


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
console.log(true || true); // true
console.log(true || false); // true (in any order)
console.log(false || false); // false
```
Above is a the truth table for the OR `||` operator with the different combinations of `Boolean` values, and what they evaluate as.


### Summary
- [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) is a primitive data type that can be `true` or `false`.
- [Logical NOT `!` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT) inverses the value of a `Boolean`.
- [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) value represents the intentional absence of value.
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


### Assignment 4

# TODO

---

## Lesson 5: Objects
The [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) data type allows the definition of more complex data by allowing the aggregation of data that has some kind of connection between them.

```
{
  key: value,
  key: value
}
```
Object definitions are usually `key: value` pairs inside curly brackets `{}` separated by comma `,`.

A property `key` is usually a `String` and the property `value` can be any type.

```js
const testObject = {
  textProperty: 'words are fun',
  numberProperty: 58008,
};
```
Constant `testObject` is defined with two properties:
- `textProperty` with the value of `"words are fun"`.
- `numberProperty` with the value of `58008`.


### Accessing properties
```
object.property
object[key]
```
An object's property can be accessed with the dot `.` notation, or by using the key inside hard brackets `[]`.

```js
console.log(testObject.textProperty); // "words are fun"
console.log(testObject['numberProperty']); // 58008
```
The `textProperty` of `testObject` is accessed with the dot `.` notation, and `numberProperty` is accessed using the `String` value of the key inside hard brackets `[]`.

```js
console.log(testObject.missingProperty); // undefined
```
Accessing a property that does not exist returns `undefined`.


### Nesting objects
```js
const person = {
  name: 'John Smith',
  age: 27,
  address: {
    street: 'Fake street 1',
    postalCode: '12345',
    city: 'Faketown',
    country: 'Fantasyland',
  }
};
console.log(person.address.street); // "Fake street 1"
```
Because an object's property can have any value, we can easily compose more complex structures by nesting objects; `person` has the property `address` that is also an object with it's own properties.

We can access the inner properties of the `address` property by chaining the dot `.` notation.

```js
const addressKey = 'address';
console.log(person[addressKey].postalCode); // "12345"
```
Access to properties can be made dynamic. Because an object's keys are `String` values, the key can be stored in a *variable*, and that variable can be used to access the desired property using the hard brackets `[]` syntax.

These methods of accessing properties can be chained together as needed.


### Object instances
```js
const anotherPerson = person;
anotherPerson.name = 'Jane Doe';
console.log(person.name); // "Jane Doe"
```
Constant `anotherPerson` is assigned the value of `person`. When an object is used as a value, it's a *reference* to an *object instance*.

When changing the `name` property of `anotherPerson`, the change occurs on the *object instance*, which is why the `name` property of `person` also changes. They are the *same object instance*.


### Iterating objects
TODO


### This
TODO: function `this` scope.


### JSON
```js
const jsonString = JSON.stringify(testObject)
console.log(jsonString) // "{'property':'value','anotherProperty':2}"

const parsedObject = JSON.parse(jsonString)
console.log(parsedObject) // copy of testObject
```
JavaScript Object Notation, or JSON for short, is a way of representing data the same way JavaScript represents data. JSON is being used by most websites on the planet as it works seamlessly with JavaScript with the [`JSON.stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) and [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) functions.

```js
const prettyJsonString = JSON.stringify(person, null, 2)
console.log(prettyJsonString) // person as formatted JSON
```
The `JSON.stringify()` function can format the output for better readability with the right parameters.


### Summary
- [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) type TODO
- [`JSON.stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) TODO
- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) TODO


### Assignment 5

# TODO

---

## Lesson 6: Arrays and loops
Sometimes you want to store more than a single value in a variable. One way to accomplish this is to use the [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) type.

An `Array` is an ordered list of values, or *elements*, which can be accessed with an *index*.

```
[value, ...values]
```
The easiest way to define an `Array` is to wrap the elements between hard brackets `[]`, separated by `,` comma.

```js
const countries = ['Finland', 'Canada', 'Iceland'];
```
The constant `countries` is assigned an `Array` with three elements.

```
array[index]
```
To access an element at a specific *index* of an array, use a beginning hard bracket `[`, followed by the *index number*, followed with a closing hard bracket `]`.

The first index is always zero `0`.

```js
console.log(countries[0]); // "Finland"
console.log(countries[1]); // "Canada"
console.log(countries[2]); // "Iceland"
```
Each element of `countries` is logged by accessing it via the index.

```js
console.log(countries.length); // 3
```
Arrays have a *property* called `length`, which is a `Number` value that equals the number of elements stored in the array. The maximum index in an array is always `length - 1`.

```js
console.log(countries[3]); // undefined
```
If an `Array` does not have an element at the index, it returns `undefined`.

Because `countries` is a constant, it's value cannot be overwritten. The `Array` it contains can still be manipulated with built-in functionality.


### Adding and removing values
```js
countries.push('Russia');
console.log(countries); // ["Finland", "Canada", "Iceland", "Russia"]
```
To add new elements to the *end* of an `Array` use [`Array.push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push), which accepts the new values to be added as parameters.

```js
let removedCountry = countries.pop();
console.log(removedCountry); // "Russia"
console.log(countries); // ["Finland", "Canada", "Iceland"]
```
To remove the *last* element of an `Array` use [`Array.pop()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop), which returns the removed value.

```js
countries.unshift(removedCountry);
console.log(countries); // ["Russia", "Finland", "Canada", "Iceland"]
```
To add elements to the *beginning* of an `Array` use [`Array.unshift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift), which accepts the new values to be added as parameters.

```js
removedCountry = countries.shift();
console.log(removedCountry); // "Russia"
console.log(countries); // ["Finland", "Canada", "Iceland"]
```
To remove the *first* element of an `Array` use [`Array.shift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift), which returns the removed value. 


### Splicing values in and out an array
```js
countries.splice(1, 0, 'Egypt');
console.log(countries); // ["Finland", "Egypt", "Canada", "Iceland"]
```
There are more ways to manipulate arrays than simply adding or removing elements to the beginning or end of an array. [`Array.splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) lets you pick an index in an array, and add and or remove elements at that location.

First the value `"Egypt"` is *spliced in* at index `1`.

```js
let removedCountries = countries.splice(1, 2);
console.log(removedCountries); // ["Egypt", "Canada"]
console.log(countries); // ["Finland", "Iceland"]
```
Next, `2` values are *spliced out* at index `1`, which are `"Egypt"` and `"Canada"`.

They are stored in variable `removedCountries`, an array, as `Array.splice()` returns the removed values as an `Array`.

```js
countries.splice(2, 0, 'Norway', 'Denmark');
console.log(countries); // ["Finland", "Norway", "Denmark", "Iceland"]
```
Two more values, `"Norway"` and `"Denmark"`, are spliced in at index `2`.


### Loops
```
for (initialization; condition; afterthought) {
  ...
}
```
Sometimes code needs to be repeated, like when *iterating* through the elements of an `Array`. The [`for`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) loop can be used in such cases.

The keyword `for` is followed by an opening parenthesis `(`, followed by three optional expressions separated by semicolon `;` and ended with a closing parenthesis `)`.

Next is an opening curly bracket `{`, which starts a code block that is repeated each iteration. The `...` signifies that code can be placed here. The code block ends with a matching closing curly bracket `}`.

**Initialization**
> Evaluated once before the loop begins. This is where variables used in the loop are declared.

**Condition**
> Evaluated once before each loop iteration.
> 
> If the expression evaluates to `true` the code inside the loop is executed.  
> If the expression evaluates to `false` the loop ends.

**Afterthought**
> Evaluated at the end of loop iteration. This is usually used to update counters before the next iteration.

```js
for (let index = 0; index < countries.length; index++) {
  const country = countries[index];
  console.log(country); // "Finland", "Norway", "Denmark" and "Iceland" in sequence
}
```
This for loop iterates through the elements of `countries`.

The *initialization* expression declares variable `index` and it is assigned the value zero `0`, as we plan to count indexes upwards.

The *condition* expression checks if value of `index` is less than `countries.length`. This evaluates as `true` until `index` equals `countries.length`, when it evaluates as `false` and the loop ends.

The *afterthought* expression uses the [increment `++` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment) to increase the value of `index` at the end of each iteration.

Inside the loop the constant `country` is defined, and it is assigned the value of `countries` at `index`. The value of `country` is then logged.

```js
for (const country of countries) {
  console.log(country); // "Finland", "Norway", "Denmark" and "Iceland" in sequence
}
```
The [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loop iterates through the *values* of an `Array` when the index is not relevant.

The two `for` loops in the example code are functionally identical.

```
while (condition) {
  ...
}
```
The [`while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) loop checks it's condition *before* each iteration.

```js
let counter = 0
while (counter++ < 10) {
  console.log('while', counter); // "while" 1...10
}
```
The increment `++` operator is used to increase the value of `counter`.

```
do {

} while (condition)
```
The [`do...while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while) loop checks it's condition *after* each iteration.

```js
counter = 10
do {
  console.log('do while', counter) // "do while" 10...1
} while (--counter > 0);
```
The [decrement `--` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement) is used to decrease the value of `counter`.


### Map
The `Array` type has three incredibly useful functions that each take a function as it's parameter.

[`Array.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) creates a new `Array` with the results of calling the provided function on every element of an array.

```
(element, index, array) => { ... }
```
The function `Array.map()` accepts as a parameter should follow the signature above.
- `element` is the current *value*.
- `index` is the current *index*. *This parameter is optional*.
- `array` is a *reference* to the `Array` itself. *This parameter is optional*.

```js
const numberList = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const double = value => value * 2;
console.log(numberList.map(double)); // [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```
Constant `numberList` is defined as an `Array`, with a range of numbers from `1` to `10` as it's values.

An arrow function `double` is defined, which returns the expression `value * 2` when called.

The `map()` function iterates through each element in `numberList` and runs the `double()` function on each element, storing the new values in an `Array` that is returned.

The return value, which is logged, has the same number of elements as `numberList`, but each value is doubled.


```js
const multiplyByIndex = (value, index) => value * index;
console.log(numberList.map(multiplyByIndex)); // [0, 2, 6, 12, 20, 30, 42, 56, 72, 90]
```
An arrow function `multiplyByIndex` is defined, which returns the expression `value * index` when called.

Again, the `map()` function iterates through each element and runs the `multiplyByIndex` on each element.

The return value, which is logged, has the same number of elments as `numberList`, but each value is multiplied by the `index`.


### Filter
[`Array.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) creates a new `Array` with all the elements that pass the *condition implemented by the provided function*.

```
(element, index, array) => { ... }
```
The function `Array.filter()` accepts as a parameter should follow the signature above.
- `element` is the current *value*.
- `index` is the current *index*. *This parameter is optional*.
- `array` is a *reference* to the `Array` itself. *This parameter is optional*.

```js
const onlyEvenNumbers = value => value % 2 === 0;
console.log(numberList.filter(onlyEvenNumbers)); // [2, 4, 6, 8, 10]
```
Constant `onlyEvenNumbers` is defined, with an arrow function `=>` as it's value, which runs the expression `value % 2 === 0`.

Only *even numbers* return `true` from the evaluation, so the resulting `Array` contains only even numbers.

```js
// TODO: use (element, index) in example
```


### Reduce
[`Array.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) applies a function against an *accumulator* and each element in the array to reduce it to a single value.

It executes the provided function for each value of the array (from left-to-right) and the return value of the function is stored in an *accumulator*, which is then passed along to the next call of the function.

`Array.reduce()` accepts two parameters:
- The *function*.
- The initial value of the *accumulator*.

```
(accumulator, element, index, array) => { ... }
```
The function `Array.reduce()` accepts as the *first parameter* should follow the signature above.
- `accumulator` is the return value that is passed from the previous call of the function.
- `element` is the current *value*.
- `index` is the current *index*. *This parameter is optional*.
- `array` is a *reference* to the `Array` itself. *This parameter is optional*.

The *second parameter* in `Array.reduce()` is the *initial value of the accumulator*.

```js
const sumReducer = (accumulator, value) => accumulator + value;
console.log(numberList.reduce(sumReducer, 0)); // 55
```
TODO description

```js
// TODO: use (accumulator, element, index) in example
```


### Cloning an array
```js
let cloneArray = [];
for (const country of countries) {
  cloneArray.push(country);
}
console.log(cloneArray); // ["Finland", "Norway", "Denmark", "Iceland"]
```
Sometimes a *copy* of an `Array` is required. Loops are one way to do do it.

Variable `cloneArray` is assigned an empty `Array` as it's value with the hard brackets `[]` without any values defined.

The `for` loop iterates through the elements of `countries`, and adds `country` to the end of `cloneArray` with `Array.push()`.

```js
console.log('These are the same instance', countries === cloneArray); // false
```
The resulting `cloneArray` has the *same values* as `countries`, but is not the *same object instance*.

```js
cloneArray = Array.from(countries);
```
An easier way to clone an array is to use [`Array.from()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from), which accepts any *iteratable* type as a parameter and returns a new `Array`.


### Summary
- [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) TODO
- [`Array.push`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) TODO
- [`Array.pop`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) TODO
- [`Array.unshift`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) TODO
- [`Array.shift`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) TODO
- [`Array.splice`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) TODO
- [`for` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) TODO
- [`while` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) TODO
- [`do...while` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while) TODO
- [Increment `++` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment) TODO
- [Decrement `--` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement) TODO
- [`Array.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) creates a new `Array` with the results of calling the provided function on every element of an array.
- [`Array.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) creates a new `Array` with all the elements that pass the condition implemented by the provided function.
- [`Array.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) applies a function against an accumulator and each element in the array to reduce it to a single value.
- [`Array.from()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) TODO


### Assignment 6
In this assignment you will use the `Array` type and loops.


#### Task 1: A list of numbers
The first task is to create a function that returns a list of numbers.

##### Step 1
> Create a new function called `createNumberList()` that accepts a single parameter: `maximumNumber`

##### Step 2
> In the function, create an empty `Array` called `numbers`.

##### Step 3
> In the function, add a `for` loop.
> 
> In the *initialization* expression defines a variable called `counter` and set it's value to zero `0`.
>
> In the *condition* expression check that `counter` is less than `maximumNumber`.
>
> In the *afterthought* expression increment `counter` by one.

##### Step 4
> In the body of the `for` loop add the value of `counter + 1` to the `numbers` array.

##### Step 5
> Outside `createNumberList()`, add the following code to verify it works correctly:

```js
const numbers = createNumberList(9);
console.log(numbers); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
> The function should produce the same result when called with the same parameter.


#### Task 2: Pluck a value from an Array
The second task is to create a function that removes a value from an `Array` at a specified index and returns it.

##### Step 1
> Create a new function called `pluckValueFromArray()` that accepts two parameters: `array` and `index`

##### Step 2
> In the function, remove a value from `array` at `index`.

##### Step 3
> In the function, return the the value removed from `array`.

##### Step 4
> Outside `pluckValueFromArray()`, add the following code to verify it works correctly:

```js
const plucked = pluckValueFromArray(numbers, 2);
console.log(plucked); // 3
```
> The function should produce the same result when called with the same parameters.

---

## Lesson 7: Built-in objects
JavaScript comes with several built-in *global objects* that give us tools to solve problems with one of the most useful being [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math).

```js
console.log('Round down', Math.floor(1.998)); // 1
console.log('Round nearest', Math.round(1.500)); // 2
console.log('Round up', Math.ceil(1.001)); // 2
```
Some of the basic functionality in the `Math` object includes functions for rounding numbers.

[`Math.floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) returns the value of a number rounded down, [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round) returns the value of a number rounded to the nearest integer and [`Math.ceil()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) returns a value of a number rounded up.


```js
console.log(Math.random());
console.log(Math.random());
console.log(Math.random());
```
Sometimes randomness is a desired feature of a program. [`Math.random()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) returns a new random `Number` value each time the function is called. The returned value is a fractional value between `0.0` an `1.0`.


### Summary
- [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) is a global object. TODO
- [`Math.floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) returns the value of a number rounded down.
- [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round) returns the value of a number rounded to the nearest integer.
- [`Math.ceil()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) returns a value of a number rounded up.
- [`Math.random()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) returns a random number between `0.0` and `1.0`.


### Assignment 7
This assignment will have you combine previously learned information with the new functions learned from this lesson.


#### Task 1: Random Array index
In this task you will use random numbers to access values in an `Array`.

##### Step 1
> Create a new function called `getRandomIndex()` that accepts a single parameter: `array`

##### Step 2
> In the function, return a random index from `array`.

##### Step 3
> Test your implementation by using `getRandomIndex()` with the previously defined `numbers` array:
>
> Construct a loop to repeatedly request a new index. Make sure the loop ends.
>
> Use `console.log()` to output the values.


#### Task 2: Pluck a random value from an Array
In this task you will combine functions written previously with random values.

##### Step 1
> Create a new function called `pluckRandomValueFromArray()` that accepts one parameter: `array`

##### Step 2
> In the function, use `getRandomIndex()` and `pluckValueFromArray()` to remove a random value from `array`.  
> 
> Return the value removed from `array`.

##### Step 4
> Outside the `pluckRandomValueFromArray()` function, construct a `while` loop.
>
> The loop `condition` checks if `numbers` has any values.
> 
> Inside the loop body use `pluckRandomValueFromArray()` to remove a value from `numbers`.
> 
> Use `console.log()` to inspect the removed value.
> 
> The loop should output a value from `numbers` in random order until `numbers` has no values left.


#### Task 3: Pluck multiple random values from an Array
In this task you will combine functions written previously remove random elements from an `Array`.

Note the difference in the *function names*; the previously made is *singular*, and the new is *plural*.

##### Step 1
> Create a new function called `pluckRandomValuesFromArray()` that accepts two parameter: `array` and `count`

##### Step 2
> Inside the function, use a loop to remove `count` values from `array` using `pluckRandomValueFromArray()` from the previous task.

##### Step 3
> Inside the function, store the removed values in a new `Array`.

##### Step 4
> Inside the function, return the removed values as an array.

##### Step 5
> Outside `pluckRandomValuesFromArray()`, use `createNumberList()` to create a new list and store it in a variable called `moreNumbers`.

##### Step 6
> Use `pluckRandomValuesFromArray()` to remove some number of values from `moreNumbers`, and store them in a variable.

##### Step 7
> Use `console.log()` to check the value of `moreNumbers`, and the `Array` returned by `pluckRandomValuesFromArray()`.


#### Task 4: Select multiple random values from an Array
In this task you will combine functions written previously to select random elements from an `Array` without mutating it.

##### Step 1
> Create a new function called `selectRandomValuesFromArray()` that accepts two parameters: `array` and `count`

##### Step 2
> Inside the function, clone the `array` parameter to a new variable.

##### Step 3
> Inside the function, use `pluckRandomValuesFromArray()` to pluck `count` values from the *cloned array*.

##### Step 4
> Outside `selectRandomValuesFromArray()`, use `createNumberList()` to create a new list and store it in a variable called `staticNumbers`.

##### Step 5
> Use `selectRandomValuesFromArray()` to return random values from `staticNumbers`, and store them in a variable.

##### Step 6
> Use `console.log()` to check the value of `staticNumbers`, and the `Array` returned by `selectRandomValuesFromArray()`.
>
> The `staticNumbers` should have *all the values* intact, and the return value of `selectRandomValuesFromArray()` should have *some of the values* of `staticNumbers`, but no duplicates.
