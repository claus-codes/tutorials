# JavaScript deep dive

> This is very much a work in progress.

This tutorial aims to teach complete beginners [JavaScript](https://en.wikipedia.org/wiki/JavaScript); the programming language running in every Internet browser and powering the web as we know it.

If you find yourself struggling to understand the lessons or the assignments, please let me know so I can make improvements.


## How does this work?

This tutorial is split into 10 lessons that aim to teach you JavaScript with sample code and thorough explanations. All sample code should work when copy-pasted to any editor with the exception of lines of code that mention *throwing an Error*.

Each lesson is finished with an assignment that lets you put what you learned to the test by writing code yourself with clear specifications but no guidance.

Lessons feature the following recurrent chapters:

Recap
: Contains a list of links to documentation detailing concepts learned during the lesson. I recommend you study them carefully if you did not understand something.

Useful things
: These are things I didn't know where to put in the tutorial, but I would consider them things you **should** know.

Extra credit
: Appearing at the very end, beyond assignments for each lesson, extra credits are coding challenges that you should try after you've finished all the lessons and assignments. These will have you go over previous assignments and make changes to code you wrote.


## Workflow

I highly recommend registering an account with [CodePen](https://codepen.io/pen/) as they offer a free coding playground where you can write code that runs and saves automatically.

This tutorial uses the developer console exclusively for information, so the first thing you need to do is be able to see it.

CodePen
: If you are using CodePen, the button to open developer console can be found at the bottom-left corner of the workspace.

Chrome
: You can open Developer Tools with the **CTRL+Shift+J** hotkey.

**All of the code from the assignments should go in the same file.** Code written in earlier assignments will be used by later assignments. I would recommend writing a *comment* before the code of each assignment and the assignment number included in the connect. We will soon learn about comments in [Lesson 1](#lesson-1-hello-world).


## Table of Contents

- [Lesson 1: Hello World!](#lesson-1-hello-world)
- [Lesson 2: Values, variables and expressions](#lesson-2-values-variables-and-expressions)
- [Lesson 3: Functions](#lesson-3-functions)
- [Lesson 4: Boolean values, comparisons and conditional operations](#lesson-4-boolean-values-comparisons-and-conditional-operations)
- [Lesson 5: Arrays and loops](#lesson-5-arrays-and-loops)
- [Lesson 6: Math functions](#lesson-6-math-functions)
- [Lesson 7: Objects](#lesson-7-objects)


---


## Lesson 1: Hello World!

All software is just data processing and manipulation. Let me introduce you to two primitive data types found in JavaScript that we will be meeting soon.

Number
: The `Number` primitive data type represents *any real numbers* like `42`, `3.14159` or `-10000000000`

String
: The `String` primitive data type represents sequences of characters, and is commonly wrapped in either single-quotes like `'single'`, or in double-quotes like `"double"`. There is a third method which we will learn in [Lesson 2](#lesson-2-values-variables-and-expressions).


### A humble beginning

```js
console.log('Hello World!')
```
The first part, `console.log`, is the name of a built-in function in JavaScript that lets us write to the developer console which you should have open if you followed the tutorial so far. We pass it a single parameter; a `String` value of `'Hello World!'`

We will cover functions in more detail in [Lesson 3](#lesson-3-functions), but for now think of a function as a block of code that can be called by following it's name with a pair of parenthesis `()` wrapping any parameters separated by comma `,`


### Comments

```js
console.log('Hello again!') // I am a comment
```
In this example the part that reads `// I am a comment` seems trustworthy.

Anything written after a double backslash `//` is interpreted as not being part of the code in JavaScript. It's good practice to write comments for your own code to explain to yourself what is happening. It can prove to be be a valuable learning tool, and a potential future favor to anyome who might have to try to understand your code later.

```js
/* I am
   a multi-line
   comment */
```
JavaScript also offers multi-line comments, started with `/*` and terminated with a pairing `*/`. They can be useful to comment code out selectively, such as a list of parameters or a block of code that you don't want executed right now.


### Recap
- [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) is a primitive data type that represents a numeric value.
- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) is a primitive data type that represents a sequence of characters.
- [`console.log()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/log) logs all parameters from each call made to it and is incredibly useful for figuring out what is happening.


### Useful things
- [`console.error()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/error) lets you handle and trace errors. It can speed up debugging tremendously. **TODO**
- [`console.trace()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/trace) lets you trace the location where you called this function. **TODO**


---


## Assignment 1: Make your own call

Write code that calls `console.log()` with your own message or messages.

#### Extra credit
- Write your own logging function that uses `console.log()`.
- Add the current time and date before each log entry.
- Process every parameter that is of type `Object` with `JSON.stringify()`.
- Create a mechanism to turn the logging on and off.


---


## Lesson 2: Values, variables and expressions

If we want to store any value, like `Number` or `String` or anything else, we need to use variables.

```js
let num = 9
let text = 'coding is dope'
```
Variables are declared with the keyword `let` followed by the name of the variable, followed by an optional *assign operation* to set an initial value.

The code above declares two variables; `num` that we assign the `Number` value of `9`, and `text` we assign `String` value of `'coding is dope'`.


### Empty values

```js
let emptyVariable
console.log(emptyVariable) // undefined
```
You can declare a variable without assigning it an initial value. The variable `emptyVariable` gets a special *empty value* called `undefined`, which means it has not been given any value. You will learn more about empty values in [Lesson 4](#lesson-4-booleans-comparisons-and-conditional-operations).


### Constant values

```js
const immutableValue = 'I cannot be overwritten'
immutableValue = 'this will not work' // this will throw an Error
```
The `const` keyword creates a constant value, which acts like a variable but it's value cannot be changed after it's declaration. If you know a value will not change during execution, prefer to use `const` over `let` for the sake of code-readability and performance.


### Changing the value of a variable

```js
console.log(text) // "coding is dope"

const catchphrase = 'super easy, barely an inconvenience'
text = catchphrase
console.log(text)

num = num * 3
console.log(num) // 27
```
Variables declared with the `let` keyword can have their value changed by simply assigning them a new value.

In the code above a variable named `greeting` is given `String` value of `'Hello'`, and another variable named `frenchGreeting` gets `String` of value `'Bonjour'`. We call `console.log()` to see the current value of `greeting`. We then assign it the value of `frenchGreeting` before we log the value again to witness it changing.

We also set the new value of `num` to be an *expression* where the value is the evaluation of `num * 3`.


### Logging variables

```js
console.log('Message', text) // "Message" "JavaScript is awesome!"
```
You can use variables as parameters to functions just like we did with `Number` and `String` values. When we use a variable as a parameter, the parameter gets the *value of the variable*.

When adding logging to your code it's a good rule of thumb to add a `String` value describing context, or you might lose what you are looking for in a sea of log entries.


### Expressions

```js
console.log(23 * 3) // 69
```
This code calls `console.log()` again, but this time we pass it the expression `23 * 3` instead of a single value or variable. Expressions are evaluated on the fly. Heree we are performing a multiplication operation on numbers `23` and `3` and the code will output the result of the calculation in the console as expressions are evaluated to determine their value.

You can perform calculations with numbers using various mathematical operators.

Addition `+`
: The addition operator adds two numbers together, producing the sum of values.

Subtraction `-`
: The subtraction operator subtracts two numbers from one another, producing their difference.

Multiplication `*`
: The multiplication operator multiplies numbers, producing the product of the numbers.

Division `/`
: The division operator divides the left number, the dividend, with the right, the divisor.

Remainder `%`
: The remainder operator returns the remainder left over when left number is divided with right number.

Exponentation `**`
: The exponentation operator returns the result of raising left number to the power of the right number.

```js
console.log(9 % 6) // 3
console.log(10 ** 3) // 1000
```
The remainder and exponentation operators might not be very familiar to most people, so here's an example of both.

```js
console.log((num * 100) - 1363) // 1337
```
Parenthesis can be used to group operators together which gives us the ability to write complex calculations where maintaining a strict order of operations is necessary.

```js
let numberValue = 13
let notNumberValue = 'hello'
console.log(numberValue / notNumberValue) // NaN
```
When you try to use mathematical operators with values that are not a `Number`, a special `NaN` value is used which stands for **Not a Number**.


### String interpolation

```js
let a = 'ined'
let b = 'comb'
console.log(b + a) // "combined" 
```
Instead of performing addition like on `Number` values, the addition `+` operator with `String` values joins strings together.

```js
let name = 'wizard'
console.log(`Hello, ${name}?`) // "Hello, wizard?" 
```
You can use the backtick `` ` `` syntax to inject values directly in *template literals* that evaluate to a new `String` value. We simply wrap the `name` variable in that particular pattern of dollar sign `$` followed by curly braces `{}` around the value we want to inject.

```js
let title = 'My Website'
let multiLineText = 'two\nlines'
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
`
console.log(templateLiteralString) // filled template
```
To indicate a line-break on a normal string, we use the *escape-character* `\n`. Template literals instead use existing line breaks in the code.


### Naming variables

```js
let variable_with_underscores = 'This is called snake_case'
let variableWithCapitals = 'This is called camelCase'
let VARIABLE_WITH_UPPER_CASE = 'ALL CAPS AAAHHHH!!!!'
```
You can name your variables almost whatever you want with some restrictions; a variable's name cannot start with a number, should be alpha-numeric or the underscore `_` character.

What styles of naming things you adopt does not matter as it is a personal preference. You should always strive to be as descriptive as possible when naming things, as it can help make the program logic easier to follow and reason about.


### Recap
- [Variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables) are containers for values.
- [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) make it easy to inject `String` values to each other.
- [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is a concept from classic mathematics about the order in which calculations should be evaluated.
- [Remainder `%` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder)
- [Exponentiation `**` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)


### Useful things
- 


---


## Assignment 2: How old is that dog in human years?

> You met the cutest dog outside. He had the enthusiasm of a puppy, but was a grown ass dog. His owner told you he is six and a half years old.

Write code where you declare two variables: `dogAge`, which you should give any `Number` value between `1` and `20`, and `dogAgeInHumanYears`, which gets the value of the expression `dogAge * 7`.

Use `console.log()` to inspect both values, and see what happens when you modify the value of `dogAge`.

### Extra credit
- Turn the calculation into a function called `calculateDogAgeInHumanYears()` that accepts a single parameter `dogAge`.
- The actual "dog age" calculation is much more complex. Try to find the equation through Google and implement it in your code.


---


## Lesson 3: Functions

As mentioned in [Lesson 1](#lesson-1-hello-world), a `function` is essentially a block of code that can be executed by calling it by adding add a pair of parenthesis `()` after the function name, with any parameters separated by commas `,`. We have called `console.log()` in previous lessons, but it's time for us to define our own simple function.

```js
function addNumbers(a, b) {
  return a + b
}
```
To declare a new function we use the `function` keyword followed by the name of our new function which is `addNumbers`. Similar to when calling a function with parameters, we wrap any parameter names in parenthesis `()` and separate them by commas in the definition as well.

This function accepts two parameters, `a` and `b`, which can be thought of as internal variables that receive the value of parameters passed when calling the function in the same order as they were passed.

The *function body* is a block of code that's wrapped inside curly brackets `{}`. The `return` keyword inside the function body will cause the function to stop executing and return the value of the expression which is `a + b` which is a simple addition operation with the function parameters.


### Parameters and values

```js
let firstNumber = 12
let secondNumber = 30
let sum = addNumbers(firstNumber, secondNumber)
console.log(sum) // 42
```
In the code above we first declare two variables, `firstNumber` and `secondNumber`, which both contain a `Number` value.

We create a third variable `sum` which receives the value returned by calling `addNumbers(firstNumber, secondNumber)`.

What happens inside the `addNumbers()` function when called in the code above is that parameter `a` gets the value of `firstNumber`, and `b` gets the value of `secondNumber` as they were used in that specific order when calling the function.


### Documenting your code

```js
/**
 * Adds two numbers together.
 * @param {number} a - First number
 * @param {number} b - Second number
 * @return {number} The sum of two numbers
 **/
function addNumbers(a, b) {
  return a + b
}
```
This oddly formatted block-level comment before the `addNumbers()` function definition is called JSDoc. It's a standard way to document functionality and there are tools that generate documentation from annotated code like this. Good documentation can be invaluable as projects or teams grow in size and complexity.


### Default parameters

```js
function roundNumber(value, precision = 2) {
  const precisionFactor = 10 ** precision
  return Math.floor(value * precisionFactor) / precisionFactor
}
```
We define a new function `roundNumber()` that accepts two parameters; `value` that has no default value and is required, and `precision` which is an optional parameter due to us giving it a default value by writing `precision = 2` in the parameter definitions.

> Piiloviestin mahdollisuus!

```js
const f = 1983.518273645
console.log(roundNumber(fraqup)) // 1983.51
console.log(roundNumber(fraqup, 3)) // 1983.518
```
This function rounds a decimal number based on precision.

### Functions as variables

```js
let divideBy = function(dividend, divisor) {
  return dividend / divisor
}
console.log(divideBy(8022, 6)) // 1337 
```
Variables can also contain functions, and they can be called the same way as regular functions would.

```js
const divideByShort = (dividend, divisor) => (dividend / divisor)
console.log(divideByShort(8022, 6)) // 1337
```
JavaScript also has another way to write a function definition, the *arrow function expression* `=>`

Both of these versions of `divideBy()` are functionally identical; using the `=>` shorthand we can lose the `function` keyword. If we don't need the curly brackets `{}` around the function body we can also drop the `return` keyword, and simply state the expression after the fat arrow.

It's usually a good idea to define functions as constant values rather than variables.


### Recap
- [Function declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)
- [Function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function)
- [Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [JSDoc](https://devhints.io/jsdoc)


### Useful things
- 


## Assignment 3: A flexible hello

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

Boolean
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
Conditional operations can be composed like chains of options with no upper limit on complexity. Both `else` and `else if` are entirely optional.

The comparison of `4 > 3` evaluates as `Boolean` value `true`, so logging `'Great success!'` is always executed while the code in the `else if` and `else`-blocks are never executed.


### Recap
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

Initialization
: Evaluated once before the loop begins. This is where we set up any variables we might use in the loop, like `index` which we gave the value of zero `0` as we plan to count indices upwards.

Condition
: Evaluated once before each loop iteration. If the expression evaluates to `Boolean` value of `true`, the code inside the loop is executed and if the expression evaluates to `Boolean` value of `false`, the loop ends. With `index < countries.length` we are checking if `index` is smaller than the `length` property of the `countries` array. This evaluates as `Boolean` value of `true` until `index` has a value of `countries.length - 1` which is the maximum index we can access.

Afterthought
: Evaluated at the end of loop iteration. This happens before the next iteration and here we usually update our counters. The expression `i++` is using the increment `++` operator.

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


### Recap
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


## Assignment 5: Creating an array of numbers, and remove values from it

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


### Recap
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


### Recap
- [`Object` type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [`JSON.stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)


## Assignment 7: TODO

TODO


---


## Lesson 8: Destructuring and the spread syntax

### Recap
- [Spread syntax `...`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

## Assignment 8: Lottery system part 3 - finishing up the number system

Write a function called `pluckRandomElementsFromArray()` that accepts two parameters; `array` and `count`. The function should return `count` number of random elements from `array` parameter.

Write another function called `pickLotteryNumbers()` that acceps two parameters; `array` and `count`. The function should work like `pluckRandomElementsFromArray()` but **not** modify the parameter `array` that was passed to it by cloning it.

Write code to generate a series of numbers, and then use `pickLotteryNumbers()` to select random numbers from the list.
