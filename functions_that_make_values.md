# Functions that Make Values

As discussed earlier, while all functions **do** something, calling functions can also result in that funciton **makng** something new.

## Objectives

## Terminology for Functions That Make

**When we talk about functions that "make new things" we use the more accurate technical language that _calling_ functions _return_ new values.**

In the real world it is perfectly natural to say "When I **call** someone they will **return** my call," and thinking about function **calls** and their resulting **return** values in this way can prove helpful.

Here's an example using a built-in function that we have not yet discussed: `typeof`. The `typeof` function takes a single **argument**, and when **called** returns a **string value** that indicates the **type** of the value that was **passed in.** Here we will **call** `typeof`, which will **return** a new value, and will **pass** that new value as an **argument** into `console.log`:

```javascript
console.log(typeof(8));                   // logs `'number'` to the console
console.log(typeof('gimme a new value')); // logs `'string'` to the console
console.log(typeof(true));                // logs `'boolean'` to the console
console.log(typeof(undefined));           // logs `'undefined'` to the console
console.log(typeof(null));                // logs `'null'` to the console
```

## All Functions Return New Values

**In JavaScript, all functions return a new value when called. When programmers create functions that they don't intend to return a new value, that function will return `undefined`.**

One such function that we would not expect to return a new value is `console.log`, however, since every function call in JavaScript returns a value, we should not be surpised to see that `console.log` returns `undefined`. Here we call `console.log`, passing its newly created return value into `console.log`.

```javascript
console.log(console.log()) // logs `'undefined'` to the console
```
