# Passing Functions as Arguments to Other Functions

## Objective

By the end of this lesson you will be able to:

- Define and invoke a function that takes a function definition as one of its arguments
- Return the results of calling this passed-in function with other arguments passed into the main function

In service of this main objective you will also be able to:

- Define and invoke functions that correctly utilize *rest parameters*
- Be able to use the *spread syntax* in a function call, to convert an array into a list of arguments

## Prerequisites

Before taking this lesson you should:
- Know the difference between defining a function and calling/invoking/executing a function.
- Be able to write and execute functions that take arguments and return values based on those passed-in arguments.
- Be familiar working with arrays, including iterating over them with a `for...of` loop.

## Motivation

Learning the techniques in this lesson will set the beginning stages for your mastery of *higher order functions*: functions that either receive functions as arguments, or return functions themselves. Learning how to effectively utilize higher order functions create the possibility to solve otherwise unsolvable problems, and, to solve otherwise solveable problems more elegantly. Higher order functions are a key feature of JavaScript.

Additionally, you will be introduced to a couple intermediate JavaScript language features, *rest parameters* and the *spread syntax* that will enhance your abilities to write concise JavaScript.

## The Plan

In this lesson, in order to be able to correctly define and invoke functions that invoke passed-in functions, and to be able to invoke these passed-in functions with other arguments passed into the main function, you will first get comfortable with:
- Passing in function definitions and invoking them within main functions.
- Gathering into arrays the arguments that need to be given to passed-in functions using *rest parameters*.
- Using the *spread syntax* to deliver the elements of *rest parameter* arrays to passed-in functions.

## Passing In and Invoking Functions

### Passing In and Returning Function Definitions

In JavaScript, function definitions are in fact a special kind of object, which like any other object, can be passed into functions, and returned from them.

The following code therefore will not throw an error:

```javascript
function sayWord() {
  return 'word';
}

function reflectFunction(func) {
  return func;
}

var speakWord = reflectFunction(sayWord);
```

:question: Are we invoking the `sayWord` function at any point in the code above?

:question: What type of value is `speakWord`?

:question: What would happen if we tried to invoke `speakWord`?

:speak_no_evil: Describe, in a single sentence, what `reflectFunction` does.

### Passing In Functions and Returning the Results of Calling Them

The following code, which once again passes the `sayWord` function definition into another function, looks very similar to the code above, but is significantly different.

:speak_no_evil: Read through the following code block out loud. Try to use words like "define", "call", "parameter", "argument", "passed-in", and "return":

```javascript
function sayWord() {
  return 'word';
}

function callFunction(func) {
  return func();
}

var spokenWord = callFunction(sayWord);
```

:question: What type of value is `spokenWord`?

:question: What would happen if we tried to invoke `spokenWord`?

:question: What is the key difference between `reflectFunction` (above) and `callFunction`?

:speak_no_evil: Describe, in a single sentence, what `callFunction` does.

### Passing In Functions and Returning the Results of Calling Them With a Fixed Argument

Rather than simply invoking the passed-in function, you can also invoke whatever function is passed in with a fixed argument:

:speak_no_evil: Read through the following code block out loud, being sure to distinguish between variable and strings, as well as function definitions and function invocations:

```javascript
function sayWord(word) {
  return word;
}

function callFunctionWithWord(func) {
  return func('word');
}

var spokenWord = callFunctionWithWord(sayWord);
```

:question: What type of value is `spokenWord`?

:question: What is the key difference between `callFunction` (above) and `callFunctionWithWord`?

:speak_no_evil: Describe, in a single sentence, what `callFunctionWithWord` does.

:question: If we passed a different function into `callFunctionWithWord`, what argument would it be called with?

:star: Complete the `callFunctionWithThree` definition below. `callFunctionWithThree` should return the results of passing the number `3` into whatever function is passed into `callFunctionWithThree` as its first argument.

```javascript
function callFunctionWithThree(func) {
  // your code here
}

function double(num) {
  return num * 2;
}

// Example behavior

callFunctionWithThree(double); // should return 6
```

### Passing In Functions and Returning the Results of Calling Them With Another Passed-In Argument

Rather than passing the same fixed argument into the passed-in function, you may wish to also pass into the main function the argument that should be passed into the passed-in function when it is invoked.

:speak_no_evil: Read through the following code block out loud:

```javascript
function sayWord(word) {
  return word;
}

function callFunctionWith(func, word) {
  return func(word);
}

var spokenWord = callFunctionWith(sayWord, 'word');
```

:question: What type of value is `spokenWord`?

:question: What is the key difference between `callFunctionWithWord` (above) and `callFunctionWith`?

:speak_no_evil: Describe, in a single sentence, what `callFunctionWith` does.

## Using Rest Parameters to Store Arguments in an Array

We will now digress into *rest parameters* and the *spread syntax*, before putting everything together.

In JavaScript, when defining a function, you may prefix the last parameter in the definition with an ellipses (`...`). If you do this, any argument passed into the function during its invocation, at this position in the arguments list and later, will be gathered up into an array. In the function definition, the array is stored in the variable name of the parameter prefixed with the ellipses:

This special kind of parameter, prefixed with an ellipses, is called a *rest parameter* as in, "the *rest* of the arguments will be gathered into an array by this name."

Here's a simple example where the first parameter is a rest parameter, meaning the first argument, and all the *rest*, will be available as an array by the name of the parameter, in this case the name is `allTheArgs`. Like any parameter in a function definition, the rest parameter can be given any legal name: it is the ellipses prefix that makes it special, not the name that we give it:

```javascript
function countArguments(...allTheArgs) {
  return allTheArgs.length;
}

countArguments('argumentOne', 'argumentTwo');                  // returns 2 since `allTheArgs` is an array containing all the passed-in arguments.
countArguments('argumentOne', 'argumentTwo', 'argumentThree'); // returns 3
countArguments();                                              // returns 0 since `allTheArgs` is here an empty array.
```

Remember that a rest parameter must be the last parameter, but does not have to be the first. If the rest parameter is not the first parameter, it stores the *rest* of the arguments from its position forward in an array by its name, but not those preceding it:

```javascript
function countTheRestOfTheArgs(firstArg, ...theRestOfTheArgs) {
  return theRestOfTheArgs.length;
}

countTheRestOfTheArgs('argumentOne', 'argumentTwo');                  // returns 1
countTheRestOfTheArgs('argumentOne', 'argumentTwo', 'argumentThree'); // returns 2
countTheRestOfTheArgs();                                              // returns 0
```

:question: In each of the three calls to `countTheRestOfTheArgs` above, what is the value of `firstArg`?

:speak_no_evil: Read out loud the following block of code:

```javascript
function average(...numbers) {
  let total = 0;
  for(let number of numbers) {
    total += number;
  }
  return total / numbers.length;
}
```

:question: Why are we able to use the `length` property of `numbers`?

:question: Why are we able to use a `for...of` loop to iterate over `numbers`?

:star: Complete the `hasAtLeastThreeArgs` function below to return a boolean indicating whether or not it is called with at least 3 arguments total.

```javascript
function hasAtLeastThreeArgs(arg1, ...rest) {
  // your work here
}

// Example behavior

hasAtLeastThreeArgs(1, 2, 3)    // true
hasAtLeastThreeArgs(1, 2, 3, 4) // true
hasAtLeastThreeArgs(1, 2)       // false
```

## Passing Array Values as Arguments to Functions With the Spread Syntax

When not used with a **parameter** in a function **definition**, the ellipses (`...`) in JavaScript has a different functionality altogether: it is used to *spread* out the contents of an expression into multiple values where multiple values are expected, for example, *spread*ing an array into a list of function arguments.

As an example, consider that `console.log` expects any number of arguments, and prints each of them in order, separated by a space:

```javascript
function logArgs(word1, word2, word3) {
  console.log(word1, word2, word3);
}

logArgs('This', 'is', 'basic.'); // Logs to the console: 'This is basic.'
```

Using the *spread syntax* we could write a function that accepted an array of any length, and then *spread* the array into its values for consumption by `console.log` which accepts a list of arguments:

```javascript
function logArray(arrayOfWords) {
  console.log(...arrayOfWords);
}

let words = ['This', 'is', 'really', 'cool.'];
logArray(words); //Logs to the console: 'This is really cool.'
```

:question: What would happen if we removed the ellipses from the call to `console.log` in the `logArray` definition above?

:question: Where is the only place that an ellipses indicates a rest parameter?

:star: Use the spread syntax to implement a solution to `combineArrays` below:

```javascript
// Recall that to add multiple values to an array using `Array.push`,
// you must pass it multiple arguments:
var array1 = [1, 2];
array1.push(3, 4); // <--- Multiple arguments, not a single array.
console.log(array1) // [1, 2, 3, 4];

// If we pass in an array of values,
// `Array.push` simply adds the entire array as the next value.
var array2 = [5, 6];
array1.push(array2);
console.log(array1) // [1, 2, 3, 4, [5, 6]];

// `combineArrays` should return a single array with
// a length of `array1.length` + `array2.length`.
function combineArrays(array1, array2) {
  // your code here
}

// Example behavior

combineArrays(['a', 'b'], ['c', 'd']); // ['a', 'b', 'c', 'd']
```

## Putting it All Together

You now have the following techniques at your disposal which can be used to define and invoke functions that accept functions as arguments, and to invoke these passed-in functions with other arguments passed-in to the main function:
- Passing in function definitions and invoking them within main functions.
- Gathering up arguments that need to be given to passed-in functions using rest parameters.
- Using the spread syntax to deliver the elements of rest parameter arrays to passed-in functions.

:star2: Complete the `testFunction` function below, which will allow you to test the behavior of a function that you pass in. Be sure to use rest parameters and spread syntax in your solution, and to check out the expected behavior below before beginning.

```javascript
// See expected behavior below
function testFunction(func, expected, ...argsToPassToFunc) {
  // your work here
}

/* Expected behavior */

// We will pass these 3 functions into `testFunction` below
function double(number) {
  return number * 2;
}

function add(number1, number2) {
  return number1 + number2;
}

function brokenAverage(num1, num2, num3) {
  return (num1 + num2 + num3) / 4; // <---- we should divide by 3 here, not 4
}

// `testFunction` takes a function, an expected output of calling the function,
// followed by any arguments that need to be passed to the passed-in function,
// and returns a boolean
// indicating whether or not calling the passed-in function with the given arguments
// results in the expected behavior.

// Here we expect that `double` will return `12` when given the argument `6`.
// If `double` is working correctly, `testFunction` should return `true`.
testFunction(double, 12, 6); // returns `true`

// Here we expect that `add` will return `13` when given the arguments `5`, and `8`.
// If `add` is working correctly, `testFunction` should return `true`.
testFunction(add, 13, 5, 8); // returns `true`

// Here we expect that `brokenAverage` will return `2`, when given the arguments `1`, `2` and `3`.
// Since `brokenAverage` is not working correctly, `testFunction` should return `false`.
testFunction(brokenAverage, 2, 1, 2, 3); // returns `false` since `brokenAverage` is broken.

// We can use `testFunction` to test itself.
// Here we expect that `testFunction` will return `true` when given the arguments `add`, `5`, `2`, and `3`.
// If `testFunction` is working correctly, `testFunction` should return `true`.
testFunction(testFunction, true, add, 5, 2, 3); // returns true
```

## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- [Functions that Make Values](functions_that_make_values.md)
- [JavaScript Types Crash Course](type_crash_course.md)
- [Variables](variables.md)
- [String Methods](string_methods.md)
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- [Leveraging Multiple Functions](leveraging_multiple_functions.md)
- [Next Steps](next_steps.md)

### Advanced Content

- *Passing Functions as Arguments*
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
