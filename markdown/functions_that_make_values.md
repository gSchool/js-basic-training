# Functions that Make Values

As discussed earlier, while all functions **do** something, calling functions can also result in that function **making** something new.

## Objectives

By the time you complete this section you should be able to:

- Speak accurately about functions **returning** values when **called**
- Understand that all functions in JavaScript return values
- Use a few built in functions (`String`, `Math.min`, `Math.max`) to return new values

## Terminology for Functions That Make New Things

**When we talk about functions that "make new things" we use the more accurate technical language that _calling_ functions _return_ new values.**

In the real world it is perfectly natural to say "When I **call** someone they will **return** my call," and thinking about function **calls** and their resulting **return** values in this way can prove helpful.

Here's an example using a built-in function that we have not yet discussed: `typeof`. The `typeof` function takes a single **argument**, and when **called** returns a **string value** that indicates the **type** of the value that was **passed in.** Here we will **call** `typeof`, which will **return** a new value, and will **pass** that new value as an **argument** into `console.log`:

```javascript
console.log(typeof(8));                   // logs `'number'` to the console
console.log(typeof('gimme a new value')); // logs `'string'` to the console
console.log(typeof(true));                // logs `'boolean'` to the console
console.log(typeof(undefined));           // logs `'undefined'` to the console
console.log(typeof(null));                // logs `'object'` to the console
```

## All Functions Return New Values

**In JavaScript, all functions return a new value when called. When programmers create functions that they don't intend to return a new value, that function will return `undefined`. Returned values, like any value, can be passed into functions.**

One such function that is not intended to return a new value is `console.log`, however, since **every function call in JavaScript returns a value**, we should not be surprised to see that `console.log` returns `undefined`. Here we call `console.log`, passing its newly created return value into `console.log`.

```javascript
console.log(console.log()) // logs `'undefined'` to the console
```

## A Few Built In Functions Returning New Values

Let's explore a few built in functions that return values in order to both increase our fluency with JavaScript, and as a way to practice understanding return values and comparison operators.

### The Built In String Function

The built in function `String` takes a single argument of any type and returns a string representation of it:

```javascript
console.log(String(8));         // logs `'8'` (as a string) to the console
console.log(String(undefined)); // logs `'undefined'` (as a string) to the console
```

:question: What will each of the following lines of code log to the console? Why?

```javascript
console.log(String(1234));
console.log(typeof(String(null)));
console.log(String(true) === true);
console.log(String(false) === 'false');
console.log(String(console.log('Not undefined')) === 'undefined');
console.log(String(console.log('Not undefined')) !== 'Not undefined');
```

### The Build In Math.max and Math.min Functions

The `Math.min` and `Math.max` functions both take any number of numerical arguments and return a value of the `number` type for whichever was the smallest or largest number passed in, respectively.

```javascript
console.log(Math.max(2, 5, 8, 1, 3)); // logs `8` to the console
console.log(Math.min(2, 5, 8, 1, 3)); // logs `1` to the console
```

:question: What will each of the following lines of code log to the console? Why?

```javascript
console.log(Math.max(8, 7, 9) === 9);
console.log(Math.min(8, 7, 9) === '7');
console.log(Math.min(8, 7, 9) === Math.max(3, 7, 4));
console.log(String(Math.min(8, 7, 9)) === '9');
console.log(Math.max(0) >= Math.min(0));
console.log(typeof(Math.max(0)) === 'number');
console.log(typeof(String(Math.max(0))) === typeof(String('number')));
```

## Conclusion

All JavaScript functions, when called, return a value. Even functions that are not intended to be used for their return values return `undefined`. Returned values, just like any other value, can be passed into functions.

Before continuing further into using functions, and eventually, defining our own, we need to take a brief segue into **variable** declaration, which will allow us to store values, including those returned from functions, so that we can use them in a variety of locations in our programs.

Before continuing, be sure that you can:

- Speak accurately about functions **returning** values when **called**
- Understand that all functions in JavaScript return values
- Use a few built in functions (`String`, `Math.min`, `Math.max`) to return new values

## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Dev Environment Setup](setup.md)
- [Introduction to Functions](intro_to_javascript_functions.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- [JavaScript Types Crash Course](type_crash_course.md)
- *Functions that Make Values*
- [Variables](variables.md)
- [String Methods](string_methods.md)
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- [Leveraging Multiple Functions](leveraging_multiple_functions.md)
- [Next Steps](next_steps.md)

### Advanced Content

- [Passing Functions as Arguments](passing_functions_as_arguments.md)
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
