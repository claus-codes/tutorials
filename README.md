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
Like the one seen above, sample code is always followed by an explanation and is always *syntax highlighted* which means different things have different colors based on semantic rules. JavaScript is very strict about syntax, which is the set of rules that govern the structure of a language.

```
if (condition) {
  ...
}
```
Some lessons teach you how JavaScript code is structured with an example of syntax. Like sample code they are followed by an explanation, but unlike sample code they are not syntax highlighted as they are not code.

Lessons feature the following recurrent sections at the end:

#### Summary
> The Summary section contains a list of links to documentation for the things discussed during the lesson. These are your best resources to learn more, so be curious and explore.

#### Useful things
> Useful things are things you *should* know about, but did not have a good place in the tutorial.


### Assignments
The assignments after each lesson are designed to use new and previously learned information. Assignments can have multiple steps for you to complete, which include writing new code and modifying code you wrote previously.

*All the code from the assignments should be placed in the same file*, as code written in earlier assignments will be used later. Tasks should be done in the order they are presented.

#### Extra credit
> Some assignments have an Extra Credit section at the end. This section contains small challenges for when you have finished all the lessons and assignments.


### Workflow
This tutorial is intended to be used with [CodePen](https://codepen.io/pen/) which offers a free coding playground, where you can write code that runs and saves automatically.

We use the *console* exclusively for displaying information so you can keep track of what's happening. You can open the console in **CodePen** from the **bottom-left corner** of the workspace from the *"Console"* button.

Sample code provided in each lesson can be copied to the editor and will work **unless** it specifically mentions *throwing an Error*. Copying the sample code is not necessary as the expected output is shown as *comments* in most cases. You will soon learn about comments in [Lesson 1](#lesson-1-hello-world).

I would recommend writing a comment before the code for each assignment, and to include the assignment number so you can find it more easily.


---


## Lesson 1: Hello World!
All software is just data processing and manipulation. Let me introduce you to two primitive data types found in JavaScript that we will be using soon:

#### [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
> The `Number` data type represents *any real numbers* like `42`, `3.14159` or `-10000000000`.

#### [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
> The `String` data type represents sequences of characters. They are commonly wrapped in quotes like `'single'`, or `"double"`. This tutorial uses double-quotes when discussing string values during this tutorial, and single-quotes in sample code.

### A humble beginning
```
functionName(parameter, ...parameters);
```
Above is the syntax for a **function call**; it starts with the *name of the function* followed with an opening parenthesis `(`, an *optional* list of parameters separated by comma `,`, and a closing parenthesis `)` at the end.

The trailing semicolon `;` after a statement is *entirely optional* in JavaScript. This tutorial includes them in this tutorial as code can break in unexpected ways when you do not include them.

```js
console.log('Hello World!');
```
The first part, [`console.log`](https://developer.mozilla.org/en-US/docs/Web/API/console/log), is the name of a built-in function in JavaScript that lets us write to the developer console. It gets passed a single parameter - the `String` value of `"Hello World!"`.

There is a lesson dedicated to functions so for now think of a function as code that can be called with or without parameters.


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


### Assignment 1: Make your own call
Write code that calls `console.log()` with your own message.

#### Extra credit
- Write your own logging function that uses `console.log()` and accepts an arbitrary number of parameters.
- Add the current time and date before each log entry.
- Process every parameter that is of type `Object` with `JSON.stringify()` and format the output.
- Create another function to turn the logging on and off.


---


## Lesson 2: Values, variables and expressions
To store and manipulate values, like `Number` or `String`, we need to use variables.

```
let variableName = expression
```
Variables are declared with the keyword [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), followed by the name of the variable, followed by an *optional* [Assignment `=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) operation to set an initial value which is evaluated from the expression. Expressions are explained later in this lesson.

```js
let num = 9;
let text = 'JavaScript';
```
The code above declares two variables; `num` that we assign the `Number` value of `9`, and `text` we assign `String` value of `"JavaScript"`.


### Empty values
```js
let emptyVar;
console.log(emptyVar); // undefined
```
Variables can be declared with assigning an initial value. The variable `emptyVar` gets a special *empty value* called `undefined`, which means it has not been given any value. There is more information about empty values in [Lesson 4](#lesson-4-booleans-comparisons-and-conditional-operations).


### Constant values
```js
const immutableValue = 'I cannot be overwritten';
immutableValue = 'this will not work'; // this line will throw an Error
```
The [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) keyword creates a constant value, which acts like a variable but it's value cannot be changed after it's declaration. When it is known that a value will not change during execution, it is preferred to use `const` over `let`.


### Logging variables

```js
console.log('Number', num); // "Number" 9
console.log('Message', text); // "Message" "JavaScript"
```
Variables can be used as parameters just like `Number` and `String` values. It is good practice to add some context before values when logging things as it's easy to lose track of what value is relevant in the logs.

For the sake of readability in this tutorial, I will omit the context message.


### Changing the value of a variable
```js
text = 'JS';
console.log('New message', text) // "JS"

num = num * 3;
console.log('After multiplication', num); // 27
```
Variables can have their value changed by assigning them a new value. `text` is assigned a new value of `"JS"`, after which the new value is logged to see it is changed.

The variable num `num` is assigned `num * 3`, an *expression*, which evaluates to the `Number` value of `27` as the value of `num` was `9` before evaluation.


### Expressions
```js
console.log('Nice', 23 * 3); // 69
```
The code above calls `console.log()` again, but this time it gets passed the *expression* `23 * 3` instead of a single value or variable. It is a multiplication operation on numbers `23` and `3` which evaluates to the number `69`.

When referring to a value, a variable or an operation in code, you are using an expression. Simply put: *expressions are pieces of code that produce a value.*

`Number` values can be used to perform calculations using various mathematical operators - some more familiar than others.

#### [Addition `+`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition)
> The addition operator adds numbers together, producing a sum of values.

#### [Subtraction `-`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction)
> The subtraction operator subtracts two numbers from one another, producing their difference.

#### [Multiplication `*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication)
> The multiplication operator multiplies numbers, producing the product of the numbers.

#### [Division `/`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division)
> The division operator divides the left number, the dividend, with the right, the divisor.

#### [Remainder `%`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder)
> The remainder operator returns the remainder left over when left number is divided with right number.

#### [Exponentation `**`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)
> The exponentation operator returns the result of raising left number to the power of the right number.

```js
console.log('Four is even', 4 % 2); // 0
console.log('One left over', 21 % 10); // 1

console.log('Basic multiplication', 10 * 10 * 10) // 1000
console.log('Exponentation', 10 ** 3); // 1000
```
The remainder and exponentation operators might not be very familiar to most people, so here's examples for both. To break down the remainder:

> `21 % 10` evaluates to `1` because 21 divided by 10 equals to 2, with the 1 as the remainder.
>
> `4 % 2` evaluates to `0` as 4 is an even number, while odd numbers would produce `1`. 

```js
console.log((num * 100) - 1363); // 1337
```
Parenthesis can be used to group operators together which gives us the ability to write complex calculations where maintaining a strict order of operations is necessary.

```js
const numberValue = 13;
const notNumberValue = 'hello';
console.log('Fail', numberValue / notNumberValue); // NaN
```
When a mathematical operations are attempted with values that are not `Number` types, a special [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) value is used which stands for *Not-a-Number*.


### String interpolation
```js
let text1 = 'ined';
let text2 = 'comb';
console.log(text2 + text1); // "combined" 
```
Instead of performing addition like on `Number` values, the addition `+` operator with `String` values joins strings together.

```js
let name = 'person';
console.log(`Hello, ${name}?`); // "Hello, person?" 
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
To indicate a line-break on a normal string, the *escape-character* `\n` is used. Template literals instead use existing line breaks in the code.


### Naming variables

```js
let variable_with_underscores = 'This is called snake_case';
let variableWithCapitals = 'This is called camelCase';
let VARIABLE_WITH_UPPER_CASE = 'ALL CAPS AAAHHHH!!!!';
```
Variables can be named almost anything with some restrictions; a variable's name cannot start with a number, should be alpha-numeric or the underscore `_` character.

What styles of naming *you* adopt does not matter as it is a personal preference. More importantly you should always strive to be as descriptive as possible when naming things, as it can help make the program logic easier to follow and reason about.


### Summary
- [Variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables) are containers for values defined with the [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) keyword.
- [Assignment `=` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment) is used to assign a value to a variable.
- [`const` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) is used to define constant values which cannot be changed.
- [`NaN` value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) is the result from mathematical operations with values that are *Not a Number*.
- [Remainder `%` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder) returns the remainder left over from a division. 
- [Exponentiation `**` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation) returns the result of raising a number to the power of another number.
- [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is a concept from classic mathematics about the order in which calculations should be evaluated.
- [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) make it easy to construct complex `String` values.


### Useful things
- 


### Assignment 2: Financial transaction

In this assignment you will define variables and perform calculations on them using expressions. Write the code for each step in sequence.

##### Step 1
> Define a constant value named `PRICE`.
> 
> Assign it any `Number` value above zero `0`.

##### Step 2
> Define a variable named `money`.
> 
> Assign it a `Number` value higher than the value of `PRICE`.

##### Step 3
> Define a variable named `affordAmount`.
>
> Assign it an expression that divides `money` by `PRICE`.

##### Step 4
> Define a variable named `change`.
> Assign it the expression of getting the *remainder* of dividing `money` by `PRICE`.

##### Step 5
> Define a variable named `itemAmount`.
>
> Assign it an expression where you first subtract `change` from `money`, then divide the result with `PRICE`.

##### Step 6
> Define a variable named `totalPrice`.
>
> Assign it an expression where you multiply `itemAmount` with `PRICE`.

##### Step 7
> Call `console.log()` to inspect the values of the variables you defined.

##### Step 8
> Define a variable named `previousMoney`.
> 
> Assign it the value of `money`.

##### Step 9
> Change the value of `money` with an expression where `PRICE` multiplied by `itemAmount` is subtracted from `money`.

#### Step 10
> Add the code below after the code you wrote for this assignment to verify that the calculations are correct:
```js
console.log('Calculation is correct', previousMoney - totalPrice === money);
```
> This code prints `"Calculation is correct"` with `true` or `false` as value from the expression - these values are discussed in [Lesson 4](#lesson-4-boolean-values-comparisons-and-conditional-operations).


#### Extra credit
- 

---


## Lesson 3: Functions

As mentioned in [Lesson 1](#lesson-1-hello-world), a `function` is essentially a block of code that can be called with parameters.

```
function functionName(parameter, ...parameters) {
  ...
  return expression;
}
```
New functions are declared with a [`function` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function), followed by the name of the function. Similar to calling a function with parameters, there is opening parenthesis `(`, an *optional* list of parameters separated by comma `,` and a closing parenthesis `)`.

Next is an opening curly bracket `{` that starts the *function body*. The `...` signifies that code can be placed here. The function ends with an *optional* [`return` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return) followed by an expression to return a value. The function body ends with a closing curly bracket `}`.

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
The code above defines two variables: `firstNumber` and `secondNumber` which both are assigned `Number` values.

The third variable `sum` is assigned the value returned by calling `addNumbers(firstNumber, secondNumber)`.

Inside `addNumbers()` parameter `a` receives the value `12`, parameter `b` receives the value `30` and the function returns the sum of the values which is `42`.


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
  return expression;
}
```
Some functions are often called with the same parameters. Parameters be assigned a default value, like `optionalParameter` above, which make them optional. Optional parameters are always defined after required parameters which lack a default value.

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
console.log(roundNumber(PI, 4)); // 3.1415
console.log(roundNumber(PI)); // 3.14
```
The code above shows the values returned by `roundNumber()` with and without the parameter `precision`.

### Functions as values
```
variable = function(parameter, ...parameters) {
  ...
}
```
Functions can be used as values using a [`function` expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function).

```js
let divide = function(dividend, divisor) {
  return dividend / divisor
}
console.log(divide(8022, 6)) // 1337 
```
This sample shows variable `divide` being assigned a function as a value. Variables can be called like functions if their value is a function.

```
(parameter, ...parameters) => expression

parameter => expression
```
JavaScript has a compact alternative to a traditional function expression called the [arrow function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions). The curly brackets `{}` normally surrounding the function body can be omitted, in which case the `return` keyword can be omitted as well.

The expression after the fat arrow `=>` symbol evaluates to the return value.

```js
divide = (dividend, divisor) => (dividend / divisor)
console.log(divide(8022, 6)) // 1337
```
Both versions of `divide()` are functionally identical.


### Summary
- [Function declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) is used to create new functions.
- [Function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function) is used to assign a function as a value.
- [`return` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return) is used inside a function to return a value.
- [Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) are a more compact way to define functions.
- [JSDoc](https://jsdoc.app/) is used to describe code in block-level comments.
- [JSDoc cheatsheet](https://devhints.io/jsdoc) is a quick reference guide to the syntax of JSDoc.


### Useful things
- 


## Assignment 3: A flexible hello

TODO: refactor assignment 2 into function (purchase stuff)

Write a function called `greet()` that accepts two parameters; `name`, and `greeting` which should have a default value like `'Hello'` to make it optional.

The function should return `"(greeting) (name)"`, where `(greeting)` is replaced by the value of the parameter `greeting`, and `(name)` is replaced by the value of the parameter `name`.

Use `console.log()` to inspect the returned values when calling `greet()` with different parameters.


### Extra credit
- Change the implementation of `greet()`, so that the `name` parameter can be an array of `String` values. When an array is passed instead of a single value, we return the list of names joined by `', '` except for the last name on the list which is joined by `' and '` to format a list of names as follows: `'Claus, Tony and Henry'`
- Change `createGreetFunction()` to accept a function as the `greeting` parameter. The function should return a random greeting when called.
- Write a new function called `createGreetFunction()` that accepts a single parameter; `greeting`. When `createGreetFunction()` is called it should return a new function with a single parameter; `name`. The returned function calls `greet()` using the parameter `greeting` from the scope of `createGreetFunction()`, and `name` from it's own parameter. Create a few different customized `greet()` functions using this method.


---


## Lesson 4: Boolean values, comparisons and conditional operations

There is still an important primitive data type we must learn about before we can move forward.

*Boolean*
: The `Boolean` primitive data type has only two possible values: `true` and `false`.

A major part of programming is to alter the execution of a program based on it's data. Comparison operations produce `Boolean` values when evaluated.

```js
console.log(!true) // false
console.log(!false) // true 
```
Boolean values can be inversed with the logical not `!` operator.

```js
console.log(1 === 1) // true
console.log(1 !== 1) // false
```
To compare if two values are equal we use triple equals operator `===`, and to see if they are **not** equal, we use the negated equals check `!==`.

```js
console.log(4 > 3) // greater than, true
console.log(3 >= 3) // greater than or equals, true

console.log(4 < 3) // less than, false false
console.log(4 <= 3) // less than or equals, false
```
We can also compare `Number` values against each other.


### Logical comparisons

```js
console.log(true && true) // true
console.log(true && false) // false (in any order)
console.log(false && false) // false

console.log(true || true) // true
console.log(true || false) // true (in any order)
console.log(false || false) // false
```
Boolean are also used to make logical comparisons with `&&` and `||` operators, meaning `and` and `or` respectively.


### Empty values

We previously touched the topic of empty values in [Lesson 2](#lesson-2-values-and-variables) when we learned about `undefined` which we can use to say someting is actually nothing. Another way to do that in JavaScript is the `null` value.

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


### Conditional operations

```js
if (1 !== 1) {
  console.log('This is never called because 1 === 1')
}
```
After learning about booleans and comparisons we can finally use *conditional execution of code.* We sometimes want to execute code only if a condition is met. We begin with the `if` keyword followed by the conditional expression wrapped inside a pair of parenthesis `()`, followed by a code block to execute when the expression evaluates as `true`.

```js
if (false) {
  console.log('Duck')
}
else if (false) {
  console.log('Duck')
}
else {
  console.log('Goose') // "Goose"
}
```
Conditional operations can be composed like chains of options with no upper limit on complexity. Both `else` and `else if` are entirely optional. As the `if` and `else if` conditions evaluate as false, the `else`-block is executed.


### Summary
- [`Boolean` values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
- [Euquality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
- [Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#logical_operators)


### Useful things
- 


## Assignment 4: TODO


### Extra credit
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


## Assignment 5: Create an array of numbers, and remove values from it

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

## Assignment 6: Generate random array indexes

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


## Assignment 7: TODO

TODO


---


## Lesson 8: Destructuring and the spread syntax

### Summary
- [Spread syntax `...`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

## Assignment 8: Lottery system part 3 - finishing up the number system

Write a function called `pluckRandomElementsFromArray()` that accepts two parameters; `array` and `count`. The function should return `count` number of random elements from `array` parameter.

Write another function called `pickLotteryNumbers()` that acceps two parameters; `array` and `count`. The function should work like `pluckRandomElementsFromArray()` but **not** modify the parameter `array` that was passed to it by cloning it.

Write code to generate a series of numbers, and then use `pickLotteryNumbers()` to select random numbers from the list.
